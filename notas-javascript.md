# 📒 Notas de JavaScript — Desde los Fundamentos hasta Extensiones de Chrome

> **Meta:** Aprender JavaScript de forma progresiva para poder crear extensiones de Chrome bonitas y funcionales.

---

## 🧱 MÓDULO 1 — Fundamentos del Lenguaje

### Variables

Hay tres formas de declarar variables. En la práctica moderna solo usarás dos:

```javascript
let nombre = "Ana";       // puede cambiar de valor
const PI = 3.14159;       // no puede cambiar (constante)
var antiguo = "evitar";   // vieja escuela, tiene comportamientos raros — no la uses
```

**Regla de oro:** usa `const` por defecto. Si sabes que el valor va a cambiar, usa `let`.

---

### Tipos de datos

```javascript
// Primitivos
let texto    = "Hola mundo";       // string
let numero   = 42;                  // number
let decimal  = 3.14;               // también number
let booleano = true;               // boolean (true/false)
let nada     = null;               // null — ausencia intencional de valor
let indefinido = undefined;        // undefined — variable sin valor asignado

// Complejo
let lista    = [1, 2, 3];          // array
let objeto   = { nombre: "Ana" };  // object
```

Puedes ver el tipo de algo con `typeof`:

```javascript
typeof "hola"   // "string"
typeof 42       // "number"
typeof true     // "boolean"
```

---

### Strings (cadenas de texto)

```javascript
let nombre = "Carlos";
let saludo = "Hola " + nombre;            // concatenación clásica
let saludo2 = `Hola ${nombre}!`;          // template literal (más limpio ✅)

// Métodos útiles
"hola".toUpperCase()      // "HOLA"
"  hola  ".trim()         // "hola"
"hola mundo".includes("mundo")  // true
"hola".length             // 4
"javascript".slice(0, 4)  // "java"
"a,b,c".split(",")        // ["a", "b", "c"]
```

---

### Números

```javascript
let suma  = 10 + 5;   // 15
let resta = 10 - 3;   // 7
let multi = 4 * 3;    // 12
let div   = 10 / 4;   // 2.5
let resto = 10 % 3;   // 1 (módulo / residuo)
let pot   = 2 ** 8;   // 256 (potencia)

Math.round(3.7)   // 4
Math.floor(3.9)   // 3
Math.ceil(3.1)    // 4
Math.random()     // número random entre 0 y 1
Math.max(1, 5, 3) // 5
parseInt("42px")  // 42
parseFloat("3.14") // 3.14
```

---

### Booleanos y comparaciones

```javascript
// Comparaciones — siempre usa === (tres iguales)
5 === 5    // true
5 === "5"  // false (distinto tipo)
5 == "5"   // true (con == hace conversión rara — evítalo)

5 !== 3    // true (diferente)
5 > 3      // true
5 >= 5     // true

// Operadores lógicos
true && true    // true  (Y — ambos deben ser true)
true || false   // true  (O — al menos uno debe ser true)
!true           // false (negación)
```

---

### Condicionales

```javascript
let edad = 20;

if (edad >= 18) {
  console.log("Mayor de edad");
} else if (edad >= 13) {
  console.log("Adolescente");
} else {
  console.log("Niño");
}

// Versión corta (ternario) — ideal para asignar valores
let mensaje = edad >= 18 ? "Puedes entrar" : "Eres menor";
```

---

### Bucles (loops)

```javascript
// For clásico
for (let i = 0; i < 5; i++) {
  console.log(i); // 0, 1, 2, 3, 4
}

// While
let n = 0;
while (n < 3) {
  console.log(n);
  n++;
}

// For...of (para recorrer arrays — el más usado en la práctica)
let frutas = ["manzana", "pera", "uva"];
for (let fruta of frutas) {
  console.log(fruta);
}
```

---

## 🔧 MÓDULO 2 — Funciones

### Formas de declarar funciones

```javascript
// 1. Función clásica
function saludar(nombre) {
  return `Hola, ${nombre}!`;
}

// 2. Función flecha (arrow function) — la más moderna y usada
const saludar = (nombre) => `Hola, ${nombre}!`;

// Con varias líneas
const sumar = (a, b) => {
  const resultado = a + b;
  return resultado;
};

// Llamar a una función
saludar("Ana");   // "Hola, Ana!"
sumar(3, 4);      // 7
```

### Parámetros por defecto

```javascript
const saludar = (nombre = "Visitante") => `Hola, ${nombre}!`;
saludar();         // "Hola, Visitante!"
saludar("Luis");   // "Hola, Luis!"
```

---

## 📦 MÓDULO 3 — Arrays y Objetos

### Arrays

