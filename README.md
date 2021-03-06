# Noto-color-emoji

A node module which makes it easier to play with [noto-color-emoji](https://github.com/googlefonts/noto-emoji) fonts

## Example Usage

```bash
$ npm i noto-color-emoji require-style
$ npm i yo-yo
```

```js
var requireStyle = require('require-style')
var html = require('yo-yo')

var style = html`
  <style>
    ${requireStyle('noto-color-emoji')} 

    body {
      font-family: arial, NotoColorEmoji;
    }
  </style>
`
document.head.appendChild(style)


var hello = html`
  <h1>Hello Noto! </h1>
`
document.body.appendChild(hello)
```

Notes :
- order of fonts in `font-family` css matters. I recommend you make `NotoColorEmoji` a fallback (as in example), otherwise it will try to take over all your fonts
- this "just works" in electron apps, but for bundled apps read `require-style` documentation about bundling transforms.
