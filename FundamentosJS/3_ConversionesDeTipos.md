## Conversion de tipos:
Es el proceso de pasar un valor de un tipo de dato a otro (por ejemplo, de un `String` a un `Number`). 
En Javascript existen dos tipos de conversiones:

### Conversion explicita (Casting)
Es cuando usas funciones nativas para obligar al cambio. Es la forma más segura porque tienes el control.

- **A Number:** Usas `Number()`, `parseInt()` o `parseFloat()`

- **A String:** Usas `String()` o el método `.toString()`

- **A Boolean:** Usas `Boolean()`
  
<br>

```js
let n = 10, num_str = "3";

console.log(Number(num_str)) // "3" → 3
console.log(Boolean(n) // 10 → true
console.log(String(n))) // 10 → "10"
```

<br>

### Conversion implicita (Coercion)
JavaScript cambia el tipo por defecto, sin intervencion del programador 

```js
let x = 3, w = "2";

console.log(x + w) // 3 + "2" → 32

console.log(x- w) // 3 - 2 → 1
console.log(x * w) // 3 * 2 → 6
console.log(x / w) // 3 / 2 → 1.5
```

**Notacion para (`-`,`*`.`/`):**
A diferencia del `+`, estos operadores solo funcionan con números, por lo que **JS convierte todo a Number**

