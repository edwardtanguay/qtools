# qtools

This is a library of useful functions for JavaScript projects such as Node/Express APIs etc.

At the moment this library is most useful for providing one-line commands to:
- read SQLite database files
- read XML files
- read CSV files
- read Excel files
- read text files (e.g. import as array of lines)
- get all files in a directory
- parse a markdown file to HTML

A particular problem that has been solved is that all functions that receive a `pathAndFileName` to a file can be written in Linux path format (e.g. `src/data/settings.xml`) yet will work on Linux, Mac and Windows machines. 
```
const records = await qsql.getRecordsWithSql('SELECT * FROM employees');
const obj = qxml.getXmlFileAsObject('src/data/settings.xml');
const records = await qfil.getRecordsFromCsvFile('src/data/employees_semicolons.csv', ';');
const lines = qfil.getFileAsLines('src/data/jobs/job0001.md');
const files = qfil.getDirectoryPathAndFileNames('public/images');
```
## How to use

- download or clone repository
- copy the `qtools` folder to your project
- add the necessary dependences to your `package.json` file, e.g.:
```
    "csv-parse": "^5.2.0",
    "fast-xml-parser": "^4.0.8",
    "markdown-it": "^13.0.1",
    "sqlite3": "^5.0.8"
```
- include the qtool file you need like this:
```
import * as qsql from './qtools/qsql.js';
```

## Examples of this library being used

- Howto: [Create a data-driven, server-side Node/Express site (no framework, no templating engine)](https://edwardtanguay.netlify.app/howtos?id=566)
![grafik](https://user-images.githubusercontent.com/446574/178090452-16d7d27f-615d-4df0-8d35-77e0bdbed8c3.png)

## Join the project

- this is an open-source project run by Edward Tanguay
- you can fork or contribute to it if you like

## Open Tasks

- convert /dev/todo-read-excel to qtool function so that an excel file can be read with a one-liner, e.g. `qexc.getRecordsFromExcelFile('src/data/employees.xlsx')`
- implement unit testing with [Jest](https://jestjs.io) or [Vitest](https://vitest.dev)
- create a demo in `demo` with `demo/data` which is a demonstration of how to use the various tools in this library, e.g. as:
	- API
    -   server-side website (not EJS but text parsing which takes advantage of the tools in this library)	-
