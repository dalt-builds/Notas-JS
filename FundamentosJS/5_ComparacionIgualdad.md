## Comparaiciones de igualdad
Las comparaciones de igualdad se utilizan en declaraciones logicas, para determinar la igualdad o difencia entre valores o variables

### Operadores de comparacion 

- **`==` (Loosely equality):**
Compara dos valores permitiendo la **conversion de tipos** (type casting)
```js
5 == "5"   // true
true == 1  // true
null == undefined // true
```

- **`===` (Strict equality):**
Compara **valor y tipo**, sin conversion

```js
5 === "5" // false
5 === 5   // true
```

- **`Object.is()`**
Es una comparacion un poco mas precisa que `===` en algunos casos especiales

```js
Object.is(5,5) // true
```
<br>

| Caso           | `===` | `Object.is()` |
| -------------- | ----- | ------------- |
| `NaN` vs `NaN` | false | true          |
| `+0` vs `-0`   | true  | false         |

