# polyhash

Generate an array of
[geohashes](http://en.wikipedia.org/wiki/Geohash)
that completely contains a polygon.

[![build status](https://secure.travis-ci.org/substack/polyhash.png)](http://travis-ci.org/substack/polyhash)

# example

``` js
var polyhash = require('polyhash');
var polygon = [
    [ 37.96, -122.45 ],
    [ 37.95, -122.90 ],
    [ 38.21, -122.62 ]
];
var hashes = polyhash(polygon, 4);
console.dir(hashes);
```

***

```
[ '9q8x', '9q8z', '9qb8', '9qbb' ]
```

# methods

``` js
var polyhash = require('polyhash')
```

## polyhash(polygon, level)

Return an array of [geohashes](http://en.wikipedia.org/wiki/Geohash)
that completely contains the array of points described by `polygon`.

Points are of the form `[ lat, lon ]`.

The `level` provided is the maximum hash resolution which is also the maximum
string length of the geohash entries.

At the maximum geohash resolution `level`, hashes that are partially intersected
will be counted. All other levels recurse down to sublevels until a completely
contained hash is found.

# install

With [npm](http://npmjs.org) do:

```
npm install polyhash
```

# license

MIT
