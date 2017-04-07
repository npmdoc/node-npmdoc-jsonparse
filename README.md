# api documentation for  [jsonparse (v1.3.0)](https://github.com/creationix/jsonparse#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-jsonparse.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-jsonparse) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-jsonparse.svg)](https://travis-ci.org/npmdoc/node-npmdoc-jsonparse)
#### This is a pure-js JSON streaming parser for node.js

[![NPM](https://nodei.co/npm/jsonparse.png?downloads=true)](https://www.npmjs.com/package/jsonparse)

[![apidoc](https://npmdoc.github.io/node-npmdoc-jsonparse/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-jsonparse_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-jsonparse/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-jsonparse/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-jsonparse/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Tim Caswell",
        "email": "tim@creationix.com"
    },
    "bugs": {
        "url": "http://github.com/creationix/jsonparse/issues"
    },
    "dependencies": {},
    "description": "This is a pure-js JSON streaming parser for node.js",
    "devDependencies": {
        "tap": "~0.3.3",
        "tape": "~0.1.1"
    },
    "directories": {},
    "dist": {
        "shasum": "85fc245b1d9259acc6941960b905adf64e7de0e8",
        "tarball": "https://registry.npmjs.org/jsonparse/-/jsonparse-1.3.0.tgz"
    },
    "engines": [
        "node >= 0.2.0"
    ],
    "gitHead": "69f02ca615aeeb4cbbe786ab42ce0592b44dc217",
    "homepage": "https://github.com/creationix/jsonparse#readme",
    "license": "MIT",
    "main": "jsonparse.js",
    "maintainers": [
        {
            "name": "creationix",
            "email": "tim@creationix.com"
        },
        {
            "name": "substack",
            "email": "mail@substack.net"
        }
    ],
    "name": "jsonparse",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+ssh://git@github.com/creationix/jsonparse.git"
    },
    "scripts": {
        "test": "tap test/*.js"
    },
    "tags": [
        "json",
        "stream"
    ],
    "version": "1.3.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module jsonparse](#apidoc.module.jsonparse)
1.  [function <span class="apidocSignatureSpan">jsonparse.</span>toknam (code)](#apidoc.element.jsonparse.toknam)
1.  object <span class="apidocSignatureSpan">jsonparse.</span>C



# <a name="apidoc.module.jsonparse"></a>[module jsonparse](#apidoc.module.jsonparse)

#### <a name="apidoc.element.jsonparse.toknam"></a>[function <span class="apidocSignatureSpan">jsonparse.</span>toknam (code)](#apidoc.element.jsonparse.toknam)
- description and source-code
```javascript
toknam = function (code) {
  var keys = Object.keys(C);
  for (var i = 0, l = keys.length; i < l; i++) {
    var key = keys[i];
    if (C[key] === code) { return key; }
  }
  return code && ("0x" + code.toString(16));
}
```
- example usage
```shell
...
return code && ("0x" + code.toString(16));
};

var proto = Parser.prototype;
proto.onError = function (err) { throw err; };
proto.charError = function (buffer, i) {
this.tState = STOP;
this.onError(new Error("Unexpected " + JSON.stringify(String.fromCharCode(buffer[i])) + " at position " + i + " in state " + Parser
.toknam(this.tState)));
};
proto.appendStringChar = function (char) {
if (this.stringBufferOffset >= STRING_BUFFER_SIZE) {
  this.string += this.stringBuffer.toString('utf8');
  this.stringBufferOffset = 0;
}
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
