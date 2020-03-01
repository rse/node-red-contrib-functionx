
# node-red-contrib-functionx

Clone of Node-RED function node with capability to automatically install used NPM packages.

## Install

<pre>npm install node-red-contrib-function-npm</pre>

## Usage

The Node-RED **functionx** node behaves like the normal **function**
node, with the exception of allowing the use of NPM modules within
the script inside the block. It scans the script for any `require()`
statements and automatically installs the module specified in the
`require()` statement. The module is automatically cleaned from the disk
when the Node-RED process closes.

```javascript
var lowerCase = require('lower-case@1.1.3') // install specific version
var upperCase = require('upper-case');      // install latest   version
msg.payload = {             
    upper: upperCase('Hello World'),
    lower: lowerCase('Hello World')
} ;
return msg;
```

## License

This work is licensed under the [Apache License, Version 2.0](LICENSE).

## Credits

This Node-RED node is a derived from the latest
version (as of 2020-03-01) of the official
<a href="https://github.com/node-red/node-red/blob/master/packages/node_modules/%40node-red/nodes/core/function/10-function.js">
Node-RED function node</a> and was patched with the extra functionality
from John O'Connor <a
href="https://github.com/sax1johno/node-red-contrib-function-npm">fork of the node-red-contrib-function-npm</a> Node-RED node.

