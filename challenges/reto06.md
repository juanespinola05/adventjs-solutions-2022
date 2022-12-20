# Challenge #6

## 🎄 Creating Xmas decorations

### 🟨 Medium

#### Watch [Live coding](https://youtu.be/mE0abqZt5RE)

### A couple of Christmas enthusiasts have created a Christmas decoration company. The first decoration they want to manufacture is a cube that is placed on the trees.

#### JavaScript
##### First solution
```js
function createCube(size) {
  const barras = ["/", "\\"]
  const up = "\\_".repeat(size) + "\\"
  const down = "/_".repeat(size) + "/"
  
  let upperCube = Array.from({ length: size }, () => '')
  for(let i = 0; i < size; i++) {
    const amount = i + i + 1
    upperCube[i] += " ".repeat(size - i - 1)
    for(let k = 0; k < amount; k++) {
      upperCube[i] += k % 2 === 0 ? barras[0] : barras[1]
    }
    upperCube[i] += up
  }
  
  const lowerCube = upperCube.map(line => {
    const array = Array.from(line, (ch) => {
      if(barras.includes(ch)) {
        return ch === "/" ? "\\" : "/"
      }
      return ch
    })
    return array.join('')
  }).reverse()
  
  return [...upperCube,...lowerCube].join('\n')
}
```
##### Second solution
```js
function createCube(size) {
  
  let upperCube = Array.from({ length: size }, (_, i) => {
    return " ".repeat(size - i - 1) + "/\\".repeat(i+1) + "_\\".repeat(size)
  })
  
  let lowerCube = Array.from({ length: size }, (_, i) => {
    return " ".repeat(size - i - 1) + "\\/".repeat(i+1) + "_/".repeat(size)
  }).reverse()
  
  return [...upperCube,...lowerCube].join('\n')
}
```

##### Third solution
```js
function createCube(size) {
  const createSide = ch => (
    Array.from({ length: size }, (_, i) => {
    	return " ".repeat(ch[2] - i) + ch[0].repeat(i+1) + ch[1].repeat(size)
  	})
	)
	const up = createSide(["/\\","_\\", size - 1])
  const down = createSide(["\\/","_/", size - 1]).reverse()
  return [...up,...down].join('\n')
}
```


#### Typescript
```ts
type CubeSideParams = [string, string, number]

function createCube(size: number): string {
  const createSide = (ch: CubeSideParams) => (
    Array.from({ length: size }, (_, i) => {
    	return " ".repeat(ch[2] - i) + ch[0].repeat(i+1) + ch[1].repeat(size)
  	})
	)
	const up = createSide(["/\\","_\\", size - 1])
  const down = createSide(["\\/","_/", size - 1]).reverse()
  return [...up,...down].join('\n')
}

```

- [Go to challenge 6](https://adventjs.dev/challenges/2022/6)
- [Link al siguiente reto](./reto07.md)
