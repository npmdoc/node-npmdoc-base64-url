# api documentation for  [base64-url (v1.3.3)](https://github.com/joaquimserafim/base64-url)  [![npm package](https://img.shields.io/npm/v/npmdoc-base64-url.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-base64-url) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-base64-url.svg)](https://travis-ci.org/npmdoc/node-npmdoc-base64-url)
#### Base64 encode, decode, escape and unescape for URL applications

[![NPM](https://nodei.co/npm/base64-url.png?downloads=true)](https://www.npmjs.com/package/base64-url)

[![apidoc](https://npmdoc.github.io/node-npmdoc-base64-url/build/screenCapture.buildNpmdoc.browser.%2Fhome%2Ftravis%2Fbuild%2Fnpmdoc%2Fnode-npmdoc-base64-url%2Ftmp%2Fbuild%2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-base64-url/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-base64-url/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-base64-url/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "@joaquimserafim"
    },
    "bugs": {
        "url": "https://github.com/joaquimserafim/base64-url/issues"
    },
    "dependencies": {},
    "description": "Base64 encode, decode, escape and unescape for URL applications",
    "devDependencies": {
        "istanbul": "^0.3.5",
        "jscs": "^1.9.0",
        "jshint": "^2.5.11",
        "pre-commit": "^1.1.3",
        "tape": "^4.6.0"
    },
    "directories": {},
    "dist": {
        "shasum": "f8b6c537f09a4fc58c99cb86e0b0e9c61461a20f",
        "tarball": "https://registry.npmjs.org/base64-url/-/base64-url-1.3.3.tgz"
    },
    "files": [
        "LICENSE",
        "README.md",
        "index.js"
    ],
    "gitHead": "fb100b8397f24b1066016cf09369a7b2be4e1a32",
    "homepage": "https://github.com/joaquimserafim/base64-url",
    "keywords": [
        "base64",
        "base64url"
    ],
    "license": "ISC",
    "main": "index.js",
    "maintainers": [
        {
            "name": "quim",
            "email": "joaquim.serafim@gmail.com"
        }
    ],
    "name": "base64-url",
    "optionalDependencies": {},
    "pre-commit": [
        "lint",
        "style",
        "test",
        "coverage:check"
    ],
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/joaquimserafim/base64-url.git"
    },
    "scripts": {
        "coverage": "open coverage/lcov-report/index.html",
        "coverage:check": "istanbul check-coverage --statements 100 --functions 100 --lines 100 --branches 100",
        "lint": "jshint -c .jshintrc *.js",
        "style": "jscs -p google *.js",
        "test": "istanbul cover tape test.js"
    },
    "version": "1.3.3"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module base64-url](#apidoc.module.base64-url)
1.  [function <span class="apidocSignatureSpan">base64-url.</span>decode (str)](#apidoc.element.base64-url.decode)
1.  [function <span class="apidocSignatureSpan">base64-url.</span>encode (str)](#apidoc.element.base64-url.encode)
1.  [function <span class="apidocSignatureSpan">base64-url.</span>escape (str)](#apidoc.element.base64-url.escape)
1.  [function <span class="apidocSignatureSpan">base64-url.</span>unescape (str)](#apidoc.element.base64-url.unescape)



# <a name="apidoc.module.base64-url"></a>[module base64-url](#apidoc.module.base64-url)

#### <a name="apidoc.element.base64-url.decode"></a>[function <span class="apidocSignatureSpan">base64-url.</span>decode (str)](#apidoc.element.base64-url.decode)
- description and source-code
```javascript
function decode(str) {
  return new Buffer(this.unescape(str), 'base64').toString();
}
```
- example usage
```shell
...

'''js
var base64url = require('base64-url');

base64url.encode('Node.js is awesome.');
// returns Tm9kZS5qcyBpcyBhd2Vzb21lLg

base64url.decode('Tm9kZS5qcyBpcyBhd2Vzb21lLg');
// returns Node.js is awesome.

base64url.escape('This+is/goingto+escape==');
// returns This-is_goingto-escape

base64url.unescape('This-is_goingto-escape');
// returns This+is/goingto+escape==
...
```

#### <a name="apidoc.element.base64-url.encode"></a>[function <span class="apidocSignatureSpan">base64-url.</span>encode (str)](#apidoc.element.base64-url.encode)
- description and source-code
```javascript
function encode(str) {
  return this.escape(new Buffer(str).toString('base64'));
}
```
- example usage
```shell
...


## API

'''js
var base64url = require('base64-url');

base64url.encode('Node.js is awesome.');
// returns Tm9kZS5qcyBpcyBhd2Vzb21lLg

base64url.decode('Tm9kZS5qcyBpcyBhd2Vzb21lLg');
// returns Node.js is awesome.

base64url.escape('This+is/goingto+escape==');
// returns This-is_goingto-escape
...
```

#### <a name="apidoc.element.base64-url.escape"></a>[function <span class="apidocSignatureSpan">base64-url.</span>escape (str)](#apidoc.element.base64-url.escape)
- description and source-code
```javascript
function escape(str) {
  return str.replace(/\+/g, '-')
    .replace(/\//g, '_')
    .replace(/=/g, '');
}
```
- example usage
```shell
...

base64url.encode('Node.js is awesome.');
// returns Tm9kZS5qcyBpcyBhd2Vzb21lLg

base64url.decode('Tm9kZS5qcyBpcyBhd2Vzb21lLg');
// returns Node.js is awesome.

base64url.escape('This+is/goingto+escape==');
// returns This-is_goingto-escape

base64url.unescape('This-is_goingto-escape');
// returns This+is/goingto+escape==
'''
...
```

#### <a name="apidoc.element.base64-url.unescape"></a>[function <span class="apidocSignatureSpan">base64-url.</span>unescape (str)](#apidoc.element.base64-url.unescape)
- description and source-code
```javascript
function unescape(str) {
  return (str + '==='.slice((str.length + 3) % 4))
    .replace(/\-/g, '+')
    .replace(/_/g, '/');
}
```
- example usage
```shell
...

base64url.decode('Tm9kZS5qcyBpcyBhd2Vzb21lLg');
// returns Node.js is awesome.

base64url.escape('This+is/goingto+escape==');
// returns This-is_goingto-escape

base64url.unescape('This-is_goingto-escape');
// returns This+is/goingto+escape==
'''


## Development

**this project has been set up with a precommit that forces you to follow a code style, no jshint issues and 100% of code coverage
 before commit**
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
