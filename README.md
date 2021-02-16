# Jar [![Build Status](https://travis-ci.org/cferdinandi/jar.svg)](https://travis-ci.org/cferdinandi/jar)
A tiny (< 1kb) helper library that makes working with cookies a bit easier.

[Installation](#installation) | [API](#api) | [Browser Compatibility](#browser-compatibility) | [License](#license)

<hr>

### Want to learn how to write your own vanilla JS libraries? Check out my [Vanilla JS Pocket Guides](https://vanillajsguides.com/) or join the [Vanilla JS Academy](https://vanillajsacademy.com) and level-up as a web developer. 🚀

<hr>


## Installation

[The CDN is the fastest and simplest way to get started](https://cdn.jsdelivr.net/npm/jarvanillajs/dist/), but you can use importable modules or a direct download if you’d prefer.

```html
<!-- Get the latest major version -->
<script src="https://cdn.jsdelivr.net/npm/jarvanillajs@1/dist/jar.min.js"></script>
```

Jar uses semantic versioning. You can grab a major, minor, or patch version from the CDN with the `@1.2.3` syntax. You can find all available versions [under releases](https://github.com/cferdinandi/jar/releases).

**ES Modules**

Jar also supports modern browsers and module bundlers (like Rollup, Webpack, Snowpack, and so on) using the ES modules import syntax. Use the `.es` version.

```js
import jar from 'https://cdn.jsdelivr.net/npm/jarvanillajs@1/dist/jar.es.min.js';
```

**NPM**

You can also use NPM (or your favorite package manager). First, install with NPM.

```bash
npm install jarvanillajs --save
```

Then import the package.

```js
import jar from 'jarvanillajs';
```

**CommonJS**

If you use NodeJS, you can import jar using the `require()` method with the `.cjs` version.

```js
let jar = require('https://cdn.jsdelivr.net/npm/jarvanillajs@1/dist/jar.cjs.min.js');
```

**AMD**

If you use RequireJS, SystemJS, and other AMD formats, you can import jar with the `.amd` version.

```js
requirejs(['https://cdn.jsdelivr.net/npm/jarvanillajs@1/dist/jar.amd.min.js'], function (jar) {
  //...
});
```

**Direct Download**

You can download the files directly from GitHub.

Compiled and production-ready code can be found in the `dist` directory. The `src` directory contains development code.

```html
<script src="path/to/jar.min.js"></script>
```



## API

### `set()`

Create a cookie. Pass in the cookie name and value as arguments.

```js
// Create a cookie named `sandwich` with a value of `turkey`
jar.set('sandwich', 'turkey');
```

As an optional third argument, provide an object of options to use for the cookie. The default values are shown below.

```js
let options = {
	path: '/',         // path to set the cookie at
	domain: hostname,  // domain for the cookie
	'max-age': null,   // maximum amount of time to keep the cookie, in seconds
	expires: null,     // date on which to expire the cookie (GMT format)
	secure: false,     // the cookie can only be transmitted over HTTPS
	'same-site': 'lax' // lax|strict|none
};
```

For example, this cookie is set for the root path ('/'), and expires in one week (60 seconds x 60 minutes x 24 hours x 7 days)

```js
jar.set('drink', 'soda', {
	'max-age': 60 * 60 * 24 * 7
});
```

### `get()`

Get the value of a cookie. Pass in the cookie name as an argument.

```js
// Get the `sandwich` cookie
jar.get('sandwich');
```

### `remove()`

Delete a cookie.  Pass in the cookie name as an argument.

```js
// Delete the `sandwich` cookie
jar.remove('sandwich');
```

If you passed in an option for `path` other than the default `/`, you must also provide that as a second argument.

```js
// Delete the `drink` cookie at the /order path
jar.remove('drink', '/order');
```



## Browser Compatibility

Jar works in all modern browsers on desktop and mobile.



## License

The code is available under the [MIT License](LICENSE.md).