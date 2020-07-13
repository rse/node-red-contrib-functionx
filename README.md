
# node-red-contrib-functionx

Clone of Node-RED function node with capability to automatically install used NPM packages.

## Install

```sh
$ npm install node-red-contrib-functionx
```

## Usage

The Node-RED **functionx** node behaves exactly like the standard
Node-RED **function** node, with the exception of allowing the use of
NPM modules within the JavaScript code. For this, the node scans the
JavaScript code for any `require()` statements and automatically and
temporarily installs the NPM modules referenced in the `require()`
statements. The temporarily installed NPM modules are automatically
cleaned from the disk when the Node-RED process closes.

## Example

```js
var { upperCase } = require("upper-case")       // install latest   version
var lowerCase     = require("lower-case@1.1.3") // install specific version
msg.payload = {             
    upper: upperCase("Hello World"),
    lower: lowerCase("Hello World")
}
return msg
```

## License

This Node-RED node is licensed under the [Apache License 2.0](https://spdx.org/licenses/Apache-2.0.html).

## Credits

This Node-RED node is a derived from the latest
version (as of 2020-07-13) of the official
[Node-RED 1.1.2 **function** node](https://github.com/node-red/node-red/blob/master/packages/node_modules/%40node-red/nodes/core/function/10-function.js)
and was patched with the extra functionality from John O'Connor's
[fork of the node-red-contrib-function-npm](https://github.com/sax1johno/node-red-contrib-function-npm)
Node-RED node.

