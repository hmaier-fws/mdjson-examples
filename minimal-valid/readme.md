# Minimum valid mdEditor recordset

The initial source of the test data was:

> Spear, K.A., and Jones, W.R., 2017, Hurricane Sandy impacts on Cape Hatteras (North Carolina), 2012 National Wetlands Inventory Classification: U.S. Geological Survey data release, https://doi.org/10.5066/F78P5XP1.

The source metadata from the above (CapeHatteras_NWI_2012.xml) was modified for testing and demonstration purposes and no longer reflects the original data.

## Files

  - **min-valid-mdEditor-20240430.json** - A minimally valid mdEditor record set containing a single metadata record, two contact records, and two dictionary records. The dictionaries are not linked to the metadata record. The recordset was created using the "Export All" function of mdEditor version 1.2.1 (https://github.com/adiwg/mdEditor/tree/405d949e) and schema version 2.8.1.
  - **min-valid-mdJson-20240430.json** - The min-valid-mdEditor-20240430.json recordset exported to mdJSON format using the "Export mdJSON" function.
  - **min-valid-csdgm-20240430.xml** - The min-valid-mdEditor-20240430.json recordset translated to CSDGM format. Translation was performed using mdTranslator version 2.18.2; "Force Valid Output" = No; "Show Empty Tags" = No.
  - **min-valid-mdEditor-dict1-20240430**.json - The min-valid-mdEditor-20240430.json recordset edited to associate "Data Dictionary 1" with the metadata record. Data were exported using the "Export All" functionto (mdEditor-Json format).
  - **min-valid-mdJson-dict1-20240430.json** - The min-valid-mdEditor-dict1-20240430.json recordset exported to mdJSON format using the "Export mdJSON" function.

ISSUE:

mdJSON does not export the dictionaryId

Load example mdEditor file "min-valid-mdEditor-dict1-20240430.json". The metadata record in this file is associated with dictionary **"mdDictionary":["7e520389-7b0a-4552-ac3f-f5f1bc81c056"]**

Export metdata record using the "Export mdJSON" option.

Clear the browser and import the previously exported mdJSON file,

The resulting mdJSON file (mdJson-min-valid-linkedDict1.json) contains a `dataDictionary` element, however, the `dataDictionary` does not contain a `dictionaryId` element. On subsequent import, the dictionaries listed in the `mdDictionary` array can not be associated with the source metadata record.


      "mdDictionary": [
            "7e520389-7b0a-4552-ac3f-f5f1bc81c056"
        ],


The dictionary summary page displays the "Dictionary Id" as "Not Defined"
The dictionary is not associated with the metadata record.

The `dataDictionary` element of the mdEditor metadata record (`"type": "records"` object; line 6 of mdJson-import-mdeditor-export.json) contains the data dictionary information.
The imported data dictionaries is also present as an `attribute` element with `"type": "dictionaries"` object.

The `dataDictionary` array within the "records" object should remain empty.
The imported dataDictionary should only be stored as a "dictionaries" object.
The `dictionaryId` should be imported and exported with all data dictionaries.




editing the mdJson-import-mdeditor-export.json file to remove the `"type": "dictionaries"` object, but retaining the "records" object `dataDictionary` element, does not import the dictionary into the mdEditor.


Schems should reflect `mdDictionary` element as an array of dictionariy ID's associated with a metadata record.

mdEditor JSO should not include a contact array or a dictionary array in the metadata record.