```javascript
let colores = ["rojo", "verde", "azul"];

colores[0]              // "rojo"
colores.length          // 3
colores.push("amarillo")   // agrega al final
colores.pop()              // elimina el último
colores.unshift("blanco")  // agrega al inicio
colores.shift()            // elimina el primero

// Los métodos más poderosos (con funciones)
const numeros = [1, 2, 3, 4, 5];

// map — transforma cada elemento y devuelve nuevo array
const dobles = numeros.map(n => n * 2);     // [2, 4, 6, 8, 10]

// filter — filtra según condición
const pares = numeros.filter(n => n % 2 === 0);  // [2, 4]

// find — encuentra el primer elemento que cumple condición
const primerPar = numeros.find(n => n % 2 === 0); // 2

// forEach — recorre sin devolver nada (para efectos secundarios)
numeros.forEach(n => console.log(n));

// includes — verifica si existe
numeros.includes(3);  // true
```

---

### Objetos

```javascript
const persona = {
  nombre: "María",
  edad: 28,
  ciudad: "Medellín",
  saludar() {           // método (función dentro del objeto)
    return `Soy ${this.nombre}`;
  }
};

// Acceder a propiedades
persona.nombre        // "María"
persona["ciudad"]     // "Medellín" (útil cuando el nombre viene de una variable)

// Modificar y agregar propiedades
persona.edad = 29;
persona.profesion = "Diseñadora";

// Desestructuración — extraer propiedades fácilmente
const { nombre, edad } = persona;
console.log(nombre); // "María"

// Spread operator — copiar/combinar objetos
const persona2 = { ...persona, nombre: "Carlos" };
```

---

## ⚡ MÓDULO 4 — JavaScript Asíncrono

Este es quizás el tema más importante para extensiones de Chrome.

### Callbacks (vieja escuela, pero es bueno entenderlos)

```javascript
setTimeout(() => {
  console.log("Esto se ejecuta después de 2 segundos");
}, 2000);
```

### Promesas

```javascript
const fetchData = () => {
  return new Promise((resolve, reject) => {
    // Si todo va bien:
    resolve("Datos obtenidos");
    // Si algo falla:
    // reject("Error al obtener datos");
  });
};

fetchData()
  .then(datos => console.log(datos))
  .catch(error => console.error(error));
```

### Async/Await — la forma moderna y más legible ✅

```javascript
const obtenerUsuario = async (id) => {
  try {
    const respuesta = await fetch(`https://api.ejemplo.com/usuarios/${id}`);
    const datos = await respuesta.json();
    return datos;
  } catch (error) {
    console.error("Error:", error);
  }
};

// Llamarlo
obtenerUsuario(1).then(usuario => console.log(usuario));
```

---

## 🌐 MÓDULO 5 — El DOM (Document Object Model)

El DOM es la interfaz para interactuar con el HTML de una página. Es fundamental para las extensiones de Chrome.

### Seleccionar elementos

```javascript
// Un elemento por selector CSS (el más usado)
const boton = document.querySelector("#mi-boton");
const titulo = document.querySelector(".titulo");
const input = document.querySelector("input[type='text']");

// Múltiples elementos
const items = document.querySelectorAll(".item");
items.forEach(item => console.log(item.textContent));
```

### Modificar elementos

```javascript
const div = document.querySelector("#contenedor");

// Texto e HTML
div.textContent = "Nuevo texto (seguro)";
div.innerHTML = "<strong>Texto en negrita</strong>";

// Estilos
div.style.color = "red";
div.style.backgroundColor = "#f0f0f0";
div.style.display = "none";    // ocultar
div.style.display = "block";   // mostrar

// Clases (la forma más limpia de manejar estilos)
div.classList.add("activo");
div.classList.remove("activo");
div.classList.toggle("activo");    // alterna (agrega si no está, quita si está)
div.classList.contains("activo");  // true/false
```

### Crear y agregar elementos

```javascript
const nuevoParrafo = document.createElement("p");
nuevoParrafo.textContent = "Soy un nuevo párrafo";
nuevoParrafo.classList.add("parrafo-custom");

document.body.appendChild(nuevoParrafo);    // al final del body
div.prepend(nuevoParrafo);                  // al inicio del div
div.insertAdjacentElement("afterend", nuevoParrafo); // después del div
```

### Eventos

```javascript
const boton = document.querySelector("#boton");

// Escuchar eventos
boton.addEventListener("click", (event) => {
  console.log("¡Botón clickeado!", event.target);
});

// Tipos de eventos comunes
// "click"       — clic del mouse
// "input"       — cuando cambia el valor de un input
// "change"      — cuando termina de cambiar
// "keydown"     — tecla presionada
// "mouseover"   — mouse encima del elemento
// "submit"      — formulario enviado
// "DOMContentLoaded" — página cargada

