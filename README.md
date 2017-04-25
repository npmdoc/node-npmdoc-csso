# npmdoc-csso

#### basic api documentation for  [csso (v3.1.0)](https://github.com/css/csso)  [![npm package](https://img.shields.io/npm/v/npmdoc-csso.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-csso) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-csso.svg)](https://travis-ci.org/npmdoc/node-npmdoc-csso)

#### CSSO (CSS Optimizer) is a CSS minifier with structural optimisations

[![NPM](https://nodei.co/npm/csso.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/csso)

- [https://npmdoc.github.io/node-npmdoc-csso/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-csso/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-csso/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-csso/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-csso/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-csso/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Sergey Kryzhanovsky",
        "url": "https://github.com/afelix"
    },
    "bugs": {
        "url": "https://github.com/css/csso/issues"
    },
    "dependencies": {
        "css-tree": "1.0.0-alpha19"
    },
    "description": "CSSO (CSS Optimizer) is a CSS minifier with structural optimisations",
    "devDependencies": {
        "browserify": "^13.0.0",
        "coveralls": "^2.11.6",
        "eslint": "^2.2.0",
        "istanbul": "^0.4.2",
        "jscs": "~2.10.0",
        "mocha": "~2.4.2",
        "package-json-versionify": "^1.0.4",
        "source-map": "^0.5.6",
        "uglify-js": "^2.6.1"
    },
    "directories": {},
    "dist": {
        "shasum": "1f95c8ea952b25526c3394983edd07f9d41f8bf2",
        "tarball": "https://registry.npmjs.org/csso/-/csso-3.1.0.tgz"
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
    "gitHead": "987861666282a97b0fb06321063daeb4a6bb3b6a",
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
            "name": "afelix"
        },
        {
            "name": "lahmatiy"
        },
        {
            "name": "tadatuta"
        }
    ],
    "name": "csso",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/css/csso.git"
    },
    "scripts": {
        "browserify": "browserify -t package-json-versionify --standalone csso lib/index.js | uglifyjs --compress --mangle -o dist/csso-browser.js",
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
    "version": "3.1.0",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
