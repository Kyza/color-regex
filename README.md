# Color RegEx

Pattern matching and extracting color code formats using RegEx.

Written in [Pomsky](https://pomsky-lang.org).

- [Source](/index.pom)
- [Compiled](/index.reg)

## Support

- [x] [Hexadecimal](https://w3c.github.io/csswg-drafts/css-color/#hex-color)
- [x] [RGB](https://w3c.github.io/csswg-drafts/css-color/#funcdef-rgb) / [RGBA](https://w3c.github.io/csswg-drafts/css-color/#funcdef-rgba)
- [x] [COLOR](https://w3c.github.io/csswg-drafts/css-color/#funcdef-color)
- [x] [HSL](https://w3c.github.io/csswg-drafts/css-color/#funcdef-hsl) / [HSLA](https://w3c.github.io/csswg-drafts/css-color/#funcdef-hsla)
- [x] [HWB](https://w3c.github.io/csswg-drafts/css-color/#funcdef-hwb)
- [x] [LAB](https://w3c.github.io/csswg-drafts/css-color/#funcdef-lab) / [OKLAB](https://w3c.github.io/csswg-drafts/css-color/#funcdef-oklab)
- [x] [LCH](https://w3c.github.io/csswg-drafts/css-color/#funcdef-lch) / [OKLCH](https://w3c.github.io/csswg-drafts/css-color/#funcdef-oklch)
- [x] [\<named-color\>](https://w3c.github.io/csswg-drafts/css-color/#named-colors)
- [x] [\<system-color\>](https://w3c.github.io/csswg-drafts/css-color/#css-system-colors)
- [x] [currentColor](https://w3c.github.io/csswg-drafts/css-color/#currentcolor-color)

## [Blocks Example](https://blocks.githubnext.com/Kyza/color-regex/blob/trunk/README.md)

<BlockComponent
block={{"owner":"Kyza","repo":"blocks","id":"pomsky-viewer","type":"file"}}
context={{"owner":"Kyza","repo":"color-regex","path":"full.pom","sha":"master","file":"README.md"}}
height={500}
/>

## Playground

- [Pomsky](https://playground.pomsky-lang.org/?text=)
- [Regex101](https://regex101.com/r/nYVb24/)

## Usage

It always matches 1, 3, 4, or 5 unnamed groups.

### 1

This group will be the name of the color alias such as `red` or `papayawhip`.

### 3-5

These groups are the color type, then the color values.

OR

These groups are `"color"`, the color type, then the color values.

### Usage

Just filter out the undefined values and you'll have an array of the values you want.

```js
"rgb(255, 255, 255)".match(regex).filter((item) => item != null)
```

## Why?

For fun and to demonstrate Pomsky's power of making complex regular expressions that are still readable.
