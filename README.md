# grunt-custom-coffee
[![Build Status](https://secure.travis-ci.org/stu-salsbury/grunt-custom-coffee.png?branch=master)](http://travis-ci.org/stu-salsbury/grunt-custom-coffee)
[![Dependency Status](https://gemnasium.com/stu-salsbury/grunt-custom-coffee.png)](https://gemnasium.com/stu-salsbury/grunt-custom-coffee)

> Compile CoffeeScript files to JavaScript -- **you bring the compiler!**


## About
This plugin is a copy of <a href="https://github.com/gruntjs/grunt-contrib-coffee" target="_blank">
grunt-contrib-coffee</a> with *one difference*:

```javascript
      return (options['compiler'] || require('coffee-script')).compile(code, options);
```
That line from the task file allows you to provide your own "CoffeeScript" compiler.

Most of the time, you would use this task to gain control of the version of CoffeeScript that is
used to compile your .coffee or .litcoffee files.  For instance, you may require a specific version,
or you may require a customized compiler, such as the <a href="">hleumas fork</a> which
has additional support for Google Closure Library.  It doesn't really matter what you specify as
your compiler as long as it does what you want when you call compile(code, options) on it. :)

Please see the <a href="https://github.com/gruntjs/grunt-contrib-coffee" target="_blank">
grunt-contrib-coffee</a> task for full documentation.  The only difference here is that you may
use the `compiler` option to override the default compiler:

## compiler
Type: `object`
Default: `undefined`

If provided, the compiler is expected to be an instance of the npm package 'coffee-script' or something
that behaves as if it were.  This can be used to build with an alternate version of coffee-script or to
build with a fork of coffee-script.  Typically, the user will specify the compiler using `compiler: require('coffee-script')` where an alternate version of coffee-script has been specified by the package as
a direct dependency.

## Release History

 * 2013-10-01   v0.0.1   Initial release -- equivalent to grunt-contrib-coffee v0.7.0.
