# mdJSON files containing custom elements

mdJSON allows a user to extend the schema by including custom elements. Those elements will be ignored by the mdEditor, but should be be retained during import/export. The files in this directory are for use in testing mdEditor functions related to custom mdJson elements.

Versions of the mdEditor prior to v1.3.0 contained a bugs that caused:

  - excess data to be embedded within the mdEditor-Json `json: { }` object. Import of a mdJson file resulted in the contacts and data dictionaries being embedded within the record `json: { }` object as `contact[ ]` and `dataDictionary: [ ]` array elements. See [issue #682](https://github.com/adiwg/mdEditor/issues/682).
  - a `mdDictionary: [ ]` array to be included in a mdJson export. A `mdDictionary: [ ]` element is required to be present in the mdEditor-Json export, but it is not a valid element of the base mdJson schema. See [issue #770](https://github.com/adiwg/mdEditor/issues/770). 

The contact and dataDictionary array elements embedded withing the `json: { }` object are not used by the mdEditor. However, because schema extension is allowed, the elements are retained when a record is exported to the mdEditor-Json format ("Export All" or "Export Selected"). 

## mdeditor-strict-20250829 and mdjson-strict-20250829

Files formatted in compliance with the default the mdEditor-Json and mdJson (version 2.8.1) formats. The metadata record contains two data dictionaries, however, only "Data Dictionary 1" is associated with the metadata record.

## mdeditor-custom-20250829

The above mdEditor-Json file manually edited to add the following elements that are not part of the standard mdJSON schema:

  - `contact: [ ]` array
  - `dataDictionary: [ ]` array
  - `metadata.customFoo:["custom array within metadata object"]` object
  - `customBar:{"customBarKey":"custom bar value"}` array within metadata.metadataInfo object

## mdjson-custom-20250829.json

Above mdEditor-Json file exported as mdJson. The mdJson contains the non-standard elements described above and a `"mdDictionary": ["0e3b807f-0f1a-477f-a8a4-b2b8e0d04ea5"]` element that references a non-existant data dictionary.

