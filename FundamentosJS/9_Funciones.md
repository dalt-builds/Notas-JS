# Funciones

## Parametros de la funcion

Existen dos tipos de sintaxis de paramtros: **default params** y **rest params**

### Default Params:

Valor por defecto si no se pasa el argumento (o es `undefined`).

```js
function saludar(nombre = "Mundo") {
  console.log(`Hola, ${nombre}!`);
}

saludar("Ana"); // Hola, Ana!
saludar();      // Hola, Mundo!
```

> `null` **no** activa el valor por defecto, solo `undefined`.

### Rest Parameters (`...rest`):

Captura múltiples argumentos en un array. Siempre va al final.

```js
function sumar(...nums) {
  return nums.reduce((acc, n) => acc + n, 0);
}

sumar(1, 2, 3); // 6
```

> A diferencia de `arguments`, `...rest` es un array real y funciona en arrow functions.

---

## Arrow Functions

Sintaxis corta. Hereda el `this` del contexto exterior.

```js
const doble = n => n * 2;
const sumar = (a, b) => a + b;

// Varias líneas → llaves + return explícito
const describir = (nombre, edad) => {
  return `${nombre} tiene ${edad} años`;
};

// Retornar objeto → envolver en paréntesis
const crearUser = (nombre) => ({ nombre });
```

| | Función normal | Arrow function |
|---|---|---|
| `this` | Propio | Heredado |
| `arguments` | ✅ | ❌ (usar `...rest`) |
| Constructor | ✅ | ❌ |

---

## Ejemplo combinado

```js
const registrar = (rol = "user", ...personas) => {
  personas.forEach(({ nombre, edad = 18 }) =>
    console.log(`[${rol}] ${nombre}, ${edad} años`)
  );
};

registrar("admin", { nombre: "Ana", edad: 25 }, { nombre: "Luis" });
// [admin] Ana, 25 años
// [admin] Luis, 18 años
```

