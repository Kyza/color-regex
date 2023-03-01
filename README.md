# Color RegEx

Pattern matching and extracting color code formats using RegEx.

Written in [Pomsky](https://pomsky-lang.org).

- [Source](/full.pom)
- [Compiled](/full.reg)

## Support

- [x] [Hexadecimal](https://w3c.github.io/csswg-drafts/css-color/#hex-color)
- [x] [RGB](https://w3c.github.io/csswg-drafts/css-color/#funcdef-rgb) / [RGBA](https://w3c.github.io/csswg-drafts/css-color/#funcdef-rgba)
- [ ] [COLOR](https://w3c.github.io/csswg-drafts/css-color/#funcdef-color)
- [x] [HSL](https://w3c.github.io/csswg-drafts/css-color/#funcdef-hsl) / [HSLA](https://w3c.github.io/csswg-drafts/css-color/#funcdef-hsla)
- [x] [HWB](https://w3c.github.io/csswg-drafts/css-color/#funcdef-hwb)
- [x] [LAB](https://w3c.github.io/csswg-drafts/css-color/#funcdef-lab) / [OKLAB](https://w3c.github.io/csswg-drafts/css-color/#funcdef-oklab)
- [x] [LCH](https://w3c.github.io/csswg-drafts/css-color/#funcdef-lch) / [OKLCH](https://w3c.github.io/csswg-drafts/css-color/#funcdef-oklch)

## Blocks Example

<BlockComponent
block={{"owner":"Kyza","repo":"blocks","id":"pomsky-viewer","type":"file"}}
context={{"owner":"Kyza","repo":"color-regex","path":"full.pom","sha":"master","file":"README.md"}}
height={500}
/>

## Playground

- [Pomsky](https://playground.pomsky-lang.org/?text=)
- [Regex101](https://regex101.com/r/nYVb24/)

## Usage

It always matches `{3,4}` unnamed groups. Those groups are the color type, then the color values. The rest will be undefined.

Just filter out the undefined values and you'll have an array of the values you want.

```js
"rgb(255, 255, 255)".match(regex).filter((item) => item != null)
```

## Why?

For fun and to demonstrate Pomsky's power of making complex regular expressions that are still readable.
