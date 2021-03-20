# fast-blurhash

> Fast & tiny [Wolt BlurHash](https://github.com/woltapp/blurhash) algorithm decoder implementation

- < 1kb minified
- up to 50% faster then [original `blurhash.decode`](https://github.com/woltapp/blurhash/tree/master/TypeScript#decodeblurhash-string-width-number-height-number-punch-number--uint8clampedarray) (see [benchmark](./benchmark.js))
## Install

```sh
npm install --save fast-blurhash
```

## API

`fast-blurhash` provides a drop-in replacement for [original `blurhash.decode`](https://github.com/woltapp/blurhash/tree/master/TypeScript#decodeblurhash-string-width-number-height-number-punch-number--uint8clampedarray)
```typescript
decode(blurhash: string, width: number, height: number, punch?: number) => Uint8ClampedArray`
```

> Decodes a blurhash string to pixels

#### Example

```js
import { decode } from "blurhash";

const pixels = decode("LEHV6nWB2yk8pyo0adR*.7kCMdnj", 32, 32);

const canvas = document.createElement("canvas");
const ctx = canvas.getContext("2d");
const imageData = ctx.createImageData(width, height);
imageData.data.set(pixels);
ctx.putImageData(imageData, 0, 0);
document.body.append(canvas);
```