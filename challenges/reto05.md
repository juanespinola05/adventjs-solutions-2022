# Challenge #5

## 🎄 Optimizing Santa's trips

### 🟥 Hard

#### Watch [Live coding](https://youtu.be/TBueCOpgvFo)

### To not tire the reindeer, Papa Noel wants to leave the maximum number of gifts by making the least number of trips possible.

#### JavaScript

```js
function getMaxGifts(giftsCities, maxGifts, maxCities) {
  const getCombinations = (nums) => {
    if (nums.length === 0) return [];

    const subsets = [];
    subsets.push([], [nums[0]]);

    for (let i = 1; i < nums.length; i++) {
      const currentLength = subsets.length;
      for (var j = 0; j < currentLength; j++) {
        subsets.push([...subsets[j], nums[i]]);
      }
    }
    return subsets;
  };

  const addTotal = (combination) => {
    return combination.reduce((acc, curr) => acc + curr, 0);
  };

  const subsets = getCombinations(giftsCities);
  const totals = subsets.map(addTotal);

  let max = totals[0];
  for (let i = 1; i < totals.length; i++) {
    if (
      totals[i] <= maxGifts &&
      totals[i] > max &&
      subsets[i].length <= maxCities
    ) {
      max = totals[i];
      console.log(subsets[i]);
      continue;
    }
  }
  return max;
}
```

#### Typescript

```ts
function getMaxGifts(
  giftsCities: number[],
  maxGifts: number,
  maxCities: number
) {
  const getCombinations = (nums: number[]) => {
    if (nums.length === 0) return [];

    const subsets = [];
    subsets.push([], [nums[0]]);

    for (let i = 1; i < nums.length; i++) {
      const currentLength = subsets.length;
      for (var j = 0; j < currentLength; j++) {
        subsets.push([...subsets[j], nums[i]]);
      }
    }
    return subsets;
  };

  const addTotal = (combination: number[]) => {
    return combination.reduce((acc, curr) => acc + curr, 0);
  };

  const subsets = getCombinations(giftsCities);
  const totals = subsets.map(addTotal);

  let max = totals[0];
  for (let i = 1; i < totals.length; i++) {
    if (
      totals[i] <= maxGifts &&
      totals[i] > max &&
      subsets[i].length <= maxCities
    ) {
      max = totals[i];
      console.log(subsets[i]);
      continue;
    }
  }
  return max;
}
```

- [Go to challenge 5](https://adventjs.dev/challenges/2022/5)
- [Link al siguiente reto](./reto06.md)
