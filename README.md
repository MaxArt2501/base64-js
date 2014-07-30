base64-js
==========

A polyfill for base64 functions `atob` and `btoa`. It also fixes IE's `atob`'s inability
to decode string containing certain whitespaces.

## Installation

As a standalone Javascript file (not needed when using AMD loaders like Require.js):

```html
<script type="text/javascript" src="base64.js"></script>
```

When using an AMD loader (like RequireJS in this example), you should require the module
at the beginning like this:

```js
require(["base64"], function() {
    ...
});
```

The module doesn't return anything, as it's a polyfill for two global functions.

To avoid unnecessary loading, it's recommended to check the existence of `window.atob`/`.btoa`
prior to requiring the module.


## Usage

Once the script has been loaded, you're good to go: `window.atob` and `window.btoa` are
ready to use.

Internet Explorer 10-11 will also have a fixed version of `atob` so it can decode strings
containing whitespaces (namely, `\t`, `\n`, `\f`, `\r` and `' '`). The original native
function can be retrieved with `atob.original` and eventually put back in place.


## Notes

The error class used in case of invalid strings is `TypeError`, instead of `InvalidCharacterError`
(for Firefox and Internet Explorer) or `DOMException` (for Chrome, Opera and Safari). This may
be changed in the future.

The error messages are also taken from Chrome's base64 implementation.


## License

The MIT License (MIT)

Copyright (c) 2014 MaxArt2501

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
