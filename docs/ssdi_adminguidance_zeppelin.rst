Using Zeppelin for Analytics
============================

What is Zeppelin?
-----------------

`Apache Zeppelin <https://zeppelin.apache.org/>`__ is a user-configurable data dashboard that connects to the back-end PostgreSQL database where the SSDI Metadata records are stored. It allows catalogue adminstrators to query the metadata alongside the other data stored in the database, using standard Structured Query Language (SQL). A read-only user is used for the database connection to ensure that the data cannot be edited or deleted.

Logging in
----------

It can be accessed by clicking the link **Analytics (admin only)** in the SSDI catalogue, and will open in a new tab. To log in (this must be done separately to the SSDI catalogue), click the **Login** buttin in the top right and use your catalogue username and password.

Once you have logged in, click the **SSDI Analytics** link on the left.

Getting Started
---------------

Zeppelin notebooks comprise a series of **paragraphs** with the following elements:

* An optional title
* Buttons to run or refresh the query, hide visual elements, and more configuration options
* The SQL statement, otherwise known as the **editor** (this may be hidden)
* An optional dynamic entry form such as a dropdown list or text box
* A set of charting options, such as table, bar graph or piechart, along with data download options
* The results, otherwise known as the **output**

SSDI Catalog Database Structure
-------------------------------

There are three schemas in the SSDI database. To refer to a table, view (saved query) or function in any schema other than the public one, it is necessary to use the form **schema.object**.

audit
#####

This holds the functions and tables required for the audit history plugin. The **logged_actions** table holds the actual audit history.

custom
######

Holds any custom functions or views (database queries) added to the core GeoNetwork database.

The key views are:

* **metadata_xml**: this is a copy of the main metadata table in the public schema, with the difference that the **data_xml** column contains the actual stored metadata in xml format rather than as a blob. This allows xpath functionality to be used, so that the metadata itself can be queried.
* **all_records**: this is a simplified conversion of the actual metadata into database columns. It is not all-encompassing as the xml structure doesn't map exactly to a flat table format. 

If **all_records** does not include the necessary information, it is possible to update it, but this must be done in the PostgreSQL database itself, not in zeppelin.

Other views have been created to simplify the SQL used in the zeppelin paragraphs.

public
######

This holds the core GeoNetwork tables. The key tables are:

* **metadata**: holds the actual metadata records along with ownership, schema, changedate and harvesting information (amongst other things)
* **groups**: lists the groups
* **users**: lists the users

Relationships between tables are done with id fields. The naming convention is to name the column **id** in the primary table, and **tableid** in the secondary table. So for example, the **usergroups** table that contains information on which users are members of which groups has the following columns:

* userid: the id from the user table
* groupid: the id from the group table
* profile: the user's profile within the given group

Some tables also have translation tables, which have a **des** suffix. This contains the display name for the given object in the different languages that GeoNetwork supports. Again, the id field is used to link the primary table to the translation table, but the naming convention is not always consistent. As an example, the groupsdes table which shows the display name for groups has the following columns:

* iddes: the id from the group table
* langid: the language shortcode
* label: the display name in the given language

See below on how to use zeppelin to understand the tables in order to build your own queries.

Constructing new paragraphs or queries
--------------------------------------

So it's possible to construct new queries, the following paragraphs can be used to understand the structure of the database and tables:

* **Get tables in public, custom and audit schemas** : This lists the tables and views in the audit, custom and public schemas. It is primarily used to get the correct table name for use in the query below.
* **Find the columns and data types for a given table**: This lists the columns and data types for the table entered into the dynamic text box. Note that this should be entered without a schema prefix.

Basic multi-table queries
#########################

If you wish to construct a query containing columns from two or more tables or views then the general approach is to use table aliases and joins on the id fields. For example, to construct a query showing usernames, the display name for the groups they belong to, and their profiles in that group, then the following syntax would be used::

	SELECT u.username, s.profile, g.label 
	FROM users u 
	JOIN usergroups s ON u.id=s.userid 
	JOIN groupsdes g ON s.groupid = g.iddes 
	WHERE g.langid = 'eng'
	ORDER BY username, label, profile;

Queries involving xml
#####################

To query the stored metadata in custom.metadata_xml it is necessary to use XPath syntax within PostgreSQL. `XPath <https://en.wikipedia.org/wiki/XPath>`__ is a query language for selecting nodes from an XML document. To use it you will need to interrogate the XML of a record, either by viewing it in the XML view when editing, or downloading it as XML and opening it in a text editor. Learning XPath is beyond the scope of this guide, but the above link gives a primer on the syntax.

PostgreSQL has a function called `xpath <https://www.postgresql.org/docs/9.6/functions-xml.html>`__ for interrogating XML. It takes the following parameters:

* **xpath**: the Xpath for the xml element you want
* **xml**: the xml it should interrogate
* **nsarray**: an array of namespaces referenced in the XPath query. These are the prefixes before the metadata elements, such as gmd:fileIdentifier or gco:CharacterString. Each namespace in the XPath query needs to have both the prefix and the namespace URI. These can be found in the root element of a metadata record if you view it as XML.

The xpath function returns an array of values. These must be concatenated into a string to use them in queries. The PostgreSQL `array_to_string <https://www.postgresql.org/docs/9.6/functions-array.html>`__ function is used for this. It takes the following parameters:

* **array**: the array to convert
* **delimiter**: the character used to delimit the array values when converted to a string
* **null string (optional)**: the optional character used in place of any NULL values found in the array

The following example extracts the uuid and title from the metadata records, using the **data_xml** column from **custom.metadata_xml** as the xml source. If there were multiple titles, they would be separated by commas::

	SELECT uuid, array_to_string
		(
			xpath
			(
				'/gmd:MD_Metadata/gmd:identificationInfo/gmd:MD_DataIdentification/gmd:citation/gmd:CI_Citation/gmd:title/gco:CharacterString/text()', 	metadata_xml.data_xml, 
				'{{gco,http://www.isotc211.org/2005/gco},{gmd,http://www.isotc211.org/2005/gmd}}'
			), 
		',')
	AS title FROM custom.metadata_xml;

(note that the above query will result in some blank rows- these are generally template records)









