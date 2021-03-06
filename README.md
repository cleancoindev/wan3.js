**PREVIEW RELEASE** This is a beta preview release with breaking changes! The current stable version is 0.20.0 
[![Join the chat at https://gitter.im/wandevs/community](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/wandevs/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

[![NPM version][npm-image]][npm-url] [![CircleCI][circle-image]][circle-url] [![dependency status][dep-image]][dep-url] [![dev dependency status][dep-dev-image]][dep-dev-url] [![Coverage Status][coveralls-image]][coveralls-url]

# wan3.js - Wanchain JavaScript API

This is the Wanchain [JavaScript API][docs]
which connects to the [Generic JSON RPC](https://github.com/ethereum/wiki/wiki/JSON-RPC) spec.

Library is still a mess! Cleanup in progress..

You need to run a local or remote Wanchain node to use this library.

Please read the [documentation][docs] for more.

## Installation

### Node

```bash
npm install web3
```

### Yarn

```bash
yarn add web3
```

### Meteor

*Note*: works only in the Browser for now. (PR welcome).

```bash
meteor add ethereum:web3
```

### In the Browser

Use the prebuild ``dist/web3.min.js``, or
build using the [wan3.js][repo] repository:

```bash
npm run-script build
```

Then include `dist/web3.js` in your html file.
This will expose `Web3` on the window object.

## Usage

```js
// in node.js
var Web3 = require('wan3');

var web3 = new Web3('ws://localhost:8546');
console.log(web3);
> {
    eth: ... ,
    shh: ... ,
    utils: ...,
    ...
}
```

Additionally you can set a provider using `web3.setProvider()` (e.g. WebsocketProvider)

```js
web3.setProvider('ws://localhost:8546');
// or
web3.setProvider(new Web3.providers.WebsocketProvider('ws://localhost:8546'));
```

There you go, now you can use it:

```js
web3.eth.getAccounts()
.then(console.log);
```

### Usage with TypeScript

Type definitions are maintained at [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped) by others. You can install them with

```bash
npm install --dev @types/web3.js
```

You might need to install type definitions for `bignumber.js` and `lodash` too.

And then use `web3.js` as follows:

```typescript
import Web3 = require("web3"); // Note the special syntax! Copy this line when in doubt!
const web3 = new Web3("ws://localhost:8546");
```

**Please note:** We do not support TypeScript ourselves. If you have any issue with TypeScript and `web3.js` do not create an issue here. Go over to DefinitelyTyped and do it there.

## Documentation

Documentation can be found at [read the docs][docs]


## Building

### Requirements

* [Node.js](https://nodejs.org)
* npm

```bash
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
```

### Building (gulp)

Build only the web3.js package

```bash
npm run-script build
```

Or build all sub packages as well

```bash
npm run-script build-all
```

This will put all the browser build files into the `dist` folder.


### Testing (mocha)

```bash
npm test
```

### Contributing

- All contributions have to go into develop, or the 1.0 branch
- Please follow the code style of the other files, we use 4 spaces as tabs.

[npm-image]: https://badge.fury.io/js/wan3.svg
[npm-url]: https://npmjs.org/package/wan3
[circle-image]: https://circleci.com/gh/wandevs/wan3.js.svg?style=svg
[circle-url]: https://circleci.com/gh/wandevs/wan3.js
[dep-image]: https://david-dm.org/wandevs/wan3.js.svg
[dep-url]: https://david-dm.org/wandevs/wan3.js
[dep-dev-image]: https://david-dm.org/wandevs/wan3.js/dev-status.svg
[dep-dev-url]: https://david-dm.org/wandevs/wan3.js#info=devDependencies
[coveralls-image]: https://coveralls.io/repos/wandevs/wan3.js/badge.svg?branch=1.0
[coveralls-url]: https://coveralls.io/r/wandevs/wan3.js?branch=1.0
