# Datos primitivos

| Tipo de dato | Descripcion |
|--------------|-------------|
| String             | Caracteres encerrados dentro de comillas            |
| Number             | Representa un valor matematico            |
| Bigint            | Representa un valor grande entero            |
| Boolean             | Representa un valor de verdad true o false            |
| Undefinied             | Un valor primitivo sin un valor asignado            |
| Null             | Representa la ausencia de un objeto            |
| Symbol             | Es un identificador unico e imborrable            |


```js
// String
let color = "Yellow";
let lastName = "Johnson";

// Number
let length = 16;
let weight = 7.5;

// BigInt
let x = 1234567890123456789012345n;
let y = BigInt(1234567890123456789012345)

// Boolean
let x = true;
let y = false;

// Object
const person = {firstName:"John", lastName:"Doe"};

// Array object
const cars = ["Saab", "Volvo", "BMW"];

// Date object
const date = new Date("2022-03-25");

// Undefined
let x;
console.log(x) // Output: Undefined

// Null
let x = null;
let y = null;

// Symbol
const x = Symbol("id");
const y = Symbol("id");
console.log(x === y); // Output: false
```

---
### Objeto
objeto es una estructura que puede guardar multiples valores. Son una coleccion de pares de **clave: valor**, estos datos son encerrados en `{}`

```js
const persona = {
  nombre: "Diego",
  edad: 25,
  saludar: function() {
    console.log("Hola!");
  }
};

console.log(persona.nombre)
console.log(persona.edad)
persona.saludar()
```
`Output`:
```
Diego
25
Hola!
```

### Bulit-in Objects (Objetos incorporados):
Javascript trae objetos listos para utilizar  
<br>

| Objeto   | Para qué sirve        |
| -------- | --------------------- |
| `Array`  | listas                |
| `String` | manipular texto       |
| `Number` | operaciones numéricas |
| `Math`   | funciones matemáticas |
| `Date`   | fechas                |


---

### Funcion `typeof`
typeof permite saber que tipo de dato es una variable

```js
let x = 12
let palabra = "Hola"

console.log(typeof x)
console.log(typeof palabra)
```

`Output`:
```
number
string
```
  
<br>

![alt text](image.png)