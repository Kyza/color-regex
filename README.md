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
- [x] RGBA
  - [x] `rgb()` and `rgba()` work the same
  - [x] `rgb(255, 255, 255)`
  - [x] `rgb(255 255 255)`
  - [x] `rgb(255, 255, 255, 1)`
  - [x] `rgb(255 255 255 / 1)`
  - [x] `rgb(100%, 100%, 100%, 100%)`
- [ ] COLOR
- [ ] HSL
- [ ] HSV
- [ ] HWB
- [ ] LCH
- [ ] OKLCH
  
## Playground

- [Pomsky](https://playground.pomsky-lang.org/?text=let%20x%20%3D%20%5Bascii_xdigit%5D%3B%0A%0Alet%20decimal_end%20%3D%20(%22.%22%20%5B%220%22-%229%22%5D%2B)%3B%0Alet%20zero_decimal_end%20%3D%20(%22.%22%20%220%22%2B)%3B%0A%0Alet%20eight_bit_number%20%3D%20(%0A%20%20%23%200.0%20-%20255.0%0A%20%20range%20%220%22-%22254%22%20decimal_end%3F%0A%20%20%7C%0A%20%20%22255%22%20zero_decimal_end%3F%0A%20%20%7C%0A%20%20%23%20.0%0A%20%20decimal_end%0A)%3B%0A%0Alet%20zero_one_decimal%20%3D%20(%0A%20%20%23%200.0%20-%200.99%0A%20%20(%220%22%2B)%3F%20decimal_end%3F%0A%20%20%7C%0A%20%20%23%201%201.0%0A%20%20%221%22%20zero_decimal_end%3F%0A%20%20%7C%0A%20%20%23%20.0%0A%20%20decimal_end%0A)%3B%0A%0Alet%20percent_number%20%3D%20(%0A%20%20%23%200.0%25%20-%20100.0%25%0A%20%20(%0A%20%20%20%20range%20%220%22-%2299%22%20decimal_end%3F%0A%20%20%20%20%7C%0A%20%20%20%20%22100%22%20zero_decimal_end%3F%0A%20%20%20%20%7C%0A%20%20%20%20%23%20.0%0A%20%20%20%20decimal_end%0A%20%20)%20%22%25%22%0A)%3B%0A%0Alet%20comma_sep%20%3D%20%5Bs%5D*%20%22%2C%22%20%5Bs%5D*%3B%0Alet%20slash_sep%20%3D%20%5Bs%5D*%20(regex%20%22%5C%5C%2F%22)%20%5Bs%5D*%3B%0A%0A(%0A%20%20%23%20Hex%0A%20%20%3A(%22%23%22)%20(%0A%20%20%20%20%23%206%20and%208%20long%0A%20%20%20%20%3A(x%7B2%7D)%20%3A(x%7B2%7D)%20%3A(x%7B2%7D)%20%3A(x%7B2%7D)%3F%0A%20%20%20%20%7C%0A%20%20%20%20%23%203%20and%204%20long%0A%20%20%20%20%3A(x%7B1%7D)%20%3A(x%7B1%7D)%20%3A(x%7B1%7D)%20%3A(x%7B1%7D)%3F%0A%20%20)%0A%20%20%7C%0A%20%20%23%20RGBA%0A%20%20%3A(%22rgb%22%20%7C%20%22rgba%22)%20%22(%22%20(%0A%20%20%20%20%23%20Percents%20and%208bit%20can%27t%20be%20mixed%0A%20%20%20%20(%0A%20%20%20%20%20%20%23%20Commas%20and%20no%20commas%2C%20choose%0A%20%20%20%20%20%20%23%20rgb(255%2C%20255%2C%20255%2C%201)%0A%20%20%20%20%20%20(%0A%20%20%20%20%20%20%20%20%5Bs%5D*%20%3A(eight_bit_number)%20comma_sep%20%3A(eight_bit_number)%20comma_sep%20%3A(eight_bit_number)%20(comma_sep%20%3A(zero_one_decimal%20%7C%20percent_number))%3F%20%5Bs%5D*%0A%20%20%20%20%20%20%20%20%7C%0A%20%20%20%20%20%20%20%20%5Bs%5D*%20%3A(eight_bit_number)%20%5Bs%5D%2B%20%3A(eight_bit_number)%20%5Bs%5D%2B%20%3A(eight_bit_number)%20(%5Bs%5D%2B%20%3A(zero_one_decimal%20%7C%20percent_number))%3F%20%5Bs%5D*%0A%20%20%20%20%20%20)%0A%20%20%20%20%20%20%7C%0A%20%20%20%20%20%20%23%20Commas%20and%20no%20commas%2C%20choose%0A%20%20%20%20%20%20%23%20rgb(100%25%2C%20100%25%2C%20100%25%2C%201)%0A%20%20%20%20%20%20(%0A%20%20%20%20%20%20%20%20%5Bs%5D*%20%3A(percent_number)%20comma_sep%20%3A(percent_number)%20comma_sep%20%3A(percent_number)%20(comma_sep%20%3A(zero_one_decimal%20%7C%20percent_number))%3F%20%5Bs%5D*%0A%20%20%20%20%20%20%20%20%7C%0A%20%20%20%20%20%20%20%20%5Bs%5D*%20%3A(percent_number)%20%5Bs%5D%2B%20%3A(percent_number)%20%5Bs%5D%2B%20%3A(percent_number)%20(%5Bs%5D%2B%20%3A(zero_one_decimal%20%7C%20percent_number))%3F%20%5Bs%5D*%0A%20%20%20%20%20%20)%0A%20%20%20%20%20%20%7C%0A%20%20%20%20%20%20%23%20At%20least%20one%20space%20required%0A%20%20%20%20%20%20%23%20Commas%20can%27t%20be%20used%20here%0A%20%20%20%20%20%20%23%20rgb(255%20255%20255%20%2F%201)%0A%20%20%20%20%20%20%5Bs%5D*%20%3A(eight_bit_number)%20%5Bs%5D%2B%20%3A(eight_bit_number)%20%5Bs%5D%2B%20%3A(eight_bit_number)%20(slash_sep%20%3A(zero_one_decimal%20%7C%20percent_number))%3F%20%5Bs%5D*%0A%20%20%20%20%20%20%7C%0A%20%20%20%20%20%20%23%20At%20least%20one%20space%20required%0A%20%20%20%20%20%20%23%20Commas%20can%27t%20be%20used%20here%0A%20%20%20%20%20%20%23%20rgb(100%25%20100%25%20100%25%20%2F%201)%0A%20%20%20%20%20%20%5Bs%5D*%20%3A(percent_number)%20%5Bs%5D%2B%20%3A(percent_number)%20%5Bs%5D%2B%20%3A(percent_number)%20(slash_sep%20%3A(zero_one_decimal%20%7C%20percent_number))%3F%20%5Bs%5D*%0A%20%20%20%20)%0A%20%20)%20%22)%22%0A)%0A)
- [Regex101](https://regex101.com/r/nYVb24/)

## Usage

It always matches `[3-4]` unnamed groups. Those groups are the color type, then the color values. The rest will be undefined.

Just filter out the undefined values and you'll have an array of the values you want.

```js
"rgb(255, 255, 255)".match(regex).filter((item) => item != null)
```

## Why?

For fun and to demonstrate Pomsky's power of making complex regular expressions that are still readable.
