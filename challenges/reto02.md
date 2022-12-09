# Challenge #2

## 🎄 Nobady wants to do extra hours at work

### 🟩 Easy

#### Watch [Live coding](https://youtu.be/mE0abqZt5RE)

### A millionaire bought a social network, and he doesn't bring good news. He has announced that each time an employee misses a working day due to a holiday, they will have to compensate it with two extra hours another working day of the same year.

#### JavaScript
```js
function countHours(year, holidays) {
  let count = 0
  for(const holiday of holidays) {
    const date = new Date(year + "/" + holiday)
    const day = date.getDay()
    if(!(day === 0 || day === 6)) {
      count++
    }
  }
  
  return count * 2
}

```
#### Typescript
```ts
function countHours(year: number, holidays: string[]): number {
  let count = 0
  for(const holiday of holidays) {
    const date = new Date(year + "/" + holiday)
    const day = date.getDay()
    if(!(day === 0 || day === 6)) {
      count++
    }
  }
  
  return count * 2
}

```

- [Go to challenge 2](https://adventjs.dev/challenges/2022/2)
- [Link al siguiente reto](./reto03.md)
