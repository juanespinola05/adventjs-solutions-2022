# Challenge #3

## 🎄 How many packs of gifts can Santa carry?

### 🟩 Easy

#### Watch [Live coding](https://youtu.be/pV0v6mCNPZE)

### You receive a Christmas gifts pack that Santa Claus wants to deliver to the children. Each gift inside the pack is represented by a string and it has a weight equal to the number of letters in its name. Santa Claus's sleigh can only carry a weight limit.

#### JavaScript
```js
function distributeGifts(packOfGifts, reindeers) {
  const packWeight = packOfGifts.reduce((acc, curr) => acc + curr.length, 0)
  const reindeersLimit = reindeers.reduce((acc, curr) => acc + curr.length * 2, 0)
	const resto = reindeersLimit % packWeight
  const amount = (reindeersLimit - resto) / packWeight
  
  return amount
}

```
#### Typescript
```ts
function distributeGifts(packOfGifts: Array<string>, reindeers: Array<string>): number {
  const packWeight = packOfGifts.reduce((acc, curr) => acc + curr.length, 0)
  const reindeersLimit = reindeers.reduce((acc, curr) => acc + curr.length * 2, 0)
	const resto = reindeersLimit % packWeight
  const amount = (reindeersLimit - resto) / packWeight
  
  return amount
}

```

- [Go to challenge 3](https://adventjs.dev/challenges/2022/3)
- [Link al siguiente reto](./reto04.md)
