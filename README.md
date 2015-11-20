# ignore-styles

[![Version][version-svg]][package-url] [![Build Status][travis-svg]][travis-url] [![License][license-image]][license-url] [![Downloads][downloads-image]][downloads-url]

A `babel/register` style hook to ignore style imports when running in Node. This
is for projects that use something like Webpack to enable CSS imports in
JavaScript. When you try to run the project in Node (to test in Mocha, for
example) you'll see errors like this:

    SyntaxError: /Users/brandon/code/my-project/src/components/my-component/style.sass: Unexpected token (1:0)
    > 1 | .title
    | ^
    2 |   font-family: serif
    3 |   font-size: 10em
    4 |

To resolve this, require `ignore-styles` with your mocha tests:

    mocha --require ignore-styles

See [DEFAULT_EXTENSIONS][default-extensions] for the full list of extensions
ignored, and send a pull request if you need more.

## More Examples

To use this with multiple Mocha requires:

    mocha --require babel-register --require ignore-styles

You can also use it just like `babel/register`:

```javascript
    import 'ignore-styles'
```

In ES5:

```javascript
    require('ignore-styles')
```

To customize the extensions used:

```javascript
    import register from 'ignore-styles'
    register(['.sass', '.scss'])
```

To customize the extensions in ES5:

```javascript
    require('ignore-styles')(['.sass', '.scss'])
```

Enjoy!

[travis-svg]: https://img.shields.io/travis/bkonkle/ignore-styles/master.svg?style=flat-square
[travis-url]: https://travis-ci.org/bkonkle/ignore-styles
[license-image]: http://img.shields.io/badge/license-MIT-green.svg?style=flat-square
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/ignore-styles.svg?style=flat-square
[downloads-url]: http://npm-stat.com/charts.html?package=ignore-styles
[version-svg]: https://img.shields.io/npm/v/ignore-styles.svg?style=flat-square
[package-url]: https://npmjs.org/package/ignore-styles
[default-extensions]: https://github.com/bkonkle/ignore-styles/blob/master/ignore-styles.js#L1
