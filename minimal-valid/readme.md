# Minimum valid mdEditor recordset

Minimally valid mdEditor and mdJson records. A collection of minimally valid mdEditor record sets containing a single metadata record, two contact records, and two dictionary records. The record sets were created using mdEditor version 1.2.1 (https://github.com/adiwg/mdEditor/tree/405d949e) and schema version 2.8.1.

The initial source of the test data was:

> Spear, K.A., and Jones, W.R., 2017, Hurricane Sandy impacts on Cape Hatteras (North Carolina), 2012 National Wetlands Inventory Classification: U.S. Geological Survey data release, https://doi.org/10.5066/F78P5XP1.

The source metadata from the above (CapeHatteras_NWI_2012.xml) was modified for testing and demonstration purposes and ***no longer reflects the original data***.

## Files

### min-valid-mdEditor-20240430.json

A minimally valid mdEditor record set containing a single metadata record, two contact records, and two dictionary records. The dictionaries are not linked to the metadata record. The recordset was created using the "Export All" function of mdEditor version 1.2.1 (https://github.com/adiwg/mdEditor/tree/405d949e) and schema version 2.8.1.

### min-valid-mdJson-20240430.json
The metadata record from the *min-valid-mdEditor-20240430.json* recordset exported to mdJSON format using the "Export mdJSON" function.

### min-valid-csdgm-20240430.xml
The metadata record from the *min-valid-mdEditor-20240430.json* recordset translated to CSDGM format. Translation was performed using mdTranslator version 2.18.2; "Force Valid Output" = No; "Show Empty Tags" = No.

---

### min-valid-mdEditor-dict1-20240430.json
The *min-valid-mdEditor-20240430.json* recordset edited to associate "Data Dictionary 1" with the metadata record. Data were exported using the "Export All" function (mdEditor-Json format).

### min-valid-mdJson-dict1-20240430.json
The metadata record from the *min-valid-mdEditor-dict1-20240430.json* recordset exported to mdJSON format using the "Export mdJSON" function.

---

### mdJson-import-mdeditor-export.json
Example illustrating the behavior when importing mdJSON files into a mdEditor session. Import of mdJSON results in the incorporation of unused data within the `json:` element of the mdEditor-Json file. This recordest was created by:

  - importing the *min-valid-mdJson-dict1-20240430.json* file (mdJson format) into the mdEditor
  - then, immediately exporting the entire recordset, without modifying any records, using the "Export All" function (mdEditor-Json format)

The mdJSON import operation exhibits the following behavior:
  - the mdJSON "contact" and "dataDictionary" arrays are used to create individual contact (`"type": "contacts"`) and dictionary (`"type": "dictionaries"`) elements within the mdEditor-Json file
  - the mdJSON "contact" and "dataDictionary" arrays are embedded within the core metadata element (`"type": "records"`) as "contact" and "dataDictionary" arrays of the `json:` element.

### mdJson-import-mdeditor-export-noContDict.json
The *mdJson-import-mdeditor-export.json* file edited to delete the contact (`"type": "contacts"`) and dictionary (`"type": "dictionaries"`) elements from within the mdEditor-Json file. Importing the file **does not** result in the creation of contacts or dictionaries, even though the "Preview JSON" shows the presence of "contact" and "dataDictionary" arrays.

### mdJson-import-mdeditor-export-editJson.json
The *mdJson-import-mdeditor-export.json* file edited to delete the "contact" and "dataDictionary" arrays from within the `json:` element of the metadata record (`"type": "records"`). Importing the file does result in the creation of contacts or dictionaries, even though the "contact" and "dataDictionary" arrays were deleted from the `json:` element.
