# Color RegEx

Pattern matching and extracting color code formats using RegEx.

Written in [Pomsky](https://pomsky-lang.org).

- [Source](/full.pom)
- [Compiled](/full.reg)

## Support

- [x] Hexadecimal
  - [x] `#FFF` 3 length
  - [x] `#FFFF` 4 length
  - [x] `#FFFFFF` 6 length
  - [x] `#FFFFFFFF` 8 length
- [x] RGB / RGBA
  - [x] `rgb()` and `rgba()` work the same
  - [x] `rgb(255, 255, 255)`
  - [x] `rgb(255 255 255)`
  - [x] `rgb(255, 255, 255, 1)`
  - [x] `rgb(255 255 255 / 1)`
  - [x] `rgb(100%, 100%, 100%, 100%)`
- [ ] COLOR
- [ ] HSL / HSLA
- [ ] HWB
- [ ] LAB
- [ ] LCH
- [ ] OKLAB
- [ ] OKLCH
  
## Playground

- [Pomsky](https://playground.pomsky-lang.org/?text=)
- [Regex101](https://regex101.com/r/nYVb24/)

## Usage

It always matches `[3-4]` unnamed groups. Those groups are the color type, then the color values. The rest will be undefined.

Just filter out the undefined values and you'll have an array of the values you want.

```js
"rgb(255, 255, 255)".match(regex).filter((item) => item != null)
```

## Why?

For fun and to demonstrate Pomsky's power of making complex regular expressions that are still readable.
