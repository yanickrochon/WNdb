
WNdb
====

A package to install [WordNet](http://wordnet.princeton.edu) database files for Node.js modules.

Used by [wordpos](http://github.com/moos/wordpos) project which is based on [natural](http://github.com/NaturalNode/natural) WordNet module.


Installation
------------

    npm install WNdb

or in your package.json dependencies:

```
  ...
  "dependencies": {
    "WNdb": "latest"
  },
  ...
```

Package requires 10 MB of disk space for the dictionaries. During post-installation, an extra 17 MB is required to download and extract the tar file archive.


Description
------------

This package does not contain the core DB files of WordNet 3.1. These files may be downloaded from [WordNet files](http://wordnet.princeton.edu/wordnet/download/current-version/).

Other "[standoff](http://wordnet.princeton.edu/wordnet/download/standoff/)" files may be added in the future.

The purpose of this package is to allow a convenient way to download WordNet files off-line rather than on-demand for node modules that require it.


Usage
-------
```js
var WNdb = require('WNdb');
console.log(WNdb);
// output:
{ version: '3.1',
  path: 'path/to/project/node_modules/WNdb/dict',
  files: [
    'data.adj',
    'data.adv',
    'data.noun',
    'data.verb',
    'index.adj',
    'index.adv',
    'index.noun',
    'index.sense',
    'index.verb'
  ]
}
```

Properties
------------

WNdb.path (string) -- the path to the installed WordNet DB files

WNdb.files (array) -- list of file names under the path

WNdb.version (string) -- version string of WordNet database file


Changes
---------

v3.0.x are pegged to WordNet 3.0 DB.

v3.0.0 -- includes the uncompressed (text) dict files.  On Windows systems, do a `git config core.autocrlf false` before _cloning_ so that CRLF isn't applied to data files.

v3.0.1 -- this includes the actual WordNet tar file, which is unpacked at install time.  There should be no CRLF issues.  Uses build-in 'zlib' package, therefore requires node >= 0.6.

v3.1.0 -- updated to WordNet 3.1 DB.

v3.1.1 -- fixed WNdb tar folder structure.

v3.1.2 -- removed tar file, and refactored post-installation process to actually download everything.


License
-------

WNdb package:
Copyright (c) 2012, 2014, mooster@42at.com
(The MIT License)

See LICENSE file for complete Princeton University WordNet(r) License.
