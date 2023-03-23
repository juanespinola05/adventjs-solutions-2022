# Challenge #7

## 🎄 Doing gifts inventory

### 🟩 Easy

#### Watch [Live coding](https://youtu.be/mE0abqZt5RE)

### In the Santa Claus stores they are doing inventory. There are three stores (which is represented as an Array each). In each store there are gifts.

#### JavaScript

##### First solution

```js
function getGiftsToRefill(a1, a2, a3) {
  const countDuplicates = (array, target) => {
    return array.filter((i) => i === target).length;
  };
  const stores = [...new Set(a1), ...new Set(a2), ...new Set(a3)];
  const gifts = [...new Set(stores)];
  return gifts.filter((gift) => countDuplicates(stores, gift) === 1);
}
```

#### Typescript

```ts
type Store = string[];

function getGiftsToRefill(a1: Store, a2: Store, a3: Store): string[] {
  const countDuplicates = (array: Store, target: string) => {
    return array.filter((i) => i === target).length;
  };
  const stores = [...new Set(a1), ...new Set(a2), ...new Set(a3)];
  const gifts = [...new Set(stores)];
  return gifts.filter((gift) => countDuplicates(stores, gift) === 1);
}
```

- [Go to challenge 7](https://adventjs.dev/challenges/2022/7)
- [Link al siguiente reto](./reto08.md)
