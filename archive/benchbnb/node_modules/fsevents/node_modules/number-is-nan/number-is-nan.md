# number-is-nan

> ES2015 [`Number.isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN) [ponyfill](https://ponyfill.com)

## Install

```text
$ npm install --save number-is-nan
```

## Usage

```javascript
var numberIsNan = require('number-is-nan');

numberIsNan(NaN);
//=> true

numberIsNan('unicorn');
//=> false
```

## License

MIT © [Sindre Sorhus](http://sindresorhus.com)

