# Jar [![Build Status](https://travis-ci.org/cferdinandi/jar.svg)](https://travis-ci.org/cferdinandi/jar)
A tiny (< 1kb) helper library that makes working with cookies a bit easier.

[Installation](#installation) | [API](#api) | [Browser Compatibility](#browser-compatibility) | [License](#license)

<hr>

### Want to learn how to write your own vanilla JS libraries? Check out my [Vanilla JS Pocket Guides](https://vanillajsguides.com/) or join the [Vanilla JS Academy](https://vanillajsacademy.com) and level-up as a web developer. 🚀

<hr>


## Installation

Compiled and production-ready code can be found in the `dist` directory. The `src` directory contains development code.

**Direct Download**

You can [download the files directly from GitHub](https://github.com/cferdinandi/jar/archive/master.zip).

```html
<script src="path/to/jar.min.js"></script>
```

**CDN**

You can also use the [jsDelivr CDN](https://cdn.jsdelivr.net/gh/cferdinandi/jar/dist/). I recommend linking to a specific version number or version range to prevent major updates from breaking your site. Jar uses semantic versioning.

```html
<!-- Always get the latest version -->
<!-- Not recommended for production sites! -->
<script src="https://cdn.jsdelivr.net/gh/cferdinandi/jar/dist/jar.min.js"></script>

<!-- Get minor updates and patch fixes within a major version -->
<script src="https://cdn.jsdelivr.net/gh/cferdinandi/jar@1/dist/jar.min.js"></script>

<!-- Get patch fixes within a minor version -->
<script src="https://cdn.jsdelivr.net/gh/cferdinandi/jar@1.0/dist/jar.min.js"></script>

<!-- Get a specific version -->
<script src="https://cdn.jsdelivr.net/gh/cferdinandi/jar@1.0.0/dist/jar.min.js"></script>
```



## API

### `set()`

Create a cookie.

Pass in the cookie name and value as arguments. As an optional third argument, provide the amount of time (in milliseconds) before the cookie expires

```js
// Create a cookie named `sandwich` with a value of `turkey`
jar.set('sandwich', 'turkey');

// Create a cookie named `drink` with a value of `soda` that expires in a day
jar.set('drink', 'soda', 1000 * 60 * 60 * 24);
```

Here are some common expiration values.

```js
var hour = 1000 * 60 * 60;
var day = 1000 * 60 * 60 * 24;
var week = 1000 * 60 * 60 * 24 * 7;
var year = 1000 * 60 * 60 * 24 * 7 * 365;
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



## Browser Compatibility

Jar works in all modern browsers, and IE 6 and above.



## License

The code is available under the [MIT License](LICENSE.md).