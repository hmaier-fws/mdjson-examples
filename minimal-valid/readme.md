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
