seajs-wrap
==========

[![Build Status](https://secure.travis-ci.org/afc163/seajs-wrap.png?branch=master)](https://travis-ci.org/afc163/seajs-wrap)

The Sea.js plugin for loading CommonJS modules directly.

It would wrap files with 'define(function(require, exports, module) {})' block so that you can load CommonJS modules without wrapping it first.

It could only load modules in the same domain, so please use it in debug environment.

Install
-------

Install with [spm@3.x](http://spmjs.io):

    $ spm install seajs-wrap


Usage
-----

```html
<script src="path/to/sea.js"></script>
<script src="path/to/seajs-wrap.js"></script>

<script>
seajs.use(['common'], function(Common) {
  var str = Common(); // 'CommonJS'
})
</script>
```

```js
// common.js
// It is a CommonJS module
var example = 'CommonJS'
module.exports = function() {
  return example;
}
```

- no wrap

```html
<script>
seajs.use(['test.js?nowrap'], function() {
  // it would excute test.js without wrapping
})
</script>
```
