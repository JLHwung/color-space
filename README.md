# color-space [![Build Status](https://travis-ci.org/dfcreative/color-space.svg?branch=master)](https://travis-ci.org/dfcreative/color-space)

Math and data behind color spaces and conversions, nothing more. Initially fork of [color-convert](https://github.com/harthur/color-convert), separated into a standalone package due to [reasons](#differences-with-color-convert).

[![NPM](https://nodei.co/npm/color-space.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/color-space/)



## Use

`$ npm install color-space`

Use [browserify](https://github.com/substack/node-browserify) for browser use.

```js
var space = require('color-space');

//convert rgb to lch
space.rgb.lch([200,230,100]);
```

## API

Convert from one space to another:

```js
space.fromSpace.toSpace(array);
```

Space meta data:

```js
space.min //channel minimums
space.max //channel maximums
space.channel //channel names
space.alias //alias space names, if any
```

Available spaces:

* rgb
* hsl
* hsv (hsb)
* hwb
* cmyk
* xyz
* lab
* lch


Don’t be shy to `console.log(space)` to see the details.



## Differences with color-convert

* no keyword "space": actually, it is not a space, it is a different kind of knowledge. Also extra bytes saved.
* no wrapper code: you have a natural wrapper already — [harthur/color](https://github.com/harthur/color) or faster fork [dfcreative/color](https://github.com/dfcreative/color).
* conversions.js are placed to index.js for better use.
* CIE spaces. (pending)
* HUSL spaces (great thanks to Alexei Boronine for his [HUSL](https://github.com/boronine/husl).
* Minimums, maximums, channel names and aliases info.
* Better structured, easier exported (esp. for webworkers).
* No result rounding — one can always do it oneself.


# Contribute

Please fork, add conversions, figure out color profile stuff for XYZ, LAB, etc. This is meant to be a basic library that can be used by other libraries to wrap color calculations in some cool way.



<a href="http://unlicense.org/UNLICENSE"><img src="http://upload.wikimedia.org/wikipedia/commons/6/62/PD-icon.svg" width="40"/></a>