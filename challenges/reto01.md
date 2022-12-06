# Challenge #1

## 🎄 Automating Christmas gift wrapping!

### 🟩 Easy

### The elves bought a gift-wrapping machine this year. But it's not programmed! We need to create an algorithm that helps it in the task.

#### JavaScript
```js
function wrapping(gifts) {
  const wrapped= []
  for(const gift of gifts) {
    let paper = "*".repeat(gift.length + 2)
    let regalo = `${paper}\n*${gift}*\n${paper}`;
    wrapped.push(regalo)
  }
  return wrapped
}

```
#### Typescript
```ts
function wrapping(gifts: string[]): string[] {
  const wrapped: string[] = []
  for(const gift of gifts) {
    let paper = "*".repeat(gift.length + 2)
    let regalo = `${paper}\n*${gift}*\n${paper}`;
    wrapped.push(regalo)
  }
  return wrapped
}

```

- [Go to challenge 1](https://adventjs.dev/challenges/2022/1)
<!-- - [Link al siguiente reto](./reto1.md) -->
