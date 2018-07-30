Creating Discovery Metadata
===========================

This section will guide the user through the process of creating discovery metadata records on `spatialdata.gov.scot <https://spatialdata.gov.scot>`__. Discovery metadata can be added to the 
portal by `importing an existing metadata <#import-existing-metadata>`__ XML file, `creating a new record from a template <#creating-metadata-from-a-template>`__, 
`duplicating an existing record <#duplicating-existing-metadata>`__, or `harvesting records <#harvesting-metadata>`__ from other metadata portals. 

Importing existing metadata
---------------------------

Prior to following the steps below to import an existing metadata record, please review `Annex 1 <UserDoc_Chap8_Annex1.rst#annex-1-requirements-for-metadata-to-be-correctly-identified-as-uk-gemini>`__.

To import an existing XML metadata record:

	**1|** Click the |button_contribute| button in the header menu and choose |button_contribute_import|. This will take the user to the **Import new records** menu board.

	**2|** Select where to import the record from. Options are from your computer (default), a URL, by copy/paste, or from a server.
	
	**3|** Select **Metadata** from the type of record dropdown.
	
	**4|** Indicate how the unique identifier for the record (UUID) should be treated. If you are uploading in order to refine or change an existing record, then choose the **Overwrite metadata with the same UUID** option. If you are uploading to create a new metadata record then choose the **Generate UUID for inserted metadata** option. If the XML contains a UUID that does not already exist on the portal but you would like to keep this UUID then the **None** option should be selected.

	*Note: The UUID is a generated automatically by whatever internal system (i.e. ESRI ArcGIS) was used to write and manage your metadata. In xml, it can be found at the top of the page under the file identifier section. Within the portal, the UUID or File Identifier can be found at the bottom of the metadata record display. This UUID, together with the metadata date stamp, are used to ensure records are unique within* `spatialdata.gov.scot <https://spatialdata.gov.scot>`__, `data.gov.uk <http://data.gov.uk/>`__ *and other metadata catalogues.*

	**5|** Under the **Apply XSLT conversion** menu, select which translation option should be used to convert the format of the metadata (e.g. choose ESRI_ISO-to-GEMINI_22 if converting from ArcGIS format to UK Gemini). The option **_to_gemini** should be chosen as the default.
	
	*Note: For an xml that is already in Gemini 2.2 format, review the guidance in* `Annex 1 <#annex-1-requirements-for-metadata-to-be-correctly-identified-as-uk-gemini>`__. *If the record contains these elements, the* **Apply XSLT conversion** *option can be left blank. If the metadata does not contain these elements but is otherwise in Gemini 2.2 format, then select the* **_to_gemini** *conversion.*
	
	**6|** Optionally, select whether to validate the record on import.
	
	*Note: it is recommended that the validate option be left un-ticked, and users perform a validation of the record after import. If the validation option is ticked and an error is found, the record will fail to import.*

	**7|** Leave the **Assign to current catalog** option ticked.
	
	**8|** Assign the record to a user group.
	
	**9|** Assign the record to the appropriate licence category (i.e. OGL, NCGL, INSPIRE or other).
	
	*Note: categories can also be amended at a later date. See* `assigning a licence category <UserDoc_Chap6_Edit.rst#assigning-a-licence-category>`__.
	
	**10|** Click the |button_contribute_importconfirm| button.
	
|userdoc_fig_5_1_1_ImportMetadata|

**Figure 5.1.1:** Importing an existing XML metadata record

When the import operation has finished, an **Import Report** will be displayed on the right-hand side of the screen, indicating whether or not the 
import has been successful. Following a successful import, users should verify that their records are valid. Consult the 
`Validating metadata <UserDoc_Chap6_Edit.rst#validating-metadata>`__ section for details. Amendments to the record may be required to make it fully Gemini compliant.

Creating metadata from a template
---------------------------------

Basic templates are available for users to create metadata directly on `spatialdata.gov.scot <https://spatialdata.gov.scot>`__.

