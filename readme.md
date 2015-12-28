## posthtml-px2rem

[![NPM Version](http://img.shields.io/npm/v/posthtml-px2rem.svg?style=flat)](https://www.npmjs.com/package/posthtml-px2rem "Package version") 
[![devDependencies](https://img.shields.io/david/dev/weixin/posthtml-px2rem.svg)](https://ci.appveyor.com/project/weixin/posthtml-px2rem "devDependencies") 
[![NPM Downloads](https://img.shields.io/npm/dm/posthtml-px2rem.svg?style=flat)](https://www.npmjs.com/package/posthtml-px2rem "NPM Downloads") 

[![Join the chat at https://gitter.im/weixin/posthtml-px2rem](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/TmT?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![TmT Name](https://img.shields.io/badge/Team-TmT-brightgreen.svg?style=flat)](https://github.com/orgs/TmT/people "Tencent Moe Team") 
[![License](https://img.shields.io/npm/l/posthtml-px2rem.svg?style=flat)](http://opensource.org/licenses/MIT "Feel free to contribute.") 
[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/weixin/posthtml-px2rem/trend.png)](https://bitdeli.com/free "GitHub Analyze")

> Change px to rem in HTML inline CSS based on PostHTML

**NPM Home Page:** [https://www.npmjs.com/package/posthtml-px2rem](https://www.npmjs.com/package/posthtml-px2rem)

## Install

Install with [NPM](https://npmjs.org/):

```javascript
npm install posthtml-px2rem --save
```

## Usage

**gulpfile.js**

```javascript
var posthtml = require('gulp-posthtml');
var posthtmlPx2rem = require('posthtml-px2rem');

gulp.src(paths.src.html)
.pipe(posthtml(posthtmlPx2rem({rootValue: 20, minPixelValue: 2})))
.pipe(gulp.dest(paths.dist.dir));

```

**Options**  

```javascript
options = lodash.extend({
    rootValue: 16, // root font-size on <html>
    unitPrecision: 5, // numbers after `.`
    minPixelValue: 0 // set it 2 if you want to ignore value like 1px & -1px
}, options)
```

## Result

**HTML In** (Type 1)


```css
<style>
.test {
    font-size: 10PX;
    width: 20px;
    margin: 30px 40px 50px 60px;
    border: 1px solid #fff;
}
</style>
```

**HTML Out**

```html
<style>
.test {
	font-size: 10PX;
    width: 1rem;
    margin: 1.5rem 2rem 2.5rem 3rem;
    border: 1px solid #fff
}
</style>
```

**HTML In** (Type 2)


```html
<div style="font-size: 10PX; width: 20px; margin: 30px 40px 50px 60px; border: 1px solid #fff;">
    test
</div>
```

**HTML Out**

```html
<div style="font-size: 10PX; width: 1rem; margin: 1.5rem 2rem 2.5rem 3rem; border: 1px solid #fff;">
    test
</div>
```

## Notes

* Ignoring `rem` replacement using `PX` `Px`, like `123PX` not `123px`.
* Set `minPixelValue : 2` will ignore all the value `1px` & `-1.2px`

## Contributing

This repo is build and maintained by [TmT Team](https://github.com/orgs/TmT/people).  
If you get any bugs or feature requests, please open a new [Issue](https://github.com/weixin/posthtml-px2rem/issues) or send us [Pull Request](https://github.com/weixin/posthtml-px2rem/pulls), Thank you for your contributions.
