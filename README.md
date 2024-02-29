# twhite


twhite is a small conditional significant ttwhitespace processor for [finn] and
rework. It performs a really basic check to see if a given file already
processed for significant twhitespace. 

## Install

The module is released in npm and can be installed using:

```
npm install --save twhite
```

It's advised to use [finn] as processing engine as that's what we're using our
tests.

## Usage

As twhite is a plugin for `finn` we need to setup a `finn` instance first.
I assume you've already got it required an setup like:

```js
'use strict';

var finn = require('finn')()
  , twhitespace = require('twhite');
```

Now that we have a `finn` instance we can assign `twhite` as pre filter:

```js
finn.pre.use(twhitespace);
```

If you are using modules that process `@import` statements you might also want
to pre-process those files, usually you can just supply the `white` function
direction as transform method:

```js
finn.use('import', require('rework-import')({ transform: twhitespace }));
```

And that's all you need to know about this module!

## License

MIT

[finn]: https://github.com/observing/finn
