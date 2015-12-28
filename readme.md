## posthtml-px2rem

[![NPM Version](http://img.shields.io/npm/v/posthtml-px2rem.svg?style=flat)](https://www.npmjs.com/package/posthtml-px2rem "Package version") 
[![devDependencies](https://img.shields.io/david/dev/weixin/posthtml-px2rem.svg)](https://ci.appveyor.com/project/weixin/posthtml-px2rem "devDependencies") 
[![NPM Downloads](https://img.shields.io/npm/dm/posthtml-px2rem.svg?style=flat)](https://www.npmjs.com/package/posthtml-px2rem "NPM Downloads") 

[![Join the chat at https://gitter.im/weixin/posthtml-px2rem](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/TmT?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![TmT Name](https://img.shields.io/badge/Team-TmT-brightgreen.svg?style=flat)](https://github.com/orgs/TmT/people "Tencent Moe Team") 
[![License](https://img.shields.io/npm/l/posthtml-px2rem.svg?style=flat)](http://opensource.org/licenses/MIT "Feel free to contribute.") 
[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/weixin/posthtml-px2rem/trend.png)](https://bitdeli.com/free "GitHub Analyze")

> Be lazy, add images's CSS automatically, like `width` & `height` and more.    
> Save time, make money.

**NPM Home Page:** [https://www.npmjs.com/package/posthtml-px2rem](https://www.npmjs.com/package/posthtml-px2rem)

## Install

Install with [NPM](https://npmjs.org/):

```javascript
npm install posthtml-px2rem --save
```

## Usage

**gulpfile.js**

```javascript
var px2rem = require('posthtml-px2rem');

gulp.src(paths.src.less)
    .pipe(less())
    .pipe(px2rem())
    .pipe(gulp.dest(paths.src.css));
        	
```

**Options**  
Set CSS which you wish to be added automatically.

```javascript
options = lodash.extend({
    width: true,
    height: true,
    backgroundSize: true, 
    slice: '../slice' // Set slice image path
}, options);
```

## Result

**CSS In**


```css
.icon-test {
	background-image: url(../slice/test.png);
}
```

**CSS Out**

```css
.icon-test {
	width: 32px;
	height: 66px;
	background-image: url(../slice/test.png);
	background-size: 32px;
}
```

_Tips: Use [PostCSS](https://github.com/postcss/postcss) with the `CSS Out` if needed._

## Notes

* Get image size from `HEX` data from file buffer via [fast-image-size](https://github.com/Ziv-Barber/fast-image-size), more fast now.
* Detect `PNG` & `JPG` based on [file signatures](https://en.wikipedia.org/wiki/List_of_file_signatures)
* No minimum image buffer size limited now [/fast-image-size/pull/5](https://github.com/Ziv-Barber/fast-image-size/pull/5).

## Contributing

This repo is build and maintained by [TmT Team](https://github.com/orgs/TmT/people).  
If you get any bugs or feature requests, please open a new [Issue](https://github.com/weixin/posthtml-px2rem/issues) or send us [Pull Request](https://github.com/weixin/posthtml-px2rem/pulls), Thank you for your contributions.
