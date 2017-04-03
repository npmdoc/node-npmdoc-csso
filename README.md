# api documentation for  [csso (v3.0.1)](https://github.com/css/csso)  [![npm package](https://img.shields.io/npm/v/npmdoc-csso.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-csso) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-csso.svg)](https://travis-ci.org/npmdoc/node-npmdoc-csso)
#### CSSO (CSS Optimizer) is a CSS minifier with structural optimisations

[![NPM](https://nodei.co/npm/csso.png?downloads=true)](https://www.npmjs.com/package/csso)

[![apidoc](https://npmdoc.github.io/node-npmdoc-csso/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-csso_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-csso/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-csso/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-csso/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Sergey Kryzhanovsky",
        "email": "skryzhanovsky@ya.ru",
        "url": "https://github.com/afelix"
    },
    "bugs": {
        "url": "https://github.com/css/csso/issues"
    },
    "dependencies": {
        "css-tree": "1.0.0-alpha17"
    },
    "description": "CSSO (CSS Optimizer) is a CSS minifier with structural optimisations",
    "devDependencies": {
        "browserify": "^13.0.0",
        "coveralls": "^2.11.6",
        "eslint": "^2.2.0",
        "istanbul": "^0.4.2",
        "jscs": "~2.10.0",
        "mocha": "~2.4.2",
        "source-map": "^0.5.6",
        "uglify-js": "^2.6.1"
    },
    "directories": {},
    "dist": {
        "shasum": "1469af5ee2ec509addadd8777aa0e45acb6b2f58",
        "tarball": "https://registry.npmjs.org/csso/-/csso-3.0.1.tgz"
    },
    "engines": {
        "node": ">=0.10.0"
    },
    "eslintConfig": {
        "env": {
            "node": true,
            "mocha": true,
            "es6": true
        },
        "rules": {
            "no-duplicate-case": 2,
            "no-undef": 2,
            "no-unused-vars": [
                2,
                {
                    "vars": "all",
                    "args": "after-used"
                }
            ]
        }
    },
    "files": [
        "bin",
        "dist/csso-browser.js",
        "lib",
        "HISTORY.md",
        "LICENSE",
        "README.md"
    ],
    "gitHead": "f3415a2b641a46cdf0f7a4dbd2b1053122597186",
    "homepage": "https://github.com/css/csso",
    "keywords": [
        "css",
        "minifier",
        "minify",
        "compress",
        "optimisation"
    ],
    "license": "MIT",
    "main": "./lib/index",
    "maintainers": [
        {
            "name": "afelix",
            "email": "skryzhanovsky@gmail.com"
        },
        {
            "name": "lahmatiy",
            "email": "rdvornov@gmail.com"
        },
        {
            "name": "tadatuta",
            "email": "i@tadatuta.com"
        }
    ],
    "name": "csso",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/css/csso.git"
    },
    "scripts": {
        "browserify": "browserify --standalone csso lib/index.js | uglifyjs --compress --mangle -o dist/csso-browser.js",
        "codestyle": "jscs lib test && eslint lib test",
        "codestyle-and-test": "npm run codestyle && npm test",
        "coverage": "istanbul cover _mocha -- -R dot",
        "coveralls": "istanbul cover _mocha --report lcovonly -- -R dot && cat ./coverage/lcov.info | coveralls",
        "gh-pages": "git clone -b gh-pages https://github.com/css/csso.git .gh-pages && npm run browserify && cp dist/csso-browser.js .gh-pages/ && cd .gh-pages && git commit -am \"update\" && git push && cd .. && rm -rf .gh-pages",
        "hydrogen": "node --trace-hydrogen --trace-phase=Z --trace-deopt --code-comments --hydrogen-track-positions --redirect-code-traces --redirect-code-traces-to=code.asm --trace_hydrogen_file=code.cfg --print-opt-code bin/csso --stat -o /dev/null",
        "prepublish": "npm run browserify",
        "test": "mocha --reporter dot",
        "travis": "npm run codestyle-and-test && npm run coveralls"
    },
    "version": "3.0.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module csso](#apidoc.module.csso)
1.  [function <span class="apidocSignatureSpan">csso.</span>compress (ast, options)](#apidoc.element.csso.compress)
1.  [function <span class="apidocSignatureSpan">csso.</span>minify (source, options)](#apidoc.element.csso.minify)
1.  [function <span class="apidocSignatureSpan">csso.</span>minifyBlock (source, options)](#apidoc.element.csso.minifyBlock)
1.  [function <span class="apidocSignatureSpan">csso.</span>syntax.Lexer (config, syntax, structure)](#apidoc.element.csso.syntax.Lexer)
1.  [function <span class="apidocSignatureSpan">csso.</span>syntax.List ()](#apidoc.element.csso.syntax.List)
1.  [function <span class="apidocSignatureSpan">csso.</span>syntax.Tokenizer (source, startOffset, startLine, startColumn)](#apidoc.element.csso.syntax.Tokenizer)
1.  object <span class="apidocSignatureSpan">csso.</span>syntax
1.  object <span class="apidocSignatureSpan">csso.</span>syntax.Lexer.prototype
1.  object <span class="apidocSignatureSpan">csso.</span>syntax.List.prototype
1.  object <span class="apidocSignatureSpan">csso.</span>syntax.Tokenizer.prototype
1.  object <span class="apidocSignatureSpan">csso.</span>syntax.syntax
1.  object <span class="apidocSignatureSpan">csso.</span>usage
1.  string <span class="apidocSignatureSpan">csso.</span>version

#### [module csso.syntax](#apidoc.module.csso.syntax)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>Lexer (config, syntax, structure)](#apidoc.element.csso.syntax.Lexer)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>List ()](#apidoc.element.csso.syntax.List)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>Tokenizer (source, startOffset, startLine, startColumn)](#apidoc.element.csso.syntax.Tokenizer)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>clone (node)](#apidoc.element.csso.syntax.clone)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>createLexer (config)](#apidoc.element.csso.syntax.createLexer)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>createSyntax (config)](#apidoc.element.csso.syntax.createSyntax)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>fork (extension)](#apidoc.element.csso.syntax.fork)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>fromPlainObject (ast)](#apidoc.element.csso.syntax.fromPlainObject)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>keyword (keyword)](#apidoc.element.csso.syntax.keyword)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>parse ()](#apidoc.element.csso.syntax.parse)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>property (property)](#apidoc.element.csso.syntax.property)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>toPlainObject (ast)](#apidoc.element.csso.syntax.toPlainObject)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>translate (node)](#apidoc.element.csso.syntax.translate)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>translateMarkup (node, before, after)](#apidoc.element.csso.syntax.translateMarkup)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>translateWithSourceMap (node)](#apidoc.element.csso.syntax.translateWithSourceMap)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>walk (root, fn)](#apidoc.element.csso.syntax.walk)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>walkDeclarations (root, fn)](#apidoc.element.csso.syntax.walkDeclarations)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>walkRules (root, fn)](#apidoc.element.csso.syntax.walkRules)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>walkRulesRight (root, fn)](#apidoc.element.csso.syntax.walkRulesRight)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>walkUp (root, fn)](#apidoc.element.csso.syntax.walkUp)
1.  object <span class="apidocSignatureSpan">csso.</span>syntax
1.  object <span class="apidocSignatureSpan">csso.syntax.</span>lexer

#### [module csso.syntax.Lexer](#apidoc.module.csso.syntax.Lexer)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>Lexer (config, syntax, structure)](#apidoc.element.csso.syntax.Lexer.Lexer)

#### [module csso.syntax.Lexer.prototype](#apidoc.module.csso.syntax.Lexer.prototype)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>addProperty_ (name, syntax)](#apidoc.element.csso.syntax.Lexer.prototype.addProperty_)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>addType_ (name, syntax)](#apidoc.element.csso.syntax.Lexer.prototype.addType_)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>checkStructure (ast)](#apidoc.element.csso.syntax.Lexer.prototype.checkStructure)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>createDescriptor (syntax)](#apidoc.element.csso.syntax.Lexer.prototype.createDescriptor)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>dump (syntaxAsAst)](#apidoc.element.csso.syntax.Lexer.prototype.dump)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>getProperty (name)](#apidoc.element.csso.syntax.Lexer.prototype.getProperty)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>getType (name)](#apidoc.element.csso.syntax.Lexer.prototype.getType)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>matchProperty (propertyName, value)](#apidoc.element.csso.syntax.Lexer.prototype.matchProperty)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>matchType (typeName, value)](#apidoc.element.csso.syntax.Lexer.prototype.matchType)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>toString ()](#apidoc.element.csso.syntax.Lexer.prototype.toString)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>validate ()](#apidoc.element.csso.syntax.Lexer.prototype.validate)
1.  object <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>lastMatchError
1.  object <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>structure

#### [module csso.syntax.List](#apidoc.module.csso.syntax.List)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>List ()](#apidoc.element.csso.syntax.List.List)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.</span>createItem (data)](#apidoc.element.csso.syntax.List.createItem)

#### [module csso.syntax.List.prototype](#apidoc.module.csso.syntax.List.prototype)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>append (item)](#apidoc.element.csso.syntax.List.prototype.append)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>appendData (data)](#apidoc.element.csso.syntax.List.prototype.appendData)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>appendList (list)](#apidoc.element.csso.syntax.List.prototype.appendList)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>clear ()](#apidoc.element.csso.syntax.List.prototype.clear)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>copy ()](#apidoc.element.csso.syntax.List.prototype.copy)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>createItem (data)](#apidoc.element.csso.syntax.List.prototype.createItem)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>each (fn, context)](#apidoc.element.csso.syntax.List.prototype.each)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>eachRight (fn, context)](#apidoc.element.csso.syntax.List.prototype.eachRight)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>first ()](#apidoc.element.csso.syntax.List.prototype.first)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>fromArray (array)](#apidoc.element.csso.syntax.List.prototype.fromArray)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>getSize ()](#apidoc.element.csso.syntax.List.prototype.getSize)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>insert (item, before)](#apidoc.element.csso.syntax.List.prototype.insert)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>isEmpty ()](#apidoc.element.csso.syntax.List.prototype.isEmpty)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>last ()](#apidoc.element.csso.syntax.List.prototype.last)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>map (fn, context)](#apidoc.element.csso.syntax.List.prototype.map)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>nextUntil (start, fn, context)](#apidoc.element.csso.syntax.List.prototype.nextUntil)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>prevUntil (start, fn, context)](#apidoc.element.csso.syntax.List.prototype.prevUntil)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>remove (item)](#apidoc.element.csso.syntax.List.prototype.remove)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>some (fn, context)](#apidoc.element.csso.syntax.List.prototype.some)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>toArray ()](#apidoc.element.csso.syntax.List.prototype.toArray)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>toJSON ()](#apidoc.element.csso.syntax.List.prototype.toJSON)
1.  [function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>updateCursors (prevOld, prevNew, nextOld, nextNew)](#apidoc.element.csso.syntax.List.prototype.updateCursors)

#### [module csso.syntax.Tokenizer](#apidoc.module.csso.syntax.Tokenizer)
1.  [function <span class="apidocSignatureSpan">csso.syntax.</span>Tokenizer (source, startOffset, startLine, startColumn)](#apidoc.element.csso.syntax.Tokenizer.Tokenizer)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>CssSyntaxError (message, source, offset, line, column)](#apidoc.element.csso.syntax.Tokenizer.CssSyntaxError)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>cmpChar (testStr, offset, referenceCode)](#apidoc.element.csso.syntax.Tokenizer.cmpChar)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>cmpStr (testStr, start, end, referenceStr)](#apidoc.element.csso.syntax.Tokenizer.cmpStr)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>endsWith (testStr, referenceStr)](#apidoc.element.csso.syntax.Tokenizer.endsWith)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findCommentEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findCommentEnd)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findDecimalNumberEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findDecimalNumberEnd)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findEscaseEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findEscaseEnd)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findIdentifierEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findIdentifierEnd)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findLastNonSpaceLocation (scanner)](#apidoc.element.csso.syntax.Tokenizer.findLastNonSpaceLocation)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findNumberEnd (source, offset, allowFraction)](#apidoc.element.csso.syntax.Tokenizer.findNumberEnd)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findStringEnd (source, offset, quote)](#apidoc.element.csso.syntax.Tokenizer.findStringEnd)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findWhitespaceEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findWhitespaceEnd)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>firstCharOffset (source)](#apidoc.element.csso.syntax.Tokenizer.firstCharOffset)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>isHex (code)](#apidoc.element.csso.syntax.Tokenizer.isHex)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>isNewline (source, offset, code)](#apidoc.element.csso.syntax.Tokenizer.isNewline)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>isNumber (code)](#apidoc.element.csso.syntax.Tokenizer.isNumber)
1.  object <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>NAME
1.  object <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>PUNCTUATION
1.  object <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>SYMBOL_TYPE
1.  object <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>TYPE

#### [module csso.syntax.Tokenizer.prototype](#apidoc.module.csso.syntax.Tokenizer.prototype)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>consume (tokenType)](#apidoc.element.csso.syntax.Tokenizer.prototype.consume)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>consumeNonWS (tokenType)](#apidoc.element.csso.syntax.Tokenizer.prototype.consumeNonWS)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>eat (tokenType)](#apidoc.element.csso.syntax.Tokenizer.prototype.eat)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>eatNonWS (tokenType)](#apidoc.element.csso.syntax.Tokenizer.prototype.eatNonWS)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>error (message, offset)](#apidoc.element.csso.syntax.Tokenizer.prototype.error)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>expectIdentifier (name)](#apidoc.element.csso.syntax.Tokenizer.prototype.expectIdentifier)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>getLocation (offset, filename)](#apidoc.element.csso.syntax.Tokenizer.prototype.getLocation)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>getLocationRange (start, end, filename)](#apidoc.element.csso.syntax.Tokenizer.prototype.getLocationRange)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>getTokenValue ()](#apidoc.element.csso.syntax.Tokenizer.prototype.getTokenValue)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>getTypes ()](#apidoc.element.csso.syntax.Tokenizer.prototype.getTypes)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>lookupNonWSType (offset)](#apidoc.element.csso.syntax.Tokenizer.prototype.lookupNonWSType)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>lookupType (offset)](#apidoc.element.csso.syntax.Tokenizer.prototype.lookupType)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>lookupValue (offset, referenceStr)](#apidoc.element.csso.syntax.Tokenizer.prototype.lookupValue)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>next ()](#apidoc.element.csso.syntax.Tokenizer.prototype.next)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>setSource (source, startOffset, startLine, startColumn)](#apidoc.element.csso.syntax.Tokenizer.prototype.setSource)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>skip (tokenCount)](#apidoc.element.csso.syntax.Tokenizer.prototype.skip)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>skipSC ()](#apidoc.element.csso.syntax.Tokenizer.prototype.skipSC)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>skipWS ()](#apidoc.element.csso.syntax.Tokenizer.prototype.skipWS)
1.  [function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>substrToCursor (start)](#apidoc.element.csso.syntax.Tokenizer.prototype.substrToCursor)

#### [module csso.syntax.syntax](#apidoc.module.csso.syntax.syntax)
1.  [function <span class="apidocSignatureSpan">csso.syntax.syntax.</span>Lexer (config, syntax, structure)](#apidoc.element.csso.syntax.syntax.Lexer)
1.  object <span class="apidocSignatureSpan">csso.syntax.syntax.</span>grammar

#### [module csso.usage](#apidoc.module.csso.usage)
1.  [function <span class="apidocSignatureSpan">csso.usage.</span>buildIndex (data)](#apidoc.element.csso.usage.buildIndex)



# <a name="apidoc.module.csso"></a>[module csso](#apidoc.module.csso)

#### <a name="apidoc.element.csso.compress"></a>[function <span class="apidocSignatureSpan">csso.</span>compress (ast, options)](#apidoc.element.csso.compress)
- description and source-code
```javascript
function compress(ast, options) {
    ast = ast || { type: 'StyleSheet', loc: null, children: new List() };
    options = options || {};

    var logger = typeof options.logger === 'function' ? options.logger : function() {};
    var specialComments = getCommentsOption(options);
    var restructuring = getRestructureOption(options);
    var firstAtrulesAllowed = true;
    var usageData = false;
    var inputRules;
    var outputRules = new List();
    var chunk;
    var chunkNum = 1;
    var chunkRules;

    if (options.clone) {
        ast = clone(ast);
    }

    if (ast.type === 'StyleSheet') {
        inputRules = ast.children;
        ast.children = outputRules;
    } else {
        inputRules = wrapBlock(ast);
    }

    if (options.usage) {
        usageData = usageUtils.buildIndex(options.usage);
    }

    do {
        chunk = readChunk(inputRules, Boolean(specialComments));

        compressChunk(chunk.stylesheet, firstAtrulesAllowed, usageData, chunkNum++, logger);

        // structure optimisations
        if (restructuring) {
            restructureBlock(chunk.stylesheet, usageData, logger);
        }

        chunkRules = chunk.stylesheet.children;

        if (chunk.comment) {
            // add \n before comment if there is another content in outputRules
            if (!outputRules.isEmpty()) {
                outputRules.insert(List.createItem({
                    type: 'Raw',
                    value: '\n'
                }));
            }

            outputRules.insert(List.createItem(chunk.comment));

            // add \n after comment if chunk is not empty
            if (!chunkRules.isEmpty()) {
                outputRules.insert(List.createItem({
                    type: 'Raw',
                    value: '\n'
                }));
            }
        }

        if (firstAtrulesAllowed && !chunkRules.isEmpty()) {
            var lastRule = chunkRules.last();

            if (lastRule.type !== 'Atrule' ||
               (lastRule.name !== 'import' && lastRule.name !== 'charset')) {
                firstAtrulesAllowed = false;
            }
        }

        if (specialComments !== 'exclamation') {
            specialComments = false;
        }

        outputRules.appendList(chunkRules);
    } while (!inputRules.isEmpty());

    return {
        ast: ast
    };
}
```
- example usage
```shell
...
'''

CSSO is based on [CSSTree](https://github.com/csstree/csstree) to parse CSS into AST, AST traversal and to generate AST back to
CSS. All 'CSSTree' API is available behind 'syntax' field. You may minify CSS step by step:

'''js
var csso = require('csso');
var ast = csso.syntax.parse('.test { color: #ff0000; }');
var compressedAst = csso.compress(ast).ast;
var minifiedCss = csso.syntax.translate(compressedAst);

console.log(minifiedCss);
// .test{color:red}
'''

> Warning: CSSO uses early versions of CSSTree that still in active development. CSSO doesn't guarantee API behind 'syntax' field
 or AST format will not change in future releases of CSSO, since it's subject to change in CSSTree. Be carefull with CSSO updates
 if you use 'syntax' API until this warning removal.
...
```

#### <a name="apidoc.element.csso.minify"></a>[function <span class="apidocSignatureSpan">csso.</span>minify (source, options)](#apidoc.element.csso.minify)
- description and source-code
```javascript
function minifyStylesheet(source, options) {
    return minify('stylesheet', source, options);
}
```
- example usage
```shell
...
<!-- /MarkdownTOC -->

Basic usage:

'''js
var csso = require('csso');

var minifiedCss = csso.minify('.test { color: #ff0000; }').css;

console.log(minifiedCss);
// .test{color:red}
'''

CSSO is based on [CSSTree](https://github.com/csstree/csstree) to parse CSS into AST, AST traversal and to generate AST back to
CSS. All 'CSSTree' API is available behind 'syntax' field. You may minify CSS step by step:
...
```

#### <a name="apidoc.element.csso.minifyBlock"></a>[function <span class="apidocSignatureSpan">csso.</span>minifyBlock (source, options)](#apidoc.element.csso.minifyBlock)
- description and source-code
```javascript
function minifyBlock(source, options) {
    return minify('declarationList', source, options);
}
```
- example usage
```shell
...
- Other options are the same as for ['compress()'](#compressast-options) function.

### minifyBlock(source[, options])

The same as 'minify()' but for list of declarations. Usually it's a 'style' attribute value.

'''js
var result = csso.minifyBlock('color: rgba(255, 0, 0, 1); color: #ff0000');

console.log(result.css);
// > color:red
'''

### compress(ast[, options])
...
```

#### <a name="apidoc.element.csso.syntax.Lexer"></a>[function <span class="apidocSignatureSpan">csso.</span>syntax.Lexer (config, syntax, structure)](#apidoc.element.csso.syntax.Lexer)
- description and source-code
```javascript
syntax.Lexer = function (config, syntax, structure) {
    this.valueCommonSyntax = cssWideKeywords;
    this.syntax = syntax;
    this.generic = false;
    this.properties = {};
    this.types = {};
    this.structure = structure;

    if (config) {
        if (config.generic) {
            this.generic = true;
            for (var name in generic) {
                this.addType_(name, generic[name]);
            }
        }

        if (config.types) {
            for (var name in config.types) {
                this.addType_(name, config.types[name]);
            }
        }

        if (config.properties) {
            for (var name in config.properties) {
                this.addProperty_(name, config.properties[name]);
            }
        }
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List"></a>[function <span class="apidocSignatureSpan">csso.</span>syntax.List ()](#apidoc.element.csso.syntax.List)
- description and source-code
```javascript
syntax.List = function () {
    this.cursor = null;
    this.head = null;
    this.tail = null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer"></a>[function <span class="apidocSignatureSpan">csso.</span>syntax.Tokenizer (source, startOffset, startLine, startColumn)](#apidoc.element.csso.syntax.Tokenizer)
- description and source-code
```javascript
syntax.Tokenizer = function (source, startOffset, startLine, startColumn) {
    this.offsetAndType = null;
    this.lines = null;
    this.columns = null;

    this.setSource(source || '', startOffset, startLine, startColumn);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.csso.syntax"></a>[module csso.syntax](#apidoc.module.csso.syntax)

#### <a name="apidoc.element.csso.syntax.Lexer"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>Lexer (config, syntax, structure)](#apidoc.element.csso.syntax.Lexer)
- description and source-code
```javascript
Lexer = function (config, syntax, structure) {
    this.valueCommonSyntax = cssWideKeywords;
    this.syntax = syntax;
    this.generic = false;
    this.properties = {};
    this.types = {};
    this.structure = structure;

    if (config) {
        if (config.generic) {
            this.generic = true;
            for (var name in generic) {
                this.addType_(name, generic[name]);
            }
        }

        if (config.types) {
            for (var name in config.types) {
                this.addType_(name, config.types[name]);
            }
        }

        if (config.properties) {
            for (var name in config.properties) {
                this.addProperty_(name, config.properties[name]);
            }
        }
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>List ()](#apidoc.element.csso.syntax.List)
- description and source-code
```javascript
List = function () {
    this.cursor = null;
    this.head = null;
    this.tail = null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>Tokenizer (source, startOffset, startLine, startColumn)](#apidoc.element.csso.syntax.Tokenizer)
- description and source-code
```javascript
Tokenizer = function (source, startOffset, startLine, startColumn) {
    this.offsetAndType = null;
    this.lines = null;
    this.columns = null;

    this.setSource(source || '', startOffset, startLine, startColumn);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.clone"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>clone (node)](#apidoc.element.csso.syntax.clone)
- description and source-code
```javascript
function clone(node) {
    var result = {};

    for (var key in node) {
        var value = node[key];

        if (value) {
            if (Array.isArray(value)) {
                value = value.slice(0);
            } else if (value instanceof List) {
                value = new List().fromArray(value.map(clone));
            } else if (value.constructor === Object) {
                value = clone(value);
            }
        }

        result[key] = value;
    }

    return result;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.createLexer"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>createLexer (config)](#apidoc.element.csso.syntax.createLexer)
- description and source-code
```javascript
createLexer = function (config) {
    return new Lexer(config, syntax, lexer.structure);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.createSyntax"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>createSyntax (config)](#apidoc.element.csso.syntax.createSyntax)
- description and source-code
```javascript
createSyntax = function (config) {
    return createSyntax(mix({}, config));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.fork"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>fork (extension)](#apidoc.element.csso.syntax.fork)
- description and source-code
```javascript
fork = function (extension) {
    var base = mix({}, config); // copy of config
    return createSyntax(
        typeof extension === 'function'
            ? extension(base, assign)
            : mix(base, extension)
    );
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.fromPlainObject"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>fromPlainObject (ast)](#apidoc.element.csso.syntax.fromPlainObject)
- description and source-code
```javascript
fromPlainObject = function (ast) {
    walk(ast, function(node) {
        if (node.children && node.children instanceof List === false) {
            node.children = new List().fromArray(node.children);
        }
    });

    return ast;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.keyword"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>keyword (keyword)](#apidoc.element.csso.syntax.keyword)
- description and source-code
```javascript
function getKeywordInfo(keyword) {
    if (hasOwnProperty.call(keywords, keyword)) {
        return keywords[keyword];
    }

    var name = keyword.toLowerCase();

    if (hasOwnProperty.call(keywords, name)) {
        return keywords[keyword] = keywords[name];
    }

    var vendor = !isVariable(name, 0) ? getVendorPrefix(name, 0) : '';

    return keywords[keyword] = Object.freeze({
        vendor: vendor,
        prefix: vendor,
        name: name.substr(vendor.length)
    });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.parse"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>parse ()](#apidoc.element.csso.syntax.parse)
- description and source-code
```javascript
parse = function () { [native code] }
```
- example usage
```shell
...
// .test{color:red}
'''

CSSO is based on [CSSTree](https://github.com/csstree/csstree) to parse CSS into AST, AST traversal and to generate AST back to
CSS. All 'CSSTree' API is available behind 'syntax' field. You may minify CSS step by step:

'''js
var csso = require('csso');
var ast = csso.syntax.parse('.test { color: #ff0000; }');
var compressedAst = csso.compress(ast).ast;
var minifiedCss = csso.syntax.translate(compressedAst);

console.log(minifiedCss);
// .test{color:red}
'''
...
```

#### <a name="apidoc.element.csso.syntax.property"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>property (property)](#apidoc.element.csso.syntax.property)
- description and source-code
```javascript
function getPropertyInfo(property) {
    if (hasOwnProperty.call(properties, property)) {
        return properties[property];
    }

    var name = property;
    var hack = property[0];

    if (hack === '/' && property[1] === '/') {
        hack = '//';
    } else if (hack !== '_' &&
               hack !== '*' &&
               hack !== '$' &&
               hack !== '#' &&
               hack !== '+') {
        hack = '';
    }

    var variable = isVariable(name, hack.length);

    if (!variable) {
        name = name.toLowerCase();
        if (hasOwnProperty.call(properties, name)) {
            return properties[property] = properties[name];
        }
    }

    var vendor = !variable ? getVendorPrefix(name, hack.length) : '';

    return properties[property] = Object.freeze({
        hack: hack,
        vendor: vendor,
        prefix: hack + vendor,
        name: name.substr(hack.length + vendor.length),
        variable: variable
    });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.toPlainObject"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>toPlainObject (ast)](#apidoc.element.csso.syntax.toPlainObject)
- description and source-code
```javascript
toPlainObject = function (ast) {
    walkUp(ast, function(node) {
        if (node.children && node.children instanceof List) {
            node.children = node.children.toArray();
        }
    });

    return ast;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.translate"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>translate (node)](#apidoc.element.csso.syntax.translate)
- description and source-code
```javascript
translate = function (node) {
    return context.generate(node);
}
```
- example usage
```shell
...

CSSO is based on [CSSTree](https://github.com/csstree/csstree) to parse CSS into AST, AST traversal and to generate AST back to
CSS. All 'CSSTree' API is available behind 'syntax' field. You may minify CSS step by step:

'''js
var csso = require('csso');
var ast = csso.syntax.parse('.test { color: #ff0000; }');
var compressedAst = csso.compress(ast).ast;
var minifiedCss = csso.syntax.translate(compressedAst);

console.log(minifiedCss);
// .test{color:red}
'''

> Warning: CSSO uses early versions of CSSTree that still in active development. CSSO doesn't guarantee API behind 'syntax' field
 or AST format will not change in future releases of CSSO, since it's subject to change in CSSTree. Be carefull with CSSO updates
 if you use 'syntax' API until this warning removal.
...
```

#### <a name="apidoc.element.csso.syntax.translateMarkup"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>translateMarkup (node, before, after)](#apidoc.element.csso.syntax.translateMarkup)
- description and source-code
```javascript
translateMarkup = function (node, before, after) {
    function walk(node, buffer) {
        var value = node.value;

        before(node.node, buffer, value);

        if (typeof value === 'string') {
            buffer += value;
        } else {
            for (var i = 0; i < value.length; i++) {
                if (typeof value[i] === 'string') {
                    buffer += value[i];
                } else {
                    buffer = walk(value[i], buffer);
                }
            }
        }

        after(node.node, buffer, value);

        return buffer;
    }

    if (typeof before !== 'function') {
        before = function() {};
    }
    if (typeof after !== 'function') {
        after = function() {};
    }

    return walk(context.generate(node), '');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.translateWithSourceMap"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>translateWithSourceMap (node)](#apidoc.element.csso.syntax.translateWithSourceMap)
- description and source-code
```javascript
translateWithSourceMap = function (node) {
    return sourceMapGenerator(markupGenerator, node);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.walk"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>walk (root, fn)](#apidoc.element.csso.syntax.walk)
- description and source-code
```javascript
walk = function (root, fn) {
    function walk(node, item, list) {
        fn.call(context, node, item, list);
        if (walkers.hasOwnProperty(node.type)) {
            walkers[node.type](node, context, walk);
        }
    }

    var context = createContext(root, fn);

    walk(root);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.walkDeclarations"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>walkDeclarations (root, fn)](#apidoc.element.csso.syntax.walkDeclarations)
- description and source-code
```javascript
walkDeclarations = function (root, fn) {
    walkDeclarations.call(createContext(root, fn), root);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.walkRules"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>walkRules (root, fn)](#apidoc.element.csso.syntax.walkRules)
- description and source-code
```javascript
walkRules = function (root, fn) {
    walkRules.call(createContext(root, fn), root);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.walkRulesRight"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>walkRulesRight (root, fn)](#apidoc.element.csso.syntax.walkRulesRight)
- description and source-code
```javascript
walkRulesRight = function (root, fn) {
    walkRulesRight.call(createContext(root, fn), root);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.walkUp"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>walkUp (root, fn)](#apidoc.element.csso.syntax.walkUp)
- description and source-code
```javascript
walkUp = function (root, fn) {
    function walk(node, item, list) {
        if (walkers.hasOwnProperty(node.type)) {
            walkers[node.type](node, context, walk);
        }
        fn.call(context, node, item, list);
    }

    var context = createContext(root, fn);

    walk(root);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.csso.syntax.Lexer"></a>[module csso.syntax.Lexer](#apidoc.module.csso.syntax.Lexer)

#### <a name="apidoc.element.csso.syntax.Lexer.Lexer"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>Lexer (config, syntax, structure)](#apidoc.element.csso.syntax.Lexer.Lexer)
- description and source-code
```javascript
Lexer = function (config, syntax, structure) {
    this.valueCommonSyntax = cssWideKeywords;
    this.syntax = syntax;
    this.generic = false;
    this.properties = {};
    this.types = {};
    this.structure = structure;

    if (config) {
        if (config.generic) {
            this.generic = true;
            for (var name in generic) {
                this.addType_(name, generic[name]);
            }
        }

        if (config.types) {
            for (var name in config.types) {
                this.addType_(name, config.types[name]);
            }
        }

        if (config.properties) {
            for (var name in config.properties) {
                this.addProperty_(name, config.properties[name]);
            }
        }
    }
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.csso.syntax.Lexer.prototype"></a>[module csso.syntax.Lexer.prototype](#apidoc.module.csso.syntax.Lexer.prototype)

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.addProperty_"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>addProperty_ (name, syntax)](#apidoc.element.csso.syntax.Lexer.prototype.addProperty_)
- description and source-code
```javascript
addProperty_ = function (name, syntax) {
    this.properties[name] = this.createDescriptor(syntax);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.addType_"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>addType_ (name, syntax)](#apidoc.element.csso.syntax.Lexer.prototype.addType_)
- description and source-code
```javascript
addType_ = function (name, syntax) {
    this.types[name] = this.createDescriptor(syntax);

    if (syntax === generic.expression) {
        this.valueCommonSyntax = cssWideKeywordsWithExpression;
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.checkStructure"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>checkStructure (ast)](#apidoc.element.csso.syntax.Lexer.prototype.checkStructure)
- description and source-code
```javascript
checkStructure = function (ast) {
    var structure = this.structure;
    var warns = [];

    this.syntax.walk(ast, function(node) {
        if (structure.hasOwnProperty(node.type)) {
            structure[node.type].check(node, warns.push.bind(warns));
        } else {
            throw new Error('Unknown node type: ' + node.type);
        }
    });

    return warns.length ? warns : false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.createDescriptor"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>createDescriptor (syntax)](#apidoc.element.csso.syntax.Lexer.prototype.createDescriptor)
- description and source-code
```javascript
createDescriptor = function (syntax) {
    var self = this;
    var descriptor = {
        syntax: null,
        match: null
    };

    if (typeof syntax === 'function') {
        descriptor.match = function(node) {
            if (node && syntax(node)) {
                return {
                    badNode: null,
                    lastNode: null,
                    next: node.next,
                    match: [node.data]
                };
            }

            return null;
        };
    } else {
        if (typeof syntax === 'string') {
            Object.defineProperty(descriptor, 'syntax', {
                get: function() {
                    Object.defineProperty(descriptor, 'syntax', {
                        value: parse(syntax)
                    });

                    return descriptor.syntax;
                }
            });
        } else {
            descriptor.syntax = syntax;
        }

        descriptor.match = function(ast) {
            return match(self, descriptor.syntax, ast);
        };
    }

    return descriptor;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.dump"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>dump (syntaxAsAst)](#apidoc.element.csso.syntax.Lexer.prototype.dump)
- description and source-code
```javascript
dump = function (syntaxAsAst) {
    return {
        generic: this.generic,
        types: dumpMapSyntax(this.types, syntaxAsAst),
        properties: dumpMapSyntax(this.properties, syntaxAsAst)
    };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.getProperty"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>getProperty (name)](#apidoc.element.csso.syntax.Lexer.prototype.getProperty)
- description and source-code
```javascript
getProperty = function (name) {
    return this.properties.hasOwnProperty(name) ? this.properties[name] : null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.getType"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>getType (name)](#apidoc.element.csso.syntax.Lexer.prototype.getType)
- description and source-code
```javascript
getType = function (name) {
    return this.types.hasOwnProperty(name) ? this.types[name] : null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.matchProperty"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>matchProperty (propertyName, value)](#apidoc.element.csso.syntax.Lexer.prototype.matchProperty)
- description and source-code
```javascript
matchProperty = function (propertyName, value) {
    var property = names.property(propertyName);

    // don't match syntax for a custom property
    if (property.variable) {
        return {
            type: 'NoMatch',
            comment: 'Lexer matching doesn\'t applicable for custom properties'
        };
    }

    var propertySyntax = property.vendor
        ? this.getProperty(property.vendor + property.name) || this.getProperty(property.name)
        : this.getProperty(property.name);

    if (!propertySyntax) {
        this.lastMatchError = new Error('Unknown property: ' + propertyName);
        return null;
    }

    return matchSyntax(this, propertySyntax, value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.matchType"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>matchType (typeName, value)](#apidoc.element.csso.syntax.Lexer.prototype.matchType)
- description and source-code
```javascript
matchType = function (typeName, value) {
    var typeSyntax = this.getType(typeName);

    if (!typeSyntax) {
        this.lastMatchError = new Error('Unknown type: ' + typeName);
        return null;
    }

    return matchSyntax(this, typeSyntax, value);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.toString"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>toString ()](#apidoc.element.csso.syntax.Lexer.prototype.toString)
- description and source-code
```javascript
toString = function () {
    return JSON.stringify(this.dump());
}
```
- example usage
```shell
...
  filename: 'path/to/my.css', // will be added to source map as reference to source file
  sourceMap: true             // generate source map
});

console.log(result);
// { css: '...minified...', map: SourceMapGenerator {} }

console.log(result.map.toString());
// '{ .. source map content .. }'
'''

Example of generating source map with respect of source map from input CSS:

'''js
var require('source-map');
...
```

#### <a name="apidoc.element.csso.syntax.Lexer.prototype.validate"></a>[function <span class="apidocSignatureSpan">csso.syntax.Lexer.prototype.</span>validate ()](#apidoc.element.csso.syntax.Lexer.prototype.validate)
- description and source-code
```javascript
validate = function () {
    function validate(syntax, name, broken, descriptor) {
        if (broken.hasOwnProperty(name)) {
            return broken[name];
        }

        broken[name] = false;
        if (descriptor.syntax !== null) {
            walk(descriptor.syntax, function(node) {
                if (node.type !== 'Type' && node.type !== 'Property') {
                    return;
                }

                var map = node.type === 'Type' ? syntax.types : syntax.properties;
                var brokenMap = node.type === 'Type' ? brokenTypes : brokenProperties;

                if (!map.hasOwnProperty(node.name) || validate(syntax, node.name, brokenMap, map[node.name])) {
                    broken[name] = true;
                }
            }, this);
        }
    }

    var brokenTypes = {};
    var brokenProperties = {};

    for (var key in this.types) {
        validate(this, key, brokenTypes, this.types[key]);
    }

    for (var key in this.properties) {
        validate(this, key, brokenProperties, this.properties[key]);
    }

    brokenTypes = Object.keys(brokenTypes).filter(function(name) {
        return brokenTypes[name];
    });
    brokenProperties = Object.keys(brokenProperties).filter(function(name) {
        return brokenProperties[name];
    });

    if (brokenTypes.length || brokenProperties.length) {
        return {
            types: brokenTypes,
            properties: brokenProperties
        };
    }

    return null;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.csso.syntax.List"></a>[module csso.syntax.List](#apidoc.module.csso.syntax.List)

#### <a name="apidoc.element.csso.syntax.List.List"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>List ()](#apidoc.element.csso.syntax.List.List)
- description and source-code
```javascript
List = function () {
    this.cursor = null;
    this.head = null;
    this.tail = null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.createItem"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.</span>createItem (data)](#apidoc.element.csso.syntax.List.createItem)
- description and source-code
```javascript
function createItem(data) {
    return {
        prev: null,
        next: null,
        data: data
    };
}
```
- example usage
```shell
...
        }

        chunkRules = chunk.stylesheet.children;

        if (chunk.comment) {
// add \n before comment if there is another content in outputRules
if (!outputRules.isEmpty()) {
    outputRules.insert(List.createItem({
        type: 'Raw',
        value: '\n'
    }));
}

outputRules.insert(List.createItem(chunk.comment));
...
```



# <a name="apidoc.module.csso.syntax.List.prototype"></a>[module csso.syntax.List.prototype](#apidoc.module.csso.syntax.List.prototype)

#### <a name="apidoc.element.csso.syntax.List.prototype.append"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>append (item)](#apidoc.element.csso.syntax.List.prototype.append)
- description and source-code
```javascript
append = function (item) {
    // tail
    //      ^
    //     item
    this.updateCursors(this.tail, item, null, item);

    // insert to end of the list
    if (this.tail !== null) {
        // if list has a tail, then it also has a head, but head doesn't change

        // last item -> new item
        this.tail.next = item;

        // last item <- new item
        item.prev = this.tail;
    } else {
        // if list has no a tail, then it also has no a head
        // in this case points head to new item
        this.head = item;
    }

    // tail always start point to new item
    this.tail = item;

    return this;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.appendData"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>appendData (data)](#apidoc.element.csso.syntax.List.prototype.appendData)
- description and source-code
```javascript
appendData = function (data) {
    return this.append(createItem(data));
}
```
- example usage
```shell
...
function getRestructureOption(options) {
return 'restructure' in options ? options.restructure :
       'restructuring' in options ? options.restructuring :
       true;
}

function wrapBlock(block) {
return new List().appendData({
    type: 'Rule',
    selector: {
        type: 'SelectorList',
        children: new List().appendData({
            type: 'Selector',
            children: new List().appendData({
                type: 'Identifier',
...
```

#### <a name="apidoc.element.csso.syntax.List.prototype.appendList"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>appendList (list)](#apidoc.element.csso.syntax.List.prototype.appendList)
- description and source-code
```javascript
appendList = function (list) {
    // ignore empty lists
    if (list.head === null) {
        return;
    }

    this.updateCursors(this.tail, list.tail, null, list.head);

    // insert to end of the list
    if (this.tail !== null) {
        // if destination list has a tail, then it also has a head,
        // but head doesn't change

        // dest tail -> source head
        this.tail.next = list.head;

        // dest tail <- source head
        list.head.prev = this.tail;
    } else {
        // if list has no a tail, then it also has no a head
        // in this case points head to new item
        this.head = list.head;
    }

    // tail always start point to new item
    this.tail = list.tail;

    list.head = null;
    list.tail = null;
}
```
- example usage
```shell
...
            }
        }

        if (specialComments !== 'exclamation') {
            specialComments = false;
        }

        outputRules.appendList(chunkRules);
    } while (!inputRules.isEmpty());

    return {
        ast: ast
    };
};
...
```

#### <a name="apidoc.element.csso.syntax.List.prototype.clear"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>clear ()](#apidoc.element.csso.syntax.List.prototype.clear)
- description and source-code
```javascript
clear = function () {
    this.head = null;
    this.tail = null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.copy"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>copy ()](#apidoc.element.csso.syntax.List.prototype.copy)
- description and source-code
```javascript
copy = function () {
    var result = new List();
    var cursor = this.head;

    while (cursor !== null) {
        result.insert(createItem(cursor.data));
        cursor = cursor.next;
    }

    return result;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.createItem"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>createItem (data)](#apidoc.element.csso.syntax.List.prototype.createItem)
- description and source-code
```javascript
function createItem(data) {
    return {
        prev: null,
        next: null,
        data: data
    };
}
```
- example usage
```shell
...
        }

        chunkRules = chunk.stylesheet.children;

        if (chunk.comment) {
// add \n before comment if there is another content in outputRules
if (!outputRules.isEmpty()) {
    outputRules.insert(List.createItem({
        type: 'Raw',
        value: '\n'
    }));
}

outputRules.insert(List.createItem(chunk.comment));
...
```

#### <a name="apidoc.element.csso.syntax.List.prototype.each"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>each (fn, context)](#apidoc.element.csso.syntax.List.prototype.each)
- description and source-code
```javascript
each = function (fn, context) {
    var item;

    if (context === undefined) {
        context = this;
    }

    // push cursor
    var cursor = allocateCursor(this, null, this.head);

    while (cursor.next !== null) {
        item = cursor.next;
        cursor.next = item.next;

        fn.call(context, item.data, item, this);
    }

    // pop cursor
    releaseCursor(this);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.eachRight"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>eachRight (fn, context)](#apidoc.element.csso.syntax.List.prototype.eachRight)
- description and source-code
```javascript
eachRight = function (fn, context) {
    var item;

    if (context === undefined) {
        context = this;
    }

    // push cursor
    var cursor = allocateCursor(this, this.tail, null);

    while (cursor.prev !== null) {
        item = cursor.prev;
        cursor.prev = item.prev;

        fn.call(context, item.data, item, this);
    }

    // pop cursor
    releaseCursor(this);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.first"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>first ()](#apidoc.element.csso.syntax.List.prototype.first)
- description and source-code
```javascript
first = function () {
    return this.head && this.head.data;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.fromArray"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>fromArray (array)](#apidoc.element.csso.syntax.List.prototype.fromArray)
- description and source-code
```javascript
fromArray = function (array) {
    var cursor = null;

    this.head = null;

    for (var i = 0; i < array.length; i++) {
        var item = createItem(array[i]);

        if (cursor !== null) {
            cursor.next = item;
        } else {
            this.head = item;
        }

        item.prev = cursor;
        cursor = item;
    }

    this.tail = cursor;

    return this;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.getSize"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>getSize ()](#apidoc.element.csso.syntax.List.prototype.getSize)
- description and source-code
```javascript
getSize = function () {
    var size = 0;
    var cursor = this.head;

    while (cursor) {
        size++;
        cursor = cursor.next;
    }

    return size;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.insert"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>insert (item, before)](#apidoc.element.csso.syntax.List.prototype.insert)
- description and source-code
```javascript
insert = function (item, before) {
    if (before !== undefined && before !== null) {
        // prev   before
        //      ^
        //     item
        this.updateCursors(before.prev, item, before, item);

        if (before.prev === null) {
            // insert to the beginning of list
            if (this.head !== before) {
                throw new Error('before doesn\'t below to list');
            }

            // since head points to before therefore list doesn't empty
            // no need to check tail
            this.head = item;
            before.prev = item;
            item.next = before;

            this.updateCursors(null, item);
        } else {

            // insert between two items
            before.prev.next = item;
            item.prev = before.prev;

            before.prev = item;
            item.next = before;
        }
    } else {
        this.append(item);
    }
}
```
- example usage
```shell
...
        return;
    }

    if (node.type !== 'WhiteSpace') {
        nonSpaceTokenInBuffer = true;
    }

    buffer.insert(list.remove(item));
});

return {
    comment: protectedComment,
    stylesheet: {
        type: 'StyleSheet',
        loc: null,
...
```

#### <a name="apidoc.element.csso.syntax.List.prototype.isEmpty"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>isEmpty ()](#apidoc.element.csso.syntax.List.prototype.isEmpty)
- description and source-code
```javascript
isEmpty = function () {
    return this.head === null;
}
```
- example usage
```shell
...
restructureBlock(chunk.stylesheet, usageData, logger);
        }

        chunkRules = chunk.stylesheet.children;

        if (chunk.comment) {
// add \n before comment if there is another content in outputRules
if (!outputRules.isEmpty()) {
    outputRules.insert(List.createItem({
        type: 'Raw',
        value: '\n'
    }));
}

outputRules.insert(List.createItem(chunk.comment));
...
```

#### <a name="apidoc.element.csso.syntax.List.prototype.last"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>last ()](#apidoc.element.csso.syntax.List.prototype.last)
- description and source-code
```javascript
last = function () {
    return this.tail && this.tail.data;
}
```
- example usage
```shell
...
            type: 'Raw',
            value: '\n'
        }));
    }
}

if (firstAtrulesAllowed && !chunkRules.isEmpty()) {
    var lastRule = chunkRules.last();

    if (lastRule.type !== 'Atrule' ||
       (lastRule.name !== 'import' && lastRule.name !== 'charset')) {
        firstAtrulesAllowed = false;
    }
}
...
```

#### <a name="apidoc.element.csso.syntax.List.prototype.map"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>map (fn, context)](#apidoc.element.csso.syntax.List.prototype.map)
- description and source-code
```javascript
map = function (fn, context) {
    var result = [];
    var cursor = this.head;

    if (context === undefined) {
        context = this;
    }

    while (cursor !== null) {
        result.push(fn.call(context, cursor.data, cursor, this));
        cursor = cursor.next;
    }

    return result;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.nextUntil"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>nextUntil (start, fn, context)](#apidoc.element.csso.syntax.List.prototype.nextUntil)
- description and source-code
```javascript
nextUntil = function (start, fn, context) {
    if (start === null) {
        return;
    }

    var item;

    if (context === undefined) {
        context = this;
    }

    // push cursor
    var cursor = allocateCursor(this, null, start);

    while (cursor.next !== null) {
        item = cursor.next;
        cursor.next = item.next;

        if (fn.call(context, item.data, item, this)) {
            break;
        }
    }

    // pop cursor
    releaseCursor(this);
}
```
- example usage
```shell
...
var walkRules = require('css-tree').walkRules;

function readChunk(children, specialComments) {
    var buffer = new List();
    var nonSpaceTokenInBuffer = false;
    var protectedComment;

    children.nextUntil(children.head, function(node, item, list) {
        if (node.type === 'Comment') {
if (!specialComments || node.value.charAt(0) !== '!') {
    list.remove(item);
    return;
}

if (nonSpaceTokenInBuffer || protectedComment) {
...
```

#### <a name="apidoc.element.csso.syntax.List.prototype.prevUntil"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>prevUntil (start, fn, context)](#apidoc.element.csso.syntax.List.prototype.prevUntil)
- description and source-code
```javascript
prevUntil = function (start, fn, context) {
    if (start === null) {
        return;
    }

    var item;

    if (context === undefined) {
        context = this;
    }

    // push cursor
    var cursor = allocateCursor(this, start, null);

    while (cursor.prev !== null) {
        item = cursor.prev;
        cursor.prev = item.prev;

        if (fn.call(context, item.data, item, this)) {
            break;
        }
    }

    // pop cursor
    releaseCursor(this);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.remove"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>remove (item)](#apidoc.element.csso.syntax.List.prototype.remove)
- description and source-code
```javascript
remove = function (item) {
    //      item
    //       ^
    // prev     next
    this.updateCursors(item, item.prev, item, item.next);

    if (item.prev !== null) {
        item.prev.next = item.next;
    } else {
        if (this.head !== item) {
            throw new Error('item doesn\'t below to list');
        }

        this.head = item.next;
    }

    if (item.next !== null) {
        item.next.prev = item.prev;
    } else {
        if (this.tail !== item) {
            throw new Error('item doesn\'t below to list');
        }

        this.tail = item.prev;
    }

    item.prev = null;
    item.next = null;

    return item;
}
```
- example usage
```shell
...
    var buffer = new List();
    var nonSpaceTokenInBuffer = false;
    var protectedComment;

    children.nextUntil(children.head, function(node, item, list) {
        if (node.type === 'Comment') {
if (!specialComments || node.value.charAt(0) !== '!') {
    list.remove(item);
    return;
}

if (nonSpaceTokenInBuffer || protectedComment) {
    return true;
}
...
```

#### <a name="apidoc.element.csso.syntax.List.prototype.some"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>some (fn, context)](#apidoc.element.csso.syntax.List.prototype.some)
- description and source-code
```javascript
some = function (fn, context) {
    var cursor = this.head;

    if (context === undefined) {
        context = this;
    }

    while (cursor !== null) {
        if (fn.call(context, cursor.data, cursor, this)) {
            return true;
        }

        cursor = cursor.next;
    }

    return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.toArray"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>toArray ()](#apidoc.element.csso.syntax.List.prototype.toArray)
- description and source-code
```javascript
toArray = function () {
    var cursor = this.head;
    var result = [];

    while (cursor) {
        result.push(cursor.data);
        cursor = cursor.next;
    }

    return result;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.toJSON"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>toJSON ()](#apidoc.element.csso.syntax.List.prototype.toJSON)
- description and source-code
```javascript
toJSON = function () {
    var cursor = this.head;
    var result = [];

    while (cursor) {
        result.push(cursor.data);
        cursor = cursor.next;
    }

    return result;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.List.prototype.updateCursors"></a>[function <span class="apidocSignatureSpan">csso.syntax.List.prototype.</span>updateCursors (prevOld, prevNew, nextOld, nextNew)](#apidoc.element.csso.syntax.List.prototype.updateCursors)
- description and source-code
```javascript
updateCursors = function (prevOld, prevNew, nextOld, nextNew) {
    var cursor = this.cursor;

    while (cursor !== null) {
        if (cursor.prev === prevOld) {
            cursor.prev = prevNew;
        }

        if (cursor.next === nextOld) {
            cursor.next = nextNew;
        }

        cursor = cursor.cursor;
    }
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.csso.syntax.Tokenizer"></a>[module csso.syntax.Tokenizer](#apidoc.module.csso.syntax.Tokenizer)

#### <a name="apidoc.element.csso.syntax.Tokenizer.Tokenizer"></a>[function <span class="apidocSignatureSpan">csso.syntax.</span>Tokenizer (source, startOffset, startLine, startColumn)](#apidoc.element.csso.syntax.Tokenizer.Tokenizer)
- description and source-code
```javascript
Tokenizer = function (source, startOffset, startLine, startColumn) {
    this.offsetAndType = null;
    this.lines = null;
    this.columns = null;

    this.setSource(source || '', startOffset, startLine, startColumn);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.CssSyntaxError"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>CssSyntaxError (message, source, offset, line, column)](#apidoc.element.csso.syntax.Tokenizer.CssSyntaxError)
- description and source-code
```javascript
CssSyntaxError = function (message, source, offset, line, column) {
    var error = new SyntaxError();
    error.name = 'CssSyntaxError';
    error.message = message;
    error.source = source;
    error.offset = offset;
    error.line = line;
    error.column = column;

    error.sourceFragment = function(extraLines) {
        return sourceFragment(error, isNaN(extraLines) ? 0 : extraLines);
    };
    Object.defineProperty(error, 'formattedMessage', {
        get: function() {
            return (
                'Parse error: ' + error.message + '\n' +
                sourceFragment(error, 2)
            );
        }
    });

    // for backward capability
    error.parseError = {
        offset: offset,
        line: line,
        column: column
    };

    return error;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.cmpChar"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>cmpChar (testStr, offset, referenceCode)](#apidoc.element.csso.syntax.Tokenizer.cmpChar)
- description and source-code
```javascript
function cmpChar(testStr, offset, referenceCode) {
    var code = testStr.charCodeAt(offset);

    // code.toLowerCase()
    if (code >= 65 && code <= 90) {
        code = code | 32;
    }

    return code === referenceCode;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.cmpStr"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>cmpStr (testStr, start, end, referenceStr)](#apidoc.element.csso.syntax.Tokenizer.cmpStr)
- description and source-code
```javascript
function cmpStr(testStr, start, end, referenceStr) {
    if (end - start !== referenceStr.length) {
        return false;
    }

    if (start < 0 || end > testStr.length) {
        return false;
    }

    for (var i = start; i < end; i++) {
        var testCode = testStr.charCodeAt(i);
        var refCode = referenceStr.charCodeAt(i - start);

        // testStr[i].toLowerCase()
        if (testCode >= 65 && testCode <= 90) {
            testCode = testCode | 32;
        }

        if (testCode !== refCode) {
            return false;
        }
    }

    return true;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.endsWith"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>endsWith (testStr, referenceStr)](#apidoc.element.csso.syntax.Tokenizer.endsWith)
- description and source-code
```javascript
function endsWith(testStr, referenceStr) {
    return cmpStr(testStr, testStr.length - referenceStr.length, testStr.length, referenceStr);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.findCommentEnd"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findCommentEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findCommentEnd)
- description and source-code
```javascript
function findCommentEnd(source, offset) {
    var commentEnd = source.indexOf('*/', offset);

    if (commentEnd === -1) {
        return source.length;
    }

    return commentEnd + 2;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.findDecimalNumberEnd"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findDecimalNumberEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findDecimalNumberEnd)
- description and source-code
```javascript
function findDecimalNumberEnd(source, offset) {
    for (; offset < source.length; offset++) {
        var code = source.charCodeAt(offset);

        if (code < 48 || code > 57) {  // not a 0 .. 9
            break;
        }
    }

    return offset;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.findEscaseEnd"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findEscaseEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findEscaseEnd)
- description and source-code
```javascript
function findEscaseEnd(source, offset) {
    for (var i = 0; i < 7 && offset + i < source.length; i++) {
        var code = source.charCodeAt(offset + i);

        if (i !== 6 && isHex(code)) {
            continue;
        }

        if (i > 0) {
            offset += i - 1 + isNewline(source, offset + i, code);
            if (code === SPACE || code === TAB) {
                offset++;
            }
        }

        break;
    }

    return offset;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.findIdentifierEnd"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findIdentifierEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findIdentifierEnd)
- description and source-code
```javascript
function findIdentifierEnd(source, offset) {
    for (; offset < source.length; offset++) {
        var code = source.charCodeAt(offset);

        if (code === BACK_SLASH) {
            offset = findEscaseEnd(source, offset + 1);
        } else if (code < SYMBOL_TYPE_LENGTH && PUNCTUATION[code] === PUNCTUATOR) {
            break;
        }
    }

    return offset;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.findLastNonSpaceLocation"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findLastNonSpaceLocation (scanner)](#apidoc.element.csso.syntax.Tokenizer.findLastNonSpaceLocation)
- description and source-code
```javascript
function findLastNonSpaceLocation(scanner) {
    for (var i = scanner.source.length - 1; i >= 0; i--) {
        var code = scanner.source.charCodeAt(i);

        if (code !== SPACE && code !== TAB && code !== R && code !== N && code !== F) {
            break;
        }
    }

    return scanner.getLocation(i + 1);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.findNumberEnd"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findNumberEnd (source, offset, allowFraction)](#apidoc.element.csso.syntax.Tokenizer.findNumberEnd)
- description and source-code
```javascript
function findNumberEnd(source, offset, allowFraction) {
    var code;

    offset = findDecimalNumberEnd(source, offset);

    // fraction: .\d+
    if (allowFraction && offset + 1 < source.length && source.charCodeAt(offset) === FULLSTOP) {
        code = source.charCodeAt(offset + 1);

        if (isNumber(code)) {
            offset = findDecimalNumberEnd(source, offset + 1);
        }
    }

    // exponent: e[+-]\d+
    if (offset + 1 < source.length) {
        if ((source.charCodeAt(offset) | 32) === E) { // case insensitive check for 'e'
            code = source.charCodeAt(offset + 1);

            if (code === PLUSSIGN || code === HYPHENMINUS) {
                if (offset + 2 < source.length) {
                    code = source.charCodeAt(offset + 2);
                }
            }

            if (isNumber(code)) {
                offset = findDecimalNumberEnd(source, offset + 2);
            }
        }
    }

    return offset;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.findStringEnd"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findStringEnd (source, offset, quote)](#apidoc.element.csso.syntax.Tokenizer.findStringEnd)
- description and source-code
```javascript
function findStringEnd(source, offset, quote) {
    for (; offset < source.length; offset++) {
        var code = source.charCodeAt(offset);

        // TODO: bad string
        if (code === BACK_SLASH) {
            offset++;
        } else if (code === quote) {
            offset++;
            break;
        }
    }

    return offset;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.findWhitespaceEnd"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>findWhitespaceEnd (source, offset)](#apidoc.element.csso.syntax.Tokenizer.findWhitespaceEnd)
- description and source-code
```javascript
function findWhitespaceEnd(source, offset) {
    for (; offset < source.length; offset++) {
        var code = source.charCodeAt(offset);

        if (code !== SPACE && code !== TAB && code !== R && code !== N && code !== F) {
            break;
        }
    }

    return offset;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.firstCharOffset"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>firstCharOffset (source)](#apidoc.element.csso.syntax.Tokenizer.firstCharOffset)
- description and source-code
```javascript
function firstCharOffset(source) {
    // detect BOM (https://en.wikipedia.org/wiki/Byte_order_mark)
    if (source.charCodeAt(0) === 0xFEFF ||  // UTF-16BE
        source.charCodeAt(0) === 0xFFFE) {  // UTF-16LE
        return 1;
    }

    return 0;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.isHex"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>isHex (code)](#apidoc.element.csso.syntax.Tokenizer.isHex)
- description and source-code
```javascript
function isHex(code) {
    return (code >= 48 && code <= 57) || // 0 .. 9
           (code >= 65 && code <= 70) || // A .. F
           (code >= 97 && code <= 102);  // a .. f
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.isNewline"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>isNewline (source, offset, code)](#apidoc.element.csso.syntax.Tokenizer.isNewline)
- description and source-code
```javascript
function isNewline(source, offset, code) {
    if (code === N || code === F || code === R) {
        if (code === R && offset + 1 < source.length && source.charCodeAt(offset + 1) === N) {
            return 2;
        }

        return 1;
    }

    return 0;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.isNumber"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.</span>isNumber (code)](#apidoc.element.csso.syntax.Tokenizer.isNumber)
- description and source-code
```javascript
function isNumber(code) {
    return code >= 48 && code <= 57;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.csso.syntax.Tokenizer.prototype"></a>[module csso.syntax.Tokenizer.prototype](#apidoc.module.csso.syntax.Tokenizer.prototype)

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.consume"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>consume (tokenType)](#apidoc.element.csso.syntax.Tokenizer.prototype.consume)
- description and source-code
```javascript
consume = function (tokenType) {
    var start = this.tokenStart;

    this.eat(tokenType);

    return this.substrToCursor(start);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.consumeNonWS"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>consumeNonWS (tokenType)](#apidoc.element.csso.syntax.Tokenizer.prototype.consumeNonWS)
- description and source-code
```javascript
consumeNonWS = function (tokenType) {
    this.skipWS();

    return this.consume(tokenType);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.eat"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>eat (tokenType)](#apidoc.element.csso.syntax.Tokenizer.prototype.eat)
- description and source-code
```javascript
eat = function (tokenType) {
    if (this.tokenType !== tokenType) {
        this.error(
            NAME[tokenType] + ' is expected',
            // when test type is part of another token show error for current position + 1
            // e.g. eat(HYPHENMINUS) will fail on "-foo", but pointing on "-" is odd
            this.tokenStart + (this.source.charCodeAt(this.tokenStart) === tokenType ? 1 : 0)
        );
    }

    this.next();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.eatNonWS"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>eatNonWS (tokenType)](#apidoc.element.csso.syntax.Tokenizer.prototype.eatNonWS)
- description and source-code
```javascript
eatNonWS = function (tokenType) {
    this.skipWS();
    this.eat(tokenType);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.error"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>error (message, offset)](#apidoc.element.csso.syntax.Tokenizer.prototype.error)
- description and source-code
```javascript
error = function (message, offset) {
    var location = typeof offset !== 'undefined' && offset < this.source.length
        ? this.getLocation(offset)
        : this.eof
            ? findLastNonSpaceLocation(this)
            : this.getLocation(this.tokenStart);

    throw new CssSyntaxError(
        message || 'Unexpected input',
        this.source,
        location.offset,
        location.line,
        location.column
    );
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.expectIdentifier"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>expectIdentifier (name)](#apidoc.element.csso.syntax.Tokenizer.prototype.expectIdentifier)
- description and source-code
```javascript
expectIdentifier = function (name) {
    if (this.tokenType !== IDENTIFIER || cmpStr(this.source, this.tokenStart, this.tokenEnd, name) === false) {
        this.error('Identifier '' + name + '' is expected');
    }

    this.next();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.getLocation"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>getLocation (offset, filename)](#apidoc.element.csso.syntax.Tokenizer.prototype.getLocation)
- description and source-code
```javascript
getLocation = function (offset, filename) {
    if (!this.linesAnsColumnsComputed) {
        computeLinesAndColumns(this, this.source);
    }

    return {
        source: filename,
        offset: this.startOffset + offset,
        line: this.lines[offset],
        column: this.columns[offset]
    };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.getLocationRange"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>getLocationRange (start, end, filename)](#apidoc.element.csso.syntax.Tokenizer.prototype.getLocationRange)
- description and source-code
```javascript
getLocationRange = function (start, end, filename) {
    if (!this.linesAnsColumnsComputed) {
        computeLinesAndColumns(this, this.source);
    }

    return {
        source: filename,
        start: {
            offset: this.startOffset + start,
            line: this.lines[start],
            column: this.columns[start]
        },
        end: {
            offset: this.startOffset + end,
            line: this.lines[end],
            column: this.columns[end]
        }
    };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.getTokenValue"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>getTokenValue ()](#apidoc.element.csso.syntax.Tokenizer.prototype.getTokenValue)
- description and source-code
```javascript
getTokenValue = function () {
    return this.source.substring(this.tokenStart, this.tokenEnd);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.getTypes"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>getTypes ()](#apidoc.element.csso.syntax.Tokenizer.prototype.getTypes)
- description and source-code
```javascript
getTypes = function () {
    return Array.prototype.slice.call(this.offsetAndType, 0, this.tokenCount).map(function(item) {
        return NAME[item >> TYPE_OFFSET];
    });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.lookupNonWSType"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>lookupNonWSType (offset)](#apidoc.element.csso.syntax.Tokenizer.prototype.lookupNonWSType)
- description and source-code
```javascript
lookupNonWSType = function (offset) {
    offset += this.currentToken;

    for (var type; offset < this.tokenCount; offset++) {
        type = this.offsetAndType[offset] >> TYPE_OFFSET;

        if (type !== WHITESPACE) {
            return type;
        }
    }

    return NULL;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.lookupType"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>lookupType (offset)](#apidoc.element.csso.syntax.Tokenizer.prototype.lookupType)
- description and source-code
```javascript
lookupType = function (offset) {
    offset += this.currentToken;

    if (offset < this.tokenCount) {
        return this.offsetAndType[offset] >> TYPE_OFFSET;
    }

    return NULL;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.lookupValue"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>lookupValue (offset, referenceStr)](#apidoc.element.csso.syntax.Tokenizer.prototype.lookupValue)
- description and source-code
```javascript
lookupValue = function (offset, referenceStr) {
    offset += this.currentToken;

    if (offset < this.tokenCount) {
        return cmpStr(
            this.source,
            this.offsetAndType[offset - 1] & OFFSET_MASK,
            this.offsetAndType[offset] & OFFSET_MASK,
            referenceStr
        );
    }

    return false;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.next"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>next ()](#apidoc.element.csso.syntax.Tokenizer.prototype.next)
- description and source-code
```javascript
next = function () {
    var next = this.currentToken + 1;

    if (next < this.tokenCount) {
        this.currentToken = next;
        this.tokenStart = this.tokenEnd;
        next = this.offsetAndType[next];
        this.tokenType = next >> TYPE_OFFSET;
        this.tokenEnd = next & OFFSET_MASK;
    } else {
        this.currentToken = this.tokenCount;
        this.eof = true;
        this.tokenType = NULL;
        this.tokenStart = this.tokenEnd = this.source.length;
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.setSource"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>setSource (source, startOffset, startLine, startColumn)](#apidoc.element.csso.syntax.Tokenizer.prototype.setSource)
- description and source-code
```javascript
setSource = function (source, startOffset, startLine, startColumn) {
    var start = firstCharOffset(source);

    this.source = source;
    this.startOffset = typeof startOffset === 'undefined' ? 0 : startOffset;
    this.startLine = typeof startLine === 'undefined' ? 1 : startLine;
    this.startColumn = typeof startColumn === 'undefined' ? 1 : startColumn;
    this.linesAnsColumnsComputed = false;

    this.eof = false;
    this.currentToken = -1;
    this.tokenType = 0;
    this.tokenStart = start;
    this.tokenEnd = start;

    tokenLayout(this, source, start);
    this.next();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.skip"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>skip (tokenCount)](#apidoc.element.csso.syntax.Tokenizer.prototype.skip)
- description and source-code
```javascript
skip = function (tokenCount) {
    var next = this.currentToken + tokenCount;

    if (next < this.tokenCount) {
        this.currentToken = next;
        this.tokenStart = this.offsetAndType[next - 1] & OFFSET_MASK;
        next = this.offsetAndType[next];
        this.tokenType = next >> TYPE_OFFSET;
        this.tokenEnd = next & OFFSET_MASK;
    } else {
        this.currentToken = this.tokenCount;
        this.next();
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.skipSC"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>skipSC ()](#apidoc.element.csso.syntax.Tokenizer.prototype.skipSC)
- description and source-code
```javascript
skipSC = function () {
    while (this.tokenType === WHITESPACE || this.tokenType === COMMENT) {
        this.next();
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.skipWS"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>skipWS ()](#apidoc.element.csso.syntax.Tokenizer.prototype.skipWS)
- description and source-code
```javascript
skipWS = function () {
    for (var i = this.currentToken, skipTokenCount = 0; i < this.tokenCount; i++, skipTokenCount++) {
        if ((this.offsetAndType[i] >> TYPE_OFFSET) !== WHITESPACE) {
            break;
        }
    }

    if (skipTokenCount > 0) {
        this.skip(skipTokenCount);
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.csso.syntax.Tokenizer.prototype.substrToCursor"></a>[function <span class="apidocSignatureSpan">csso.syntax.Tokenizer.prototype.</span>substrToCursor (start)](#apidoc.element.csso.syntax.Tokenizer.prototype.substrToCursor)
- description and source-code
```javascript
substrToCursor = function (start) {
    return this.source.substring(start, this.tokenStart);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.csso.syntax.syntax"></a>[module csso.syntax.syntax](#apidoc.module.csso.syntax.syntax)

#### <a name="apidoc.element.csso.syntax.syntax.Lexer"></a>[function <span class="apidocSignatureSpan">csso.syntax.syntax.</span>Lexer (config, syntax, structure)](#apidoc.element.csso.syntax.syntax.Lexer)
- description and source-code
```javascript
Lexer = function (config, syntax, structure) {
    this.valueCommonSyntax = cssWideKeywords;
    this.syntax = syntax;
    this.generic = false;
    this.properties = {};
    this.types = {};
    this.structure = structure;

    if (config) {
        if (config.generic) {
            this.generic = true;
            for (var name in generic) {
                this.addType_(name, generic[name]);
            }
        }

        if (config.types) {
            for (var name in config.types) {
                this.addType_(name, config.types[name]);
            }
        }

        if (config.properties) {
            for (var name in config.properties) {
                this.addProperty_(name, config.properties[name]);
            }
        }
    }
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.csso.usage"></a>[module csso.usage](#apidoc.module.csso.usage)

#### <a name="apidoc.element.csso.usage.buildIndex"></a>[function <span class="apidocSignatureSpan">csso.usage.</span>buildIndex (data)](#apidoc.element.csso.usage.buildIndex)
- description and source-code
```javascript
function buildIndex(data) {
    var scopes = false;

    if (data.scopes && Array.isArray(data.scopes)) {
        scopes = Object.create(null);

        for (var i = 0; i < data.scopes.length; i++) {
            var list = data.scopes[i];

            if (!list || !Array.isArray(list)) {
                throw new Error('Wrong usage format');
            }

            for (var j = 0; j < list.length; j++) {
                var name = list[j];

                if (hasOwnProperty.call(scopes, name)) {
                    throw new Error('Class can\'t be used for several scopes: ' + name);
                }

                scopes[name] = i + 1;
            }
        }
    }

    return {
        tags: buildMap(data.tags, true),
        ids: buildMap(data.ids),
        classes: buildMap(data.classes),
        scopes: scopes
    };
}
```
- example usage
```shell
...
inputRules = ast.children;
ast.children = outputRules;
    } else {
inputRules = wrapBlock(ast);
    }

    if (options.usage) {
usageData = usageUtils.buildIndex(options.usage);
    }

    do {
chunk = readChunk(inputRules, Boolean(specialComments));

compressChunk(chunk.stylesheet, firstAtrulesAllowed, usageData, chunkNum++, logger);
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
