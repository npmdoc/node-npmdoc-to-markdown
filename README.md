# api documentation for  [to-markdown (v3.0.4)](https://github.com/domchristie/to-markdown#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-to-markdown.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-to-markdown) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-to-markdown.svg)](https://travis-ci.org/npmdoc/node-npmdoc-to-markdown)
#### HTML-to-Markdown converter

[![NPM](https://nodei.co/npm/to-markdown.png?downloads=true)](https://www.npmjs.com/package/to-markdown)

[![apidoc](https://npmdoc.github.io/node-npmdoc-to-markdown/build/screenCapture.buildNpmdoc.browser.%2Fhome%2Ftravis%2Fbuild%2Fnpmdoc%2Fnode-npmdoc-to-markdown%2Ftmp%2Fbuild%2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-to-markdown/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-to-markdown/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-to-markdown/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Dom Christie"
    },
    "browser": {
        "jsdom": false
    },
    "bugs": {
        "url": "https://github.com/domchristie/to-markdown/issues"
    },
    "dependencies": {
        "collapse-whitespace": "1.1.2",
        "jsdom": "^9.0.0"
    },
    "description": "HTML-to-Markdown converter",
    "devDependencies": {
        "qunit": "^0.7.6",
        "saucie": "0.1.3",
        "standard": "^6.0.8",
        "testem": "^0.8.2",
        "watchify": "^2.5.0"
    },
    "directories": {},
    "dist": {
        "shasum": "3c7822f9286bc294ff37f9e0e5e23154c122ce69",
        "tarball": "https://registry.npmjs.org/to-markdown/-/to-markdown-3.0.4.tgz"
    },
    "engines": {
        "node": ">=4.0.0"
    },
    "gitHead": "0ffa85ad0194e541dddd2fd5d6c2065adb0d4d41",
    "homepage": "https://github.com/domchristie/to-markdown#readme",
    "keywords": [
        "markdown"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "domchristie",
            "email": "christiedom@gmail.com"
        }
    ],
    "name": "to-markdown",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/domchristie/to-markdown.git"
    },
    "scripts": {
        "start": "watchify -s toMarkdown -o dist/to-markdown.js index.js -v",
        "test": "standard index.js lib/**/*.js test/**/*.js && qunit -c ./index.js -t ./test/to-markdown-test.js ./test/gfm-test.js"
    },
    "url": "http://domchristie.github.com/to-markdown/",
    "version": "3.0.4"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module to-markdown](#apidoc.module.to-markdown)
1.  [function <span class="apidocSignatureSpan">to-markdown.</span>html_parser ()](#apidoc.element.to-markdown.html_parser)
1.  [function <span class="apidocSignatureSpan">to-markdown.</span>isBlock (node)](#apidoc.element.to-markdown.isBlock)
1.  [function <span class="apidocSignatureSpan">to-markdown.</span>isVoid (node)](#apidoc.element.to-markdown.isVoid)
1.  [function <span class="apidocSignatureSpan">to-markdown.</span>outer (node, content)](#apidoc.element.to-markdown.outer)
1.  object <span class="apidocSignatureSpan">to-markdown.</span>html_parser.prototype

#### [module to-markdown.html_parser](#apidoc.module.to-markdown.html_parser)
1.  [function <span class="apidocSignatureSpan">to-markdown.</span>html_parser ()](#apidoc.element.to-markdown.html_parser.html_parser)

#### [module to-markdown.html_parser.prototype](#apidoc.module.to-markdown.html_parser.prototype)
1.  [function <span class="apidocSignatureSpan">to-markdown.html_parser.prototype.</span>parseFromString (string)](#apidoc.element.to-markdown.html_parser.prototype.parseFromString)



# <a name="apidoc.module.to-markdown"></a>[module to-markdown](#apidoc.module.to-markdown)

#### <a name="apidoc.element.to-markdown.html_parser"></a>[function <span class="apidocSignatureSpan">to-markdown.</span>html_parser ()](#apidoc.element.to-markdown.html_parser)
- description and source-code
```javascript
html_parser = function () {}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.to-markdown.isBlock"></a>[function <span class="apidocSignatureSpan">to-markdown.</span>isBlock (node)](#apidoc.element.to-markdown.isBlock)
- description and source-code
```javascript
function isBlock(node) {
  return blocks.indexOf(node.nodeName.toLowerCase()) !== -1
}
```
- example usage
```shell
...
    }
    return '\n\n' + strings.join('\n') + '\n\n'
  }
},

{
  filter: function (node) {
    return this.isBlock(node)
  },
  replacement: function (content, node) {
    return '\n\n' + this.outer(node, content) + '\n\n'
  }
},

// Anything else!
...
```

#### <a name="apidoc.element.to-markdown.isVoid"></a>[function <span class="apidocSignatureSpan">to-markdown.</span>isVoid (node)](#apidoc.element.to-markdown.isVoid)
- description and source-code
```javascript
function isVoid(node) {
  return voids.indexOf(node.nodeName.toLowerCase()) !== -1
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.to-markdown.outer"></a>[function <span class="apidocSignatureSpan">to-markdown.</span>outer (node, content)](#apidoc.element.to-markdown.outer)
- description and source-code
```javascript
function outer(node, content) {
  return node.cloneNode(false).outerHTML.replace('><', '>' + content + '<')
}
```
- example usage
```shell
...
},

{
  filter: function (node) {
    return this.isBlock(node)
  },
  replacement: function (content, node) {
    return '\n\n' + this.outer(node, content) + '\n\n'
  }
},

// Anything else!
{
  filter: function () {
    return true
...
```



# <a name="apidoc.module.to-markdown.html_parser"></a>[module to-markdown.html_parser](#apidoc.module.to-markdown.html_parser)

#### <a name="apidoc.element.to-markdown.html_parser.html_parser"></a>[function <span class="apidocSignatureSpan">to-markdown.</span>html_parser ()](#apidoc.element.to-markdown.html_parser.html_parser)
- description and source-code
```javascript
html_parser = function () {}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.to-markdown.html_parser.prototype"></a>[module to-markdown.html_parser.prototype](#apidoc.module.to-markdown.html_parser.prototype)

#### <a name="apidoc.element.to-markdown.html_parser.prototype.parseFromString"></a>[function <span class="apidocSignatureSpan">to-markdown.html_parser.prototype.</span>parseFromString (string)](#apidoc.element.to-markdown.html_parser.prototype.parseFromString)
- description and source-code
```javascript
parseFromString = function (string) {
  return jsdom.jsdom(string, {
    features: {
      FetchExternalResources: [],
      ProcessExternalResources: false
    }
  })
}
```
- example usage
```shell
...
]

function isVoid (node) {
 return voids.indexOf(node.nodeName.toLowerCase()) !== -1
}

function htmlToDom (string) {
 var tree = new HtmlParser().parseFromString(string, 'text/html')
 collapse(tree.documentElement, isBlock)
 return tree
}

/*
* Flattens DOM tree into single array
*/
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
