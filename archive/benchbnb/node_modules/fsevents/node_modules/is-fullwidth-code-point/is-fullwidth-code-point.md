# is-fullwidth-code-point

> Check if the character represented by a given [Unicode code point](https://en.wikipedia.org/wiki/Code_point) is [fullwidth](https://en.wikipedia.org/wiki/Halfwidth_and_fullwidth_forms)

## Install

```text
$ npm install --save is-fullwidth-code-point
```

## Usage

```javascript
var isFullwidthCodePoint = require('is-fullwidth-code-point');

isFullwidthCodePoint('谢'.codePointAt());
//=> true

isFullwidthCodePoint('a'.codePointAt());
//=> false
```

## API

### isFullwidthCodePoint\(input\)

#### input

Type: `number`

[Code point](https://en.wikipedia.org/wiki/Code_point) of a character.

## License

MIT © [Sindre Sorhus](http://sindresorhus.com)

