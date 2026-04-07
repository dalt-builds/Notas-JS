## `for`:
Se usa cuando se sabe cuantas veces se va a iterar

```js
for (inicializacion; condicion; actualizacion){
    codigo
}
```

<br>

## `for...of loop`:
Itera sobre los valores de un iterable (arrays, strings, etc)

```js
for (const elemento of array) {
    // codigo
}
```

<br>

## `for...in loop`:
Itera sobre las claves(keys) de un objeto

```js
for (const key in objeto) {
    // codigo
}
```

<hr>

## `while`:
Se usa cuando no se sabe cuantas veces se va a iterar

```js
while (condicion){
    // codigo
}
```
<br>

## `do...while`:
Variante del while que garantiza ejecutarse al menos una vez

```js
do {
    // codigo
} while (condicion);
```
<hr>

### `break`:
Detiene el loop completamente

```js
for (let i = 0; i < 10; i++) {
    if (i === 5) break;
    console.log(i); // 0, 1, 2, 3, 4
}
```

<br>

### `continue`:
Salta la iteracion actual y sigue

```js
for (let i = 0; i < 5; i++) {
    if (i === 2) continue;
    console.log(i); // 0, 1, 3, 4
}
```