Introduction
============

About this guide
----------------

This guide sets out detailed instructions on the creation, publishing and maintenance of standard compliant metadata published on the
`spatialdata.gov.scot <https://www.spatialdata.gov.scot>`__ metadata portal. It has been written using Read The Docs, and can be navigated through 
by scrolling or clicking the sections in the navigation bar. The subsections can be explored by clicking the plus sign next to each 
section. A PDF copy of this guidance can be exported by clicking on **'v: latest'** at the bottom of the navigation panel, which will 
display the options to download the document in PDF and other formats.

The portal is based on the open source `GeoNetwork <https://geonetwork-opensource.org/>`__ platform. `Documentation <http://geonetwork-opensource.org/manuals/trunk/eng/users/index.html>`__ 
on the GeoNetwork framework is also linked to within some pages of spatialdata.gov.scot. While this is more generic guidance, it may be of use if 
you can't find your answer within this document.

About SpatialData.gov.scot
--------------------------

`SpatialData.gov.scot <https://www.spatialdata.gov.scot>`__ (previously referred to in short as the SSDI) 
provides a catalogue service where users can find, share, and reuse spatial data published by Scottish public sector organisations. Information 
available is not confined to just environmental data, but includes a variety of themes such as health, transport and administration. 
Datasets are discoverable by text, map and programmatically based searches, can be previewed on a map interface, and can be accessed 
directly via web service links recorded in the metadata.

In addition to the catalogue service, the portal also provides editing and validation tools necessary for data publishers registered 
on the site to create and maintain the metadata they publish. The portal employs the `UK GEMINI <https://www.agi.org.uk/agi-groups/standards-committee/uk-gemini>`__
metadata specification to ensure metadata is recorded in a consistent manner, enhancing the access to and reusability of the data.

Good quality metadata is key to understanding whether data is fit for purpose, has value, and is reliable - particularly if it is to 
inform policy decisions. `SpatialData.gov.scot <https://www.spatialdata.gov.scot>`__ fosters the development of good quality metadata, and underpins a range of websites and applications
that aim to interrogate and analyse available spatial data.

Any queries about the portal can be directed to: `SSDI.metadata@gov.scot <mailto:SSDI.metadata@gov.scot>`__

SpatialData.gov.scot and INSPIRE
--------------------------------

In order to effectively use spatial data in the delivery of national outcomes, spatial data managed by public sector bodies should be 
collected and shared in a manner that is open, minimises duplication and encourages re-use. A common way to achieve this is through the 
development of a Spatial Data Infrastructure (SDI) - which is essentially a framework of connected standards, spatial datasets, metadata 
and tools for visualisation and analysis that allow for spatial data to be used efficiently.  The main components of an SDI are:

* **Repositories** (to store the information)
* **Catalogue services** (to discover the information)
* **Web services** (to access the information)
* **Desktop GIS/Web Apps** (to interrogate the information)

The `EU Inspire Directive <https://inspire.ec.europa.eu/about-inspire>`__ aims to create a spatial data infrastructure for the European Union 
to enable the sharing of and access to environmental spatial information across Europe and assist in policy-making across boundaries. This EU 
SDI will be based on the infrastructures established and operated by the individual member states. The Directive came into force on 15 May 2007 
with full implementation expected by 2021. This directive has since been `transposed into Scottish law <http://www.legislation.gov.uk/ssi/2009/440/contents/made>`__) in 2009.

Scotland, in partnership with other administrations of the UK, works to fulfill its INSPIRE obligations by developing its own spatial data 
infrastructure compliant to the standards specified by the Directive. The Scottish SDI aims to apply the principles of INSPIRE, not just to 
environmental data, but to all spatial data maintained by the Scottish public sector.

`SpatialData.gov.scot <https://www.spatialdata.gov.scot>`__ fulfills the discovery/catalogue service component of the SDI and feeds into the UK public data publishing platform 
`Find open data (data.gov.uk) <http://data.gov.uk/>`__ (which in turn, feeds into the `EU INSPIRE Geoportal <http://inspire-geoportal.ec.europa.eu/discovery/>`__). Harvest of the metadata on `spatialdata.gov.scot <https://www.spatialdata.gov.scot>`__ 
to `data.gov.uk <http://data.gov.uk/>`__ is performed automatically on a daily basis, therefore record amendments should appear on `data.gov.uk <http://data.gov.uk/>`__ 
within 24 hours. Users should contact `SSDI.metadata@gov.scot <mailto:SSDI.metadata@gov.scot>`__ if they believe their records are not being 
harvested correctly.

Further information on INSPIRE, such as data specifications and implentation guidance, can be found on the `INSPIRE knowledge base <http://inspire.ec.europa.eu/>`__ pages.
Information relevant to Scotland is also circulated on `Knowledge Hub <https://knowledgehub.local.gov.uk/>`__, within the Scottish SDI Strategy 
Group, SDI/Inspire forum. 

Metadata Standards on SpatialData.gov.scot
------------------------------------------

Metadata on the portal is compliant to the `UK GEMINI <https://www.agi.org.uk/agi-groups/standards-committee/uk-gemini>`__ specification, which defines a core set of metadata elements for UK geospatial data, and is
compatible with the INSPIRE requirements for metadata. The current version of the standard is UK Gemini 2.3. Users should consult `Annex 2 <UserDoc_Chap9_Annex2.html#annex-2-upgrading-to-uk-gemini-2-3>`__ of this guidance to upgrade their existing metadata to Gemini 2.3 if the have not already done so.

The `MEDIN Discovery Metadata Standard <http://www.oceannet.org/marine_data_standards/medin_disc_stnd.html>`__ is a profile of UK Gemini specific to marine data. It can be thought of as a superset of Gemini, including 
the same core elements, but extending where necessary to include additional information relevant to the marine environment (e.g. marine keyword 
term lists). MEDIN format metadata uploaded to `spatialdata.gov.scot <https://www.spatialdata.gov.scot>`__ will retain these additional elements. It is recommended that Scottish orgnaisations 
maintaining marine datasets with MEDIN format metadata submit to both `spatialdata.gov.scot <https://www.spatialdata.gov.scot>`__ and the `MEDIN portal <http://portal.oceannet.org/portal/start.php>`__.
