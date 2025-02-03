# Cape Hatteras test data

Test data based on:

> Spear, K.A., and Jones, W.R., 2017, Hurricane Sandy impacts on Cape Hatteras (North Carolina), 2012 National Wetlands Inventory Classification: U.S. Geological Survey data release, https://doi.org/10.5066/F78P5XP1.

## Files

### CapeHatteras_NWI_2012_original.xml

Original CSDGM metadata file "CapeHatteras_NWI_2012.xml". The source data was validated using the [USGS Geospatial Metadata Validation Service](https://www1.usgs.gov/mp/) (Version: mp 2.9.52) "standard" profile and found to be free of errors. Validation using the "Biological" profile resulted in two errors:
  - Error (line 31): Description_of_Geographic_Extent is required in Spatial_Domain
  - Error (line 84): Geospatial_Data_Presentation_Form is required in Citation_Information

### CapeHatteras_NWI_mdEditor-initial.json

Initial mdEditor-JSON export of the source XML. The file was imported into the mdEditor and exported without performing any edits. The mdEditor file contains errors.

  - record: should match pattern "^[0-9+()#. /ext-]+$"; /contact/4/phone/0/phoneNumber
  - record: should have required property 'resourceType'; /metadata/resourceInfo
  - contact: (ScienceBase) should match pattern "^[0-9+()#. /ext-]+$"; /phone/0/phoneNumber
  - dictionary: should have required property 'subject'
  - dictionary: should have required property 'responsibleParty'
  - dictionary: should have required property 'dataType'; /entity/0/attribute/0 (All attributes require data type)

### CapeHatteras_NWI_mdEditor-valid.json

The *CapeHatteras_NWI_mdEditor-initial.json* file edited to resolve errors and link the data dictionary to metadata record. Exported (Export All) as mdEditor-JSON.
  
### CapeHatteras_simplified_mdEditor.json

Simplified version of "CapeHatteras_NWI_mdJson-valid.json". The source file was simplified to contain a single metadata record, three contacts, and two data dictionaries. Additional changes include:

  - data dictionary includes one domain
  - reduce number of data dictionary attributes
  - reduce number of contacts
  - include second data dictionary that is not associated with metadata record
  - reduced number of thesauri and keywords associated with metadata record
  - simplified lineage

### CapeHatteras_translate-csdgm.xml

The *CapeHatteras_NWI_mdEditor-valid.json* translated to CSDGM ("Force Valid Output" = No, "Show Empty Tags" = No). The following translation errors were produced:

  - WARNING spatial domain geographic description is missing, FGDC writer context not provided
  - WARNING enumerated domain value source is missing, FGDC writer context is 27cf72e6-358b-4b88-9bd5-63ab47e9e672
  - WARNING enumerated domain value source is missing, FGDC writer context is 27cf72e6-358b-4b88-9bd5-63ab47e9e672
    
### CapeHatteras_translate-19110.xml

The *CapeHatteras_NWI_mdEditor-valid.json* translated to "ISO 19110" ("Force Valid Output" = No, "Show Empty Tags" = No). The following translation errors were produced:
  
  - WARNING feature catalogue version number is missing, ISO-19110 writer context not provided
  - WARNING feature catalogue version date is missing, ISO-19110 writer context not provided
  - WARNING entity common name is missing, ISO-19110 writer context is CapeHatteras_2012_PR
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided
  - WARNING citation date is missing, ISO-19110 writer context not provided

### CapeHatteras_NWI_mdJson-valid.json

The *CapeHatteras_NWI_mdEditor-valid.json* exported as mdJson.
  
  