// Ejemplo con input
const campo = document.querySelector("input");
campo.addEventListener("input", (e) => {
  console.log(e.target.value); // valor actual del input
});
```

---

## 🔒 MÓDULO 6 — Storage y Datos Persistentes

### localStorage (para guardar datos en el navegador)

```javascript
// Guardar
localStorage.setItem("usuario", "Carlos");
localStorage.setItem("preferencias", JSON.stringify({ tema: "oscuro" }));

// Leer
const usuario = localStorage.getItem("usuario");
const prefs = JSON.parse(localStorage.getItem("preferencias"));

// Eliminar
localStorage.removeItem("usuario");
localStorage.clear(); // borra todo
```

> **Nota:** En extensiones de Chrome usarás `chrome.storage.sync` en lugar de `localStorage`, pero el concepto es idéntico.

---

## 🔌 MÓDULO 7 — Extensiones de Chrome

Ahora sí, llegamos a la parte interesante. Ya con lo anterior, tienes todo lo necesario.

### Estructura básica de una extensión

```
mi-extension/
│
├── manifest.json        ← El cerebro: configuración de la extensión
├── popup.html           ← La ventanita que aparece al hacer clic en el ícono
├── popup.js             ← Lógica del popup
├── content.js           ← Script que corre dentro de las páginas web
├── background.js        ← Script que corre en el fondo (siempre activo)
└── icons/
    ├── icon16.png
    ├── icon48.png
    └── icon128.png
```

---

### El manifest.json (Manifest V3)

```json
{
  "manifest_version": 3,
  "name": "Mi Extensión",
  "version": "1.0",
  "description": "Una extensión increíble",
  "icons": {
    "16": "icons/icon16.png",
    "48": "icons/icon48.png",
    "128": "icons/icon128.png"
  },
  "action": {
    "default_popup": "popup.html",
    "default_title": "Abrir extensión"
  },
  "permissions": [
    "storage",
    "activeTab",
    "scripting"
  ],
  "background": {
    "service_worker": "background.js"
  },
  "content_scripts": [
    {
      "matches": ["<all_urls>"],
      "js": ["content.js"]
    }
  ]
}
```

---

### popup.html — La interfaz del popup

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <style>
    body {
      width: 300px;
      padding: 16px;
      font-family: 'Segoe UI', sans-serif;
      background: #1a1a2e;
      color: white;
    }
    h1 {
      font-size: 18px;
      margin-bottom: 12px;
      color: #e94560;
    }
    button {
      background: #e94560;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 8px;
      cursor: pointer;
      width: 100%;
      font-size: 14px;
      transition: opacity 0.2s;
    }
    button:hover { opacity: 0.85; }
  </style>
</head>
<body>
  <h1>Mi Extensión</h1>
  <p id="estado">Lista para usar</p>
  <button id="btn-accion">Ejecutar acción</button>

  <script src="popup.js"></script>
</body>
</html>
```

---

### popup.js — Lógica del popup

```javascript
// Cuando el DOM del popup esté listo
document.addEventListener("DOMContentLoaded", () => {
  const boton = document.querySelector("#btn-accion");
  const estado = document.querySelector("#estado");

  // Cargar estado guardado
  chrome.storage.sync.get(["contador"], (result) => {
    estado.textContent = `Veces ejecutado: ${result.contador || 0}`;
  });

  boton.addEventListener("click", async () => {
    // Obtener la pestaña activa
    const [tab] = await chrome.tabs.query({ active: true, currentWindow: true });

    // Ejecutar código en la página
    chrome.scripting.executeScript({
      target: { tabId: tab.id },
      func: () => {
        alert("¡Hola desde la extensión! 👋");
      }
    });

    // Guardar contador
    chrome.storage.sync.get(["contador"], (result) => {
      const nuevo = (result.contador || 0) + 1;
      chrome.storage.sync.set({ contador: nuevo });
      estado.textContent = `Veces ejecutado: ${nuevo}`;
    });
  });
});
```

---

### content.js — Interactúa con la página web

Este script se inyecta en las páginas que visitas. Tiene acceso completo al DOM de la página.

```javascript
// content.js

// Este código corre dentro de cada página web
console.log("Content script cargado en:", window.location.href);

// Escuchar mensajes desde el popup o background
chrome.runtime.onMessage.addListener((mensaje, sender, responder) => {
  if (mensaje.tipo === "obtenerTexto") {
    const textoSeleccionado = window.getSelection().toString();
    responder({ texto: textoSeleccionado });
  }

  if (mensaje.tipo === "resaltarPagina") {
    document.body.style.filter = "hue-rotate(180deg)";
    setTimeout(() => {
      document.body.style.filter = "";
    }, 2000);
  }
});
```

---

### background.js — El service worker

Corre en el fondo, ideal para lógica persistente, alarmas, o interceptar requests.

```javascript
// background.js

// Se ejecuta al instalar la extensión
chrome.runtime.onInstalled.addListener(() => {
  console.log("Extensión instalada correctamente");

  // Establecer valores por defecto
  chrome.storage.sync.set({
    contador: 0,
    tema: "oscuro"
  });
});

// Escuchar mensajes de otros scripts
chrome.runtime.onMessage.addListener((mensaje, sender, responder) => {
  console.log("Mensaje recibido:", mensaje);
  responder({ ok: true });
});
```

---

### Comunicación entre partes

```javascript
// Desde popup.js — enviar mensaje al content script
const [tab] = await chrome.tabs.query({ active: true, currentWindow: true });
chrome.tabs.sendMessage(tab.id, { tipo: "resaltarPagina" });

// Desde popup.js — enviar mensaje al background
chrome.runtime.sendMessage({ tipo: "ping" }, (respuesta) => {
  console.log("Background respondió:", respuesta);
});

// Desde content.js — enviar mensaje al background
chrome.runtime.sendMessage({ tipo: "evento", datos: "algo" });
```

---

## 🎨 MÓDULO 8 — Consejos para Extensiones Bonitas

### Usa variables CSS para un sistema de diseño consistente

```css
:root {
  --color-primario: #6c63ff;
  --color-fondo: #0f0f1a;
  --color-superficie: #1e1e2e;
  --color-texto: #e2e8f0;
  --color-texto-muted: #94a3b8;
  --radio: 10px;
  --sombra: 0 4px 24px rgba(0,0,0,0.3);
}

body {
  background: var(--color-fondo);
  color: var(--color-texto);
  font-family: 'Inter', -apple-system, sans-serif;
}
```

### Animaciones suaves con CSS

```css
.tarjeta {
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.tarjeta:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 30px rgba(108, 99, 255, 0.3);
}
```

### Tamaño del popup recomendado

El popup de Chrome puede tener máximo **800x600px**. Lo ideal es entre **320–400px de ancho**.

---

## 🚀 MÓDULO 9 — Flujo de Trabajo

### Cómo cargar tu extensión en Chrome

1. Abre Chrome y ve a `chrome://extensions`
2. Activa el **Modo desarrollador** (esquina superior derecha)
3. Haz clic en **"Cargar descomprimida"**
4. Selecciona la carpeta de tu extensión
5. ¡Listo! Verás el ícono en la barra de herramientas

### Para actualizar cambios

Cada vez que modifiques archivos, haz clic en el ícono 🔄 de tu extensión en `chrome://extensions`. Para el popup, basta con cerrarlo y abrirlo de nuevo.

### Ver errores

- **Popup/popup.js:** Clic derecho en el popup → "Inspeccionar"
- **content.js:** DevTools de la página normal (F12)
- **background.js:** En `chrome://extensions`, haz clic en "service worker"

---

## 📚 Hoja de Referencia Rápida — APIs de Chrome

```javascript
// Storage
chrome.storage.sync.get(["clave"], result => { /* result.clave */ });
chrome.storage.sync.set({ clave: valor });
chrome.storage.local.get(["clave"], result => { /* sin límite de tamaño */ });

// Pestañas
chrome.tabs.query({ active: true, currentWindow: true }, ([tab]) => { });
chrome.tabs.create({ url: "https://ejemplo.com" });
chrome.tabs.reload();

// Inyectar scripts
chrome.scripting.executeScript({ target: { tabId }, func: () => {} });
chrome.scripting.insertCSS({ target: { tabId }, css: "body { background: red }" });

// Notificaciones
chrome.notifications.create("id", {
  type: "basic",
  iconUrl: "icons/icon48.png",
  title: "Título",
  message: "Mensaje de la notificación"
});

// Alarmas (tareas programadas)
chrome.alarms.create("mi-alarma", { periodInMinutes: 30 });
chrome.alarms.onAlarm.addListener(alarm => {
  if (alarm.name === "mi-alarma") { /* hacer algo */ }
});
```

---

## 🗺️ Ruta de Aprendizaje Sugerida

1. **Semana 1-2:** Módulos 1-3 (variables, funciones, arrays, objetos)
2. **Semana 3:** Módulo 4-5 (asíncrono y DOM) — practica con pequeñas páginas web
3. **Semana 4:** Módulo 7-8 — crea tu primera extensión simple (un contador, un cambiador de fondo)
4. **Semana 5+:** Extensiones más complejas: consumir APIs, guardar preferencias, inyectar UIs

---

*¡Cualquier duda es bienvenida! JavaScript se aprende haciéndolo. Rompe cosas, arréglales, y repite.* 🚀
