# Declaracion y asignacion
Primero declaramos la variable y despues le asignamos un valor. A la hora de declarar en variables en Javascript hay varias maneras de hacerlo, ya que contamos con tres tipos de declaraciones:
- `let`: Permite reasignar el valor de la variable despues de haber sido creada
- `const`: No permite reasignar el valor de la variable, por tanto se usa en caso de que sepamso de antemano que este valor no va a cambiar

```js
const x = 3;
console.log(x)

//-------------------

let val = "Hola mundo";
console.log(val);
```
**Output:**
```terminal
3
"Hola mundo"
```

---

### Alcance de variables (Scope):
El Scope define donde puede usarse una variable. Hay 3 tipos principales:  

**Global Scope:**
Variables accesibles desde todo el programa

```js
let nombre = "Daniel"
function saludar() {
    console.log(nombre)
}
```  

<br>

**Function Scope**:
Las variables declaradas dentro de una función solo existen dentro de esa función
```js
function test() {
    let x = 10
}
console.log(x) // error
```
<br>

**Block Scope:**

Un block es cualquier cosa dentro de {}

Ejemplo: (`if`, `for`, `while`)

```js
if (true) {
    let x = 5
}
console.log(x) // error
```