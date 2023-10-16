# mikroBUS add-on board list CSV file format

The document is a comma-separated value text document where each line, separated by a
newline character, represents a single record. The first record is a header, describing
the fields in the following records. For more details, see the
[Wikipedia article](https://en.wikipedia.org/wiki/Comma-separated_values).

Most fields are just plain strings, but some may only include specific string values and
others may be JSON formatted strings to nest additional values. JSON was not utilized for
the entirty of the document for a couple of reasons. First, by keeping each board in a single
line, the version control history can be kept very simple, with a single entry being a single
line change. Second, it would be incredibly redundant and error-prone to need to name each
field in each record. By using CSV, it should be readily apparent if any given field is provided
and examples should be readily explorable in your favorite spreadsheet application.

The good news is that most add-on board records won't require JSON, but plenty tools make
it easy for those that do.

Read more at:
* [JSON](https://en.wikipedia.org/wiki/JSON)

## Fields

* Add-on board name: String description of official board name from the manufacturer
* Manufacturer: String description of manufacturer, approved by manufacturer, if possible
* Manufacturer part number: String of add-on board part number provided by manufacturer
* Copyright holder: String description of contributor of data on this record
