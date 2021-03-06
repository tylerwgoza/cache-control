# cache-control [![CircleCI](https://circleci.com/gh/tusbar/cache-control.svg?style=svg)](https://circleci.com/gh/tusbar/cache-control)

[![npm version](https://img.shields.io/npm/v/@tusbar/cache-control.svg)](https://www.npmjs.com/package/@tusbar/cache-control)
[![dependencies Status](https://david-dm.org/tusbar/cachecontrol/status.svg)](https://david-dm.org/tusbar/cachecontrol)
[![codecov](https://codecov.io/gh/tusbar/cache-control/branch/master/graph/badge.svg)](https://codecov.io/gh/tusbar/cache-control)
[![XO code style](https://img.shields.io/badge/code_style-XO-5ed9c7.svg)](https://github.com/sindresorhus/xo)

> Format and parse HTTP Cache-Control header

## Getting started

```bash
$ npm install @tusbar/cache-control
```

## API

This library exposes a `CacheControl` class and two shortcut methods: `parse()` and `format()`.

### `parse(header)`

```js
const {parse} = require('@tusbar/cache-control')
```

`parse()` takes `Cache-Control` HTTP header value and returns a `CacheControl` instance.

For example, `parse('max-age=31536000, public')` will return

```js
CacheControl {
  maxAge: 31536000,
  sharedMaxAge: null,
  maxStale: false,
  maxStaleDuration: null,
  minFresh: null,
  immutable: false,
  mustRevalidate: false,
  noCache: false,
  noStore: false,
  noTransform: false,
  onlyIfCached: false,
  private: false,
  proxyRevalidate: false,
  public: true }
```

### `format(cacheControl)`

```js
const {format} = require('@tusbar/cache-control')
```

`format()` takes a `CacheControl` instance (or similar object) and returns a `Cache-Control` HTTP header value.

For example, `format({maxAge: 31536000, public: true})` will return

```js
max-age=31536000, public
```

## Example usage

```js
res.setHeader('Cache-Control', format({
  public: true,
  immutable: true
}))
```

## FAQ

**Why another cache-control library?**

None of the existing libraries focus on just parsing the `Cache-Control` headers. There are some that expose Express (or connect-like) middlewares, and some unmaintained other ones that do rudimentary parsing of the header. The idea of this module is to parse the header according to the RFC with no further analysis or integration.


## See also

- [`cachecontrol`](https://github.com/pquerna/cachecontrol): Golang HTTP Cache-Control Parser and Interpretation


## License

MIT


## Miscellaneous

```
    ╚⊙ ⊙╝
  ╚═(███)═╝
 ╚═(███)═╝
╚═(███)═╝
 ╚═(███)═╝
  ╚═(███)═╝
   ╚═(███)═╝
```
