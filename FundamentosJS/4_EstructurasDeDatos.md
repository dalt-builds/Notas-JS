## Datos estructurados
Datos organizados siguiendo una estructura definida, lo que permite que los programas los interpreten, almacenen y manipulen fácilmente

```
Usuario
 ├─ nombre
 ├─ edad
 └─ email
```
En JavaScript esto suele representarse con objetos o JSON.

```js
const usuario = {
  nombre: "Daniel", 
  edad: 21,
  email: "daniel@email.com"
}
```
---

## JSON (JavaScript Object Notation)

Un JSON permite enviar y guardar datos entre progrmas o sistemas. Se basa en dos estructuras:
- Coleccion de pares clave/valor(Objeto): Envueltas en llaves `{}`
- Listas ordenadas (Arreglos): Envueltas en corchetes `[]`

**Ejemplo:**
```js
{
    "nombre": "Martin",
    "habilidades": ["programar", "entrenar"]
    "direccion"{
        "ciudad": "Medellin",
        "barrio": "Aranjuez"
    }
}
```

En JS se us mucho para recibir datos de APIs usando funciones como:
- `JSON.parse()` → Convierte JSON a objetos JS
- `JSON:stringify()` → Convierte objeto JS a JSON

---

## Colecciones indexadas
Son colecciones de datos, donde se accede a los elementos por medio de un indice numerico. Mantienen el orden y empiezan en 0

### `Arrays`:
Conjunto el cual permite almacenar datos mediante una lista de manera ordenada, cuenta con un tamaño dinamico, puede contener diferntes tipos de datos y ademas tiene diferenes metodos (`push`, `pop`, `map`)

```js
const nums = [10, 20, 30]

nums[0] // 10
nums[1] // 20

// Agregar elementos
nums.push(40)
```

### `Typed arrays`:
Son arrays especiales para datos binarios, usados cuando se necesita más eficiencia o trabajar cerca del hardware.

Se usan en:
- WebGL
- procesamiento de audio
- manipulación de buffers
- gráficos

**Ejemplo:**
```js
const arr = new Int32Array([1,2,3])

arr[0] // 1
```

Tipos comunes:
- `Int8Array`
- `Uint8Array`
- `Float32Array`
- `Float64Array`

<br>

| Array          | TypedArray    |
| -------------- | ------------- |
| dinámico       | tamaño fijo   |
| cualquier tipo | solo números  |
| más flexible   | más eficiente |

---

## Colecciones con clave
Son colecciones de datos ordenados por una clave, no po indexacion, es decir, son datos con la estructura clave-valor. 
Los objetos `map` y `set`, son colecciones con clave y son iterables en el orden de incersion

<br>

### `Map`:
Es una coleccion de claves y valores, donde las claves puede ser cualquier tipo de dato y mantiene el orden de incersion 

```js
const map = new Map()
map.set("nombre", "Daniel")
map.get("nombre")
```

### `WeakMap`:
Las **claves deben ser objetos**, no es iterable y permite que el objeto sea eliminado por el **garbaje collector**

<br>

### `Set`:
Colecciones de valores unicos (si hay valores repetidos se queda solo con el ultimo), no hay claves solo valores

```js
const set = new Set([1,2,3])
set.add(4)
```

### `WeakSet`:
**Solo puede contener objetos**, no es iterable y permite que el objeto sea eliminado por el **garbaje collector**
