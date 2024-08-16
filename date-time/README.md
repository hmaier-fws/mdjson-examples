# Data for testing date and time functions

Minimally valid mdEditor and mdJson records for use in testing date-time resolution features. The recordset contains minimally valid mdEditor records, each of which records the "TimePeriod StartDate" as a different precision, ranging from full ISO data-time format (e.g. 2024-07-02T08:25:04-08:00) to only a year (2004).

The record sets were initially created using mdEditor version [1.5.0-beta.28](https://github.com/adiwg/mdEditor/tree/65fe1ead) (dev.mdeditor.org) and schema version 2.9.5.

## Files

### dateTest-mdeditor-20240702.json

A minimally valid mdEditor record set containing four metadata records labeled: "Date test YMD-HMS", "Date test YMD", "Date test YM", and "Date test YYYY". Each record uses a "TimePeriod StartDate" precision as indicated by the name (e.g., "Date test YM" records the date as `"startDateTime":"2024-05"`).

### dateTest-null-mdjson-20240702.json

A metadata record from the *date-testSet-mdeditor-20240702.json* recordset exported as mdJSON format ("Export mdJSON" function) and edited to store a null "TimePeriod StartDate" (`"startDateTime": ""`).
