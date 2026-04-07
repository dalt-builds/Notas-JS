# Declaracion de condicionales:

## `if...else`:
Se usa para evaluar conidiciones booleanas (verdadero / falso)

```js
if (condicion) {
    // código si es true
} else if (otraCondicion) {
    // código si otraCondicion es true
} else {
    // código si ninguna condición se cumple
}
```

<hr>

## `switch`:

Se usa cuando se tiene muchos casos posibles para un mismo valor.

```js
switch (expresion) {
    case valor1:
        // código
        break;
    case valor2:
        // código
        break;
    default:
        // código si ningún caso coincide
}
```

<hr>

# Manejo de excepciones:
Forma de evitar que el programa se rompa cuando ocurre un error


## `throw`:
Se usa para lanzar errroes manualmmente 

```js
let edad = 15;

if (edad < 18) {
    // Si es menor de edad lanza un error
    throw new Error("Eres menor de edad");
}
```

<br>

## `try / catch / finally`:

```js
try {
    // código que puede fallar
} catch (error) {
    // se ejecuta si hay error
} finally {
    // siempre se ejecuta (opcional)
}
```

<br>

## `Error objects`:
Son objetos que contienen informacion del error

```js
try {
    throw new Error("Algo salió mal");
} catch (error) {
    console.log(error.name);    // Error
    console.log(error.message); // Algo salió mal
}
```
<br>

**Tipos comunes:**
`Error` → general
`TypeError` → tipo incorrecto
`ReferenceError` → variable no definida