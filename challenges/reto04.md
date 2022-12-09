# Challenge #4

## 🎄 Box inside a box and another...

### 🟨 Medium

#### Watch [Live coding](https://youtu.be/mE0abqZt5RE)

### Santa Claus needs to review his gift boxes to make sure he can pack them all in his sleigh. He has a series of boxes of different sizes, characterized by their length, width, and height.

#### JavaScript
```js
function fitsInOneBox(boxes) {
  const sorted = boxes.sort((a,b) => a.l - b.l)
  const fits = sorted.every((box, i, array) => {
    if(i === array.length - 1) return true
    const values = Object.values(box)
    const nextValues = Object.values(array[i+1])
    const areMinor = values.every((item, i) => item < nextValues[i])
    return areMinor
  })
  return fits
}

```
#### Typescript
```ts
type Box = {
  l: number,
  w: number,
  h: number
}

type Boxes = Box[]

function fitsInOneBox(boxes: Boxes): boolean {
  const sorted = boxes.sort((a,b) => a.l - b.l)
  const fits = sorted.every((box, i, array) => {
    if(i === array.length - 1) return true
    const values = Object.values(box)
    const nextValues = Object.values(array[i+1])
    const areMinor = values.every((item, i) => item < nextValues[i])
    return areMinor
  })
  return fits
}

```

- [Go to challenge 4](https://adventjs.dev/challenges/2022/4)
- [Link al siguiente reto](./reto05.md)
