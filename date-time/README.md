# Data for testing date and time functions

Minimally valid mdEditor and mdJson records for use in testing date-time import, and date resolution selection features. The recordset contains minimally valid mdEditor records that record the `timePeriod.startDateTime` or the `citation.date` as a different precisions, ranging from full ISO data-time format (e.g. 2024-07-02T08:25:04-08:00) to only a year (2004).



## Files

### dateTest-mdeditor-20260204.json

A minimally valid mdEditor recordset, containing metadata records intended for use in testin the import of "Citation" and "Time Period" date-time values. Created using mdEditor version 1.3.1 (mdJSON schema v 2.10.2). The recordset contains seven metadata records titled:

  - "Citation date test"
  - "YYYY Time Period"
  - "YM Time Period"
  - "YMD Time Period"
  - "YMD-H:M:S +/- offset Time Period"
  - "YMD-H:M:SZ Time Period"
  - "NULL Time Period"

The "*Citation date test*" record contains several citation dates stored in a variety of allowable ISO date-time formats. Some values were manually edited to represent formats that the mdEditor might see on import, but does not write to JSON. formats:

- Year: 2000
- Month: 2001-02
- Day: 2002-03-04
- Time: 2003-04-05T11:25:30-9:00 (format stored by mdEditor)
- Time: 2003-04-05T11:25:30Z (manually edited JSON)
- Time: 2003-04-05T20:25:30 (manually edited JSON)
- Time: 20:15:30 (manually edited JSON)
- Time: null (manually edited JSON)

The remaining records each specify a "Time Period" "Start Date" precision, as indicated by the record name (e.g., "*YM Time Period*" records the date as `"startDateTime":"2024-05"`).

### dateTest-mdjson-20260204.json

The "*Citation date test*" metadata record from the above *dateTest-mdeditor-20260204.json* recordset, exported as mdJSON ("Export mdJSON" function) using mdEditor version 1.3.1 (mdJSON schema v 2.10.2).

## Deprecated files

Previous test files that should still be valid. The schema update from 2.9.5 to 2.10.2 should not affect the portions of the mdJSON that the files are intended to test.

### dateTest-mdeditor-20240702.json

A minimally valid mdEditor record set containing four metadata records labeled: "Date test YMD-HMS", "Date test YMD", "Date test YM", and "Date test YYYY". Each record uses a "TimePeriod StartDate" precision as indicated by the name (e.g., "Date test YM" records the date as `"startDateTime":"2024-05"`). The mdEditor-JSON file was created using mdEditor version [1.5.0-beta.28](https://github.com/adiwg/mdEditor/tree/65fe1ead) and schema version 2.9.5.

### dateTest-null-mdjson-20240702.json

A metadata record from the *date-testSet-mdeditor-20240702.json* recordset exported as mdJSON format ("Export mdJSON" function) and edited to store a null "TimePeriod StartDate" (`"startDateTime": ""`).The mdJSON file was created using mdEditor version [1.5.0-beta.28](https://github.com/adiwg/mdEditor/tree/65fe1ead) and schema version 2.9.5.