To create a metadata record using an available template:

	**1|** Click the |button_contribute| button in the header menu. This will enable the **Contribute** board, where all records the user has access to will be listed.

	**2|** Click the |button_contribute_addrecord| button to the right of the page.
	
	**3|** Choose the type of record to be created based on the type of resource that is being documented, i.e. a dataset, series or service record. When selected available templates for that type are displayed.
	
	*Note: templates for dataset and service metadata are slightly different. Metadata for a service has extra elements for the spatial data service type (i.e. view, download, etc.) and for coupled resources.*
	
	**4|** Click on the template to be used (e.g. for a dataset template, there is an option for a raster or vector data template).

	**5|** Click the |button_contribute_create| button to create the new record. This will automatically take the user to the editing board where elements of the new record can be modified. See `Editing a metadata record <UserDoc_Chap6_Edit.rst#editing-metadata>`__ for guidance on documenting the resource.
	
	*Note: if the user is an editor for multiple groups or an administrator to the site, they may be presented with multiple templates of the same name. Additionally, they will be required to select which group folder to create the metadata record in.*

|userdoc_fig_5_2_1_CreateTemplate|

**Figure 5.2.1:** Creating a metadata record from a template

Duplicating existing metadata
-----------------------------

One of the easiest ways to create metadata on the portal is to duplicate an existing record. This is particularly useful for organisations where many
of the metadata elements are the same for all records (e.g. points of contact, etc.)

To create a metadata record by duplicating and existing record:

	**1|** Click the |button_contribute| button in the header menu. This will enable the **Contribute** board, where all records the user has access to will be listed.

	**2|** Click the duplicate icon (|button_contribute_duplicate|) next to the record name.
	
	**3|** Click the |button_contribute_create| button to create the new record. This will automatically take the user to the **editing** board where elements of the new record can be modified. See `Editing a metadata record <UserDoc_Chap6_Edit.rst#editing-metadata>`__ for guidance on documenting the resource.

	*Note: if the user is an editor for multiple groups or an administrator to the site, they will be required to select which group folder to create the duplicate metadata record in.*

|userdoc_fig_5_3_1_Duplicate|

**Figure 5.3.1:** Duplicating an existing metadata record

Harvesting metadata
-------------------

`Spatialdata.gov.scot <https://spatialdata.gov.scot>`__ has the capability to automatically consume metadata from external services on a scheduled basis. Organisations that maintain their own
spatial data portals which are interested in having their records automatically harvested should contact `SSDI.Metadata@gov.scot <mailto:SSDI.Metadata@gov.scot>`__.

Creating directory metadata
---------------------------

Directory records are a means of automatically populating fields such as those for the `point of contact <UserDoc_Chap7_Elements.rst#point-of-contact>`__ section of a 
metadata record with pre-written values. This is useful if you have to create multiple records that share the same point of contact.

To create a directory entry:

	**1|** Click the |button_contribute| button in the header menu.

	**2|** Click either |button_contribute_managedirectory| from the contribute drop down or the button on the right hand side of the page. This will bring the user to the manage directories page.

	**3|** Duplicate the entry marked 'TEMPLATE TO DUPLICATE' by clicking the |button_contribute_duplicate| icon. Alternately, you could duplicate an existing record you have already created.

	**4|** Amend the entry as appropriate and click |button_contribute_savedirectory| to save changes.
	
	**5|** Click |button_contribute_saveclosedirectory| to save and exit.

	*Note: The individual name field is not mandatory for the UK Gemini standard, however, for directories it can be used to identify teams/business areas if you have a number of different contact details within an organisation (e.g. GIS, Planning, etc.)*

|userdoc_fig_5_5_1_DirectoryEntry|
 
**Figure 5.5.1:** Creating a directory entry

.. |userdoc_fig_5_1_1_ImportMetadata| image:: media/userdoc_fig_5_1_1_ImportMetadata.png
.. |userdoc_fig_5_2_1_CreateTemplate| image:: media/userdoc_fig_5_2_1_CreateTemplate.png
.. |userdoc_fig_5_3_1_Duplicate| image:: media/userdoc_fig_5_3_1_Duplicate.png
.. |userdoc_fig_5_5_1_DirectoryEntry| image:: media/userdoc_fig_5_5_1_DirectoryEntry.png
.. |button_contribute| image:: media/button_contribute.png
.. |button_contribute_import| image:: media/button_contribute_import.png
.. |button_contribute_importconfirm| image:: media/button_contribute_importconfirm.png
.. |button_contribute_addrecord| image:: media/button_contribute_addrecord.png
.. |button_contribute_create| image:: media/button_contribute_create.png
.. |button_contribute_duplicate| image:: media/button_contribute_duplicate.png
.. |button_contribute_managedirectory| image:: media/button_contribute_managedirectory.png
.. |button_contribute_saveclosedirectory| image:: media/button_contribute_saveclosedirectory.png
.. |button_contribute_savedirectory| image:: media/button_contribute_savedirectory.png
