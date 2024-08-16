# Example mdJSON files

This repository contains various file for use in testing various components of the mdToolkit.
The mdEditor exports two types of JSON files.

  - **mdJSON** created using the "Export mdJSON" command. This is a JSON file that conforms to the [mdJSON schema](https://github.com/adiwg/mdJson-schemas).
  - **mdEditor-JSON** created using the "Export All" and "Export Selected" commands. This is a format used by the mdEditor. The file contains the record data (as stringified mdJSON) and other elements used by the editor (e.g., user settings).

# Summary of contents

## /root

### mdeditor.json

Early example of a mdJSON file. The file was created in 2017 using mdJSON version 2.0.0.
This file may not import into newer vesion of the mdEditor, however, it is retained for
historical and testing purposes.

### minimalRecord-mdeditor-20231205.json

A minimal mdEditor record created by adding only the information required to allow a record to be saved (`Record title` and `resource type`).

### minimalRecord-mdJson-20231205.json

Contents of *minimalRecord-mdEditor-20231205.json* exported as mdJSON.


## /csdgm-biological

Examples of valid CSDGM records conforming to the Biological Profile. Contents contain the source CSDGM XML files and various mdEditor exports.


## /csdgm-geospatial

Examples of valid CSDGM records documenting geospatial data.


## /date-time

Examples of minimally valid mdEditor and mdJson records used to evaluate date and time functions.

## /minimal-valid

Examples of minimally valid mdEditor and mdJson records. A collection of minimally valid mdEditor record sets containing a single metadata record, two contact records, and two dictionary records. The recordsets were created using mdEditor version 1.2.1 (https://github.com/adiwg/mdEditor/tree/405d949e) and schema version 2.8.1.