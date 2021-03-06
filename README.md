# esnext

Use tomorrow's JavaScript syntax today.

**NOTE:** This project is early alpha. Use it in production at your own risk.
For a more robust project with similar goals, see [Google's Traceur][traceur].

## Install

```
$ npm install [--save-dev] esnext
```

## Goals

* Allow using future JavaScript syntax today.
* Require as little runtime code as possible.
* Generate human-readable code.
* TODO: Integrate with build tools such as [broccoli][broccoli].

## Non-Goals

* Provide polyfills for future JavaScript APIs.
* Line-by-line equivalence from source to compiled.

## Features

### Available

* [classes][features-classes] (via [es6-class][es6-class])
* [generators][features-generators] (via [regenerator][regenerator])
* [arrow functions][features-arrows] (via [es6-arrow-function][es6-arrow-function])
* [template strings][features-template-strings] (via [es6-templates][es6-templates])
* [rest params][features-default-rest-spread] (via [es6-rest-params][es6-rest-params])
* [default params][features-default-rest-spread] (via [es6-default-params][es6-default-params])
* [spread][features-default-rest-spread] (via [es6-spread][es6-spread])

### TODO

* [modules][features-modules] (i.e. integration with [es6-module-transpiler][es6-module-transpiler])
* [block scoping (`let`)][features-let-const]
* [destructuring][features-destructuring]

Any omissions here are not intentional and we'd love to integrate support for
more future JavaScript syntax (see [es6features][es6features] for a more
complete list). See the Contributing section below. Keep in mind that, as of
right now, this project is intended to support new JavaScript *syntax* only.
Any new APIs should be handled using polyfills. This may change in the future.

## Usage

```js
var compile = require('esnext').compile;
var result = compile(es6Source);
fs.writeFileSync('result.js', result.code, 'utf8');
fs.writeFileSync('result.js.map', JSON.stringify(result.map), 'utf8');
```

Or, use one of these libraries that integrate esnext with other tools:

* [broccoli-esnext][broccoli-esnext]
* [grunt-esnext][grunt-esnext]

## Contributing

[![Build Status](https://travis-ci.org/square/esnext.png?branch=master)](https://travis-ci.org/square/esnext)

### Setup

First, install the development dependencies:

```
$ npm install
```

Then, try running the tests:

```
$ npm test
```

### Pull Requests

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

Any contributors to the master esnext repository must sign the [Individual
Contributor License Agreement (CLA)][cla].  It's a short form that covers our
bases and makes sure you're eligible to contribute.

[cla]: https://spreadsheets.google.com/spreadsheet/viewform?formkey=dDViT2xzUHAwRkI3X3k5Z0lQM091OGc6MQ&ndplr=1

When you have a change you'd like to see in the master repository, [send a pull
request](https://github.com/square/esnext/pulls). Before we merge your
request, we'll make sure you're in the list of people who have signed a CLA.

## Acknowledgements

Huge thanks to [Ben Newman][benjamn] for [recast][recast] and
[regenerator][regenerator]. Thanks also to [Thomas Boyt][thomasboyt] for his
work on the [es6-module-transpiler][es6-module-transpiler],
[es6-class][es6-class], [es6-arrow-function][es6-arrow-function], and others.

[benjamn]: https://github.com/benjamn
[broccoli-esnext]: https://github.com/shinnn/broccoli-esnext
[broccoli]: https://github.com/joliss/broccoli
[es6-arrow-function]: https://github.com/square/es6-arrow-function
[es6-class]: https://github.com/square/es6-class
[es6-default-params]: https://github.com/square/es6-default-params
[es6-module-transpiler]: https://github.com/square/es6-module-transpiler
[es6-rest-params]: https://github.com/thomasboyt/es6-rest-params
[es6-spread]: https://github.com/square/es6-spread
[es6-templates]: https://github.com/square/es6-templates
[es6features]: https://github.com/lukehoban/es6features
[features-arrows]: https://github.com/lukehoban/es6features#arrows
[features-classes]: https://github.com/lukehoban/es6features#classes
[features-default-rest-spread]: https://github.com/lukehoban/es6features#default--rest--spread
[features-destructuring]: https://github.com/lukehoban/es6features#destructuring
[features-generators]: https://github.com/lukehoban/es6features#generators
[features-let-const]: https://github.com/lukehoban/es6features#let--const
[features-modules]: https://github.com/lukehoban/es6features#modules
[features-template-strings]: https://github.com/lukehoban/es6features#template-strings
[grunt-esnext]: https://github.com/shinnn/grunt-esnext
[recast]: https://github.com/benjamn/recast
[regenerator]: http://facebook.github.io/regenerator/
[thomasboyt]: http://www.thomasboyt.com/
[traceur]: https://github.com/google/traceur-compiler
