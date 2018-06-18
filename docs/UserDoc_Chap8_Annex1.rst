Annex 1: Requirements for metadata to be correctly identified as UK Gemini
==========================================================================

Records that are imported into the SSDI (rather than created within the portal using the available templates) must include the following XML elements 
to ensure that the record is correctly identified as UK Gemini upon import:

Root element
------------

The root element should include a link to the gml 3.2 namespace and should not include xsi:schemalocation as this is handled internally::

   <gmd:MD_Metadata xmlns:gmd="http://www.isotc211.org/2005/gmd"
                 xmlns:srv="http://www.isotc211.org/2005/srv"
                 xmlns:gts="http://www.isotc211.org/2005/gts"
                 xmlns:gco="http://www.isotc211.org/2005/gco"
                 xmlns:gml="http://www.opengis.net/gml/3.2"
                 xmlns:xlink="http://www.w3.org/1999/xlink"
                 xmlns:gmx="http://www.isotc211.org/2005/gmx"
                 xmlns:gsr="http://www.isotc211.org/2005/gsr"
                 xmlns:gss="http://www.isotc211.org/2005/gss"
                 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                 xmlns:geonet="http://www.fao.org/geonetwork">

Metadata standard name and version
----------------------------------

The correct metadata standard name and version should be included. Note these are case-sensitive::

   <gmd:metadataStandardName>
      <gco:CharacterString>UK GEMINI</gco:CharacterString>
   </gmd:metadataStandardName>
   <gmd:metadataStandardVersion>
      <gco:CharacterString>2.2</gco:CharacterString>
   </gmd:metadataStandardVersion>

