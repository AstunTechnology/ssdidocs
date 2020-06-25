Annex 2: Upgrading existing metadata to UK Gemini 2.3
==========================================================================

`SpatialData.gov.scot <https://www.spatialdata.gov.scot>`__ has now implemented `UK GEMINI <https://www.agi.org.uk/agi-groups/standards-committee/uk-gemini>`__ 2.3. All new metadata created on the portal will conform to 2.3, and metadata publishers are strongly encouraged to upgrade their existing 2.2 records to 2.3 at their earliest convenience. This section provides guidance on how users can upgrade their metadata via a number of methods. For detail on what has changed from version 2.2 to 2.3, please see information provided by the `Association of Geographic Information (AGI) <https://www.agi.org.uk/agi-groups/standards-committee/uk-gemini/40-gemini/1055-uk-gemini-major-changes-since-1-0>`__.

Converting existing records
---------------------------

The root element should include a link to the gml 3.2 namespace and should not include xsi:schemalocation as this is handled internally::

   <gmd:MD_Metadata xmlns:gml="http://www.opengis.net/gml/3.2"
                 xmlns:gmi="http://www.isotc211.org/2005/gmi"
                 xmlns:gss="http://www.isotc211.org/2005/gss"
                 xmlns:gmd="http://www.isotc211.org/2005/gmd"
                 xmlns:gts="http://www.isotc211.org/2005/gts"
                 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                 xmlns:gmx="http://www.isotc211.org/2005/gmx"
                 xmlns:gsr="http://www.isotc211.org/2005/gsr"
                 xmlns:srv="http://www.isotc211.org/2005/srv"
                 xmlns:xlink="http://www.w3.org/1999/xlink"
                 xmlns:gco="http://www.isotc211.org/2005/gco">

Converting records on import
----------------------------

The correct metadata standard name and version should be included. Note these are case-sensitive::

Converting harvested records
----------------------------

Some organisations maintain their own spatial data portals and have their metadata harvested by SpatialData.gov.scot on a scheduled basis. 
