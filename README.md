# xml-objects

Streaming wrapper around xml2js

Pipe fully formed bits of xml to _xml-objects_ to parse into javascript objects. Works great with [xml-nodes](https://github.com/timhudson/xml-nodes).

[![Build Status](https://img.shields.io/travis/timhudson/xml-objects.svg?style=flat-square)](https://travis-ci.org/timhudson/xml-objects)

[![NPM](https://nodei.co/npm/xml-objects.png?downloads=true&downloadRank=true)](https://nodei.co/npm/xml-objects/)

## Install

With [npm](https://npmjs.org/) do:

```
npm install xml-objects
```

## Example

```javascript
var request = require('request');
var xmlNodes = require('xml-nodes');
var xmlObjects = require('xml-objects');

request('http://news.yahoo.com/rss/entertainment')
  .pipe(xmlNodes('item'))
  .pipe(xmlObjects({explicitRoot: false, explicitArray: false, mergeAttrs: true}))
  .on('data', function(data) {
    console.log(data.title);
  });
```

## License

MIT
