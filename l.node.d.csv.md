---
id: d8c64825-1b5a-455f-9d66-cf94cbff288d
title: Csv
desc: ''
updated: 1613847062276
created: 1613845272968
---

# CSV
- source: [^2]
<!-- -->

[^2]: https://csv.js.org/

```ts
// Import the package main module
const csv = require('csv')
// Use the module
csv
// Generate 20 records
.generate({
  delimiter: '|',
  length: 20
})
// Parse the records
.pipe(csv.parse({
  delimiter: '|'
}))
// Transform each value into uppercase
.pipe(csv.transform(function(record){
   return record.map(function(value){
     return value.toUpperCase()
   });
}))
// Convert the object into a stream
.pipe(csv.stringify({
  quoted: true
}))
// Print the CSV stream to stdout
.pipe(process.stdout)
```

# Fast-csv
- source: [^1]
<!-- -->

- [docs](https://c2fo.github.io/fast-csv/docs/introduction/getting-started)

[^1]: https://github.com/C2FO/fast-csv

## Quickstart
```sh
yarn add fast-csv 
```

## Examples

- write
```js
const csv = require("fast-csv");
const csvStream = csv.format({ headers: true });

csvStream.pipe(process.stdout).on('end', process.exit);

csvStream.write({ header1: 'row1-col1', header2: 'row1-col2' });
csvStream.write({ header1: 'row2-col1', header2: 'row2-col2' });
csvStream.write({ header1: 'row3-col1', header2: 'row3-col2' });
csvStream.write({ header1: 'row4-col1', header2: 'row4-col2' });
csvStream.write({ header1: 'row5-col1', header2: 'row5-col2' });
csvStream.end();
```

- read
```ts
fs.createReadStream(path.resolve(__dirname, 'assets', 'parse.csv'))
    .pipe(csv.parse({ headers: true }))
    .on('error', error => console.error(error))
    .on('data', row => console.log(row))
    .on('end', (rowCount: number) => console.log(`Parsed ${rowCount} rows`));
```

- read2

```js
import csv from "fast-csv"  
csv = require("fast-csv");

let path

out = [];
file = csv
    .fromPath(path, {headers: true})
    .on("data", function(data){ out.push(data) }).on("end", function(){ console.log("done"); });
```
