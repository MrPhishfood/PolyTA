# closest-bower

[![dependency Status](https://david-dm.org/se-panfilov/closest-bower/status.svg?branch=master)](https://david-dm.org/se-panfilov/closest-bower#info=Dependencies)
[![devDependency Status](https://david-dm.org/se-panfilov/closest-bower/dev-status.svg?branch=master)](https://david-dm.org/se-panfilov/closest-bower#info=devDependencies)
[![npm version](https://badge.fury.io/js/closest-bower.svg)](http://badge.fury.io/js/closest-bower)
[![npm](https://img.shields.io/npm/l/express.svg)](https://github.com/se-panfilov/closest-bower/blob/master/LICENSE.md)

Find the closest bower.json file meeting specific criteria by searching
upwards from a given directory until hitting root.

**Based** on [https://github.com/hughsk/closest-package][1] - Find the closest **package.json**

## Usage

[![NPM](https://nodei.co/npm/closest-bower.png)](https://nodei.co/npm/closest-bower/)

### `closest(dir, [filter], found(err, file))`

Given a starting directory `dir`, look up through every directory to see if
it contains a `bower.json` file matching the `filter` function, for example:

``` javascript
closest(__dirname, function(json, filename) {
  return json.name === 'async'
}, function(err, file) {
  console.log(file)
})
```

Note that `filter` is optional and takes the following arguments:

* `json`: the parsed `bower.json` file.
* `filename`: the `bower.json`'s absolute filename.

### `file = closest.sync(dir, [filter])`

Same as the `closest` function, however executed synchronously:

``` javascript
var result = closest.sync(__dirname, function(json, filename) {
  return json.name === 'async'
})

console.log(result)
```

## License

MIT. See [LICENSE.md](http://github.com/hughsk/closest-bower/blob/master/LICENSE.md) for details.

[1]: https://github.com/hughsk/closest-package

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/se-panfilov/closest-bower/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

