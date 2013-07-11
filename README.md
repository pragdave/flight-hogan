# flight-hogan

[![Build Status](https://secure.travis-ci.org/<username>/flight-hogan.png)](http://travis-ci.org/<username>/flight-hogan)

A [Flight](https://github.com/flightjs/flight) component for Hogan.

## Installation

```bash
bower install --save flight-hogan
```

## Example


Instantiate the hogan component.

```javascript
var hogan = require('bower_components/flight-hogan/lib/hogan');
hogan.attachTo(document);
```

Use the with_hogan mixin

```javascript
define(function () {
  var defineComponent = require('flight/component');
  var withHogan = require('bower_components/flight-hogan/lib/with_hogan');
  return defineComponent(myComponent, withHogan);

  function myComponent () {
    this.after('initialize', function() {
      var helloWorld = this.renderTemplate({
        template: 'Hello, {{name}}!',
        renderParams: {
          name: 'World'
        }
      };
    };
  }
}
```

### Pre-compiled templates

You can pass a hash of compiled templates as an option to the Hogan component

```javascript
var precompiledTemplates = require('/templates/compiled.js');
var hogan = require('bower_components/flight-hogan/lib/hogan');
hogan.attachTo(document, {
  precompiledTemplates: precompiledTemplates
});
```

```javascript
define(function () {
  var defineComponent = require('flight/component');
  var withHogan = require('bower_components/flight-hogan/lib/with_hogan');
  return defineComponent(myComponent, withHogan);

  function myComponent () {
    this.after('initialize', function() {
      // render the 'hello_world' template from /templates/compiled.js
      var helloWorld = this.renderTemplate({
        templateName: 'hello_world',
        renderParams: {
          name: 'World'
        }
      };
    };
  }
}
```

## Development

Development of this component requires [Bower](http://bower.io), and preferably
[Karma](http://karma-runner.github.io) to be globally installed:

```bash
npm install -g bower karma
```

Then install the Node.js and client-side dependencies by running the following
commands in the repo's root directory.

```bash
npm install
bower install
```

To continuously run the tests in Chrome and Firefox during development, just run:

```bash
karma start
```

## Contributing to this project

Anyone and everyone is welcome to contribute. Please take a moment to
review the [guidelines for contributing](CONTRIBUTING.md).

* [Bug reports](CONTRIBUTING.md#bugs)
* [Feature requests](CONTRIBUTING.md#features)
* [Pull requests](CONTRIBUTING.md#pull-requests)