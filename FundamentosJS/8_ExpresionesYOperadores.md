# Expresiones y operadores
Una expresión es una combinación de variables, constantes, operadores y funciones que el lenguaje interpreta y evalúa para producir un único valor.

<br>

### Asignacion:
Sirven para guardar valores en variables.
```js
let x = 10;   // asignación básica
x += 5;       // x = x + 5
x -= 3;       // x = x - 3
x *= 2;       // x = x * 2
x /= 2;       // x = x / 2
```

<br>

### Comparacion:
Comparan valores y devuelven true o false.

```js
5 == "5"   // true  (solo valor)
5 === "5"  // false (valor y tipo)
5 != 3     // true
5 > 3      // true
5 <= 5     // true
```

<br>

### Operadores aritmeticos:
Operaciones matematicas basicas
```js
+   // suma
-   // resta
*   // multiplicación
/   // división
%   // módulo (residuo)
**  // potencia
```

<br>

### Operador bitwise:
Trabajan con números en binario (nivel bajo)
```js
&  // AND
|  // OR
^  // XOR
~  // NOT
<< // desplazamiento izquierda
>> // desplazamiento derecha
```

<br>

### Operadores logicos:
Se usan con condiciones
```js
&& // AND
|| // OR
!  // NOT
```

<br>

### Operador BigInt:
Para trabajar con numeros muy grandes
```js
let x = 10n;
let y = 20n;

x + y // 30n
```

<br>

### Operador String:
Para concatenar 
```js
"Hola" + " mundo" // "Hola mundo"
```

```js
let nombre = "Danieeeee";
"Hola " + nombre
```

<br>

### Operador condicional (ternary):
Es como un `if...else` pero en una sola linea

```js
condicion ? valor1 : valor2
```

<br>

### Operador Comma
Permite ejecutar varias expresiones en una línea y devuelve la última.

```js
let x = (1, 2, 3);
console.log(x); // 3
```

<br>

### Operador Unary:
Operan sobre un valor

```js
typeof x   // tipo de dato de x
!true      // negación
+x         // convierte a número
-x         // cambia signo
```

<br>

### Operador Relational
Evalua relaciones entre valores

```js
in         // propiedad en objeto
instanceof // tipo de objeto
```
