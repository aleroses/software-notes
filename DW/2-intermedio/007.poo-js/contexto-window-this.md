# Context this y window

## Context

En JavaScript, el **contexto** se refiere principalmente al **!/nav>>entorno de ejecución** donde el código se evalúa y se ejecuta, determinando el valor de la palabra clave `this`, el acceso a variables y funciones, y se organiza en el **Contexto Global** y el **Contexto de Función** (o de ejecución), gestionados por la pila de llamadas (call stack) para manejar variables y funciones en un momento dado. 

Contexto de Ejecución (Execution Context)

- Es un concepto abstracto que contiene toda la información necesaria para ejecutar una parte del código, como variables, funciones y el objeto `this`.
- Se crea cuando JS comienza a ejecutar un archivo (Global) o cuando se llama una función (Funcional).
- Tiene dos fases: creación (configuración) y ejecución (ejecución real del código). 

Tipos de Contextos

1. **Contexto Global (Global Execution Context), GEC):**
    - Es el contexto por defecto, para todo el script.
    - Crea un objeto global (`window` en navegadores) y una variable `this` que apunta a ese objeto global.
2. **Contexto de Función (Function Execution Context), FEC):**
    - Se crea cada vez que una función es invocada.
    - Tiene su propio entorno léxico (acceso a variables locales, argumentos, `this`). 

`this` y el Contexto

- La palabra clave `this` es crucial; su valor depende del contexto en el que se llama la función, refiriéndose al objeto al que pertenece la función en ese momento (global, método de objeto, etc.). 

Pila de Llamadas (Call Stack)

- JS usa una pila (LIFO: Last-In, First-Out) para manejar estos contextos de ejecución. El contexto global está abajo, y los contextos de función se apilan encima cuando se llaman, y se desapilan al terminar su ejecución. 

En resumen, el contexto es el "entorno" donde JavaScript sabe qué variables y funciones puede usar y a qué objeto está "anclado" (`this`) en un instante, controlando el flujo y el acceso a la información.

---

## This

El `this` en JavaScript es uno de los conceptos más importantes _y_ más confusos, porque **no funciona como en otros lenguajes**.

### ¿Qué es `this`?

👉 **`this` es una referencia al “contexto” donde se está ejecutando el código**.  
En palabras simples:

> **`this` apunta a “quién está usando la función” en ese momento**

⚠️ **NO apunta a donde la función fue creada**, sino **a cómo y desde dónde se ejecuta**.

### `this` en el contexto global

```js
console.log(this);
```

En navegador:

```js
this === window // true
```

📌 En el navegador, `this` en el contexto global apunta a `window`.

### `this` dentro de funciones normales (function)

Ejemplo básico

```js
function saludar() {
  console.log(this);
}

saludar();
```

Aquí `this` vuelve a ser `window` (en modo no estricto).

⚠️ En modo estricto

```js
"use strict";

function saludar() {
  console.log(this);
}

saludar();
```

`this` es **`undefined`**

📌 **Regla clave**:  
Una función normal **no tiene `this` propio**, depende de **cómo se llame**.

### `this` dentro de un objeto (función normal)

```js
const persona = {
  nombre: 'Ale',
  saludar: function () {
    // This es el objeto persona
    console.log(this.nombre);
  },
};

persona.saludar();
```

✅ Resultado:

```
Ale
```

👉 Aquí:

- `this` apunta al objeto `persona`
    
- porque **persona ejecuta la función**
    

📌 **Regla mental**:

> `this` es el objeto **antes del punto**

### Problema clásico con funciones anidadas

```js
const persona = {
  nombre: 'Henry',
  saludar: function () {
    function interna() {
      console.log(this.nombre);
    }

    interna();
  },
};

persona.saludar();
```

❌ Resultado:

```
undefined
```

👉 Porque `interna()` se ejecuta **como función normal**, no como método del objeto.

### `this` en funciones flecha (=>)

**Las funciones flecha NO tienen su propio `this`**

Heredan el `this` del contexto donde fueron creadas.

Ejemplo correcto

```js
const persona = {
  nombre: "Ale",
  saludar: function () {
    // Aquí this es el objeto persona
    const interna = () => {
      // El objeto persona es heredado de la función saludar
      console.log(this.nombre);
    };
    interna();
  }
};

persona.saludar();
```

✅ Resultado:

```
Ale
```

📌 Aquí:

- `saludar()` tiene `this = persona`
    
- la función flecha **hereda ese `this`**
    

### Error común: usar arrow function como método

```js
const persona = {
  nombre: "Ale",
  saludar: () => {
    console.log(this.nombre);
  }
};

persona.saludar();
```

❌ Resultado:

```
undefined
```

👉 Porque:

- la función flecha **no crea su propio `this`**
    
- `this` viene del contexto global (`window`)
    

📌 **Regla importante**:

> ❌ NO uses funciones flecha como métodos de objetos

### `this` en clases (class)

Las clases usan el mismo comportamiento que los objetos.

```js
class Persona {
  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    console.log(this.nombre);
  }
}

const p1 = new Persona("Ale");
p1.saludar();
```

✅ Resultado:

```
Ale
```

👉 Aquí:

- `this` apunta a la **instancia creada con `new`**

### Problema común en clases (callbacks)

```js
class Persona {
  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    setTimeout(function () {
      console.log(this.nombre);
    }, 1000);
  }
}

new Persona("Ale").saludar();
```

❌ Resultado:

```
undefined
```

#### Solución con arrow function

```js
setTimeout(() => {
  console.log(this.nombre);
}, 1000);
```

✔️ La arrow function hereda el `this` de la clase.

### Resumen mental rápido 🧠

|Contexto           |¿A qué apunta `this`?       |
|-------------------|-----------------------------|
|Global (navegador) |`window`                    |
|Función normal     |Depende de cómo se llame     |
|Método de objeto   |El objeto antes del punto    |
|Función flecha     |Hereda `this` del contexto |
|Clase              |La instancia creada (`new`) |

Frase clave para memorizar

> **En JavaScript, `this` no depende de dónde escribes la función, sino de cómo la ejecutas.**

---

## Controlando `this`: `call`, `apply` y `bind`

Estas tres herramientas sirven para **decidir manualmente qué será `this`** cuando se ejecute una función.

> 📌 Solo funcionan con **funciones normales**, **NO** con funciones flecha.

### `call()`

- **Ejecuta la función inmediatamente**  
- Le pasas el `this` como **primer argumento**  
- Los demás argumentos van **uno por uno**

Sintaxis

```js
funcion.call(thisArg, arg1, arg2, ...)
```

Ejemplo

```js
function saludar(ciudad) {
  console.log(`Hola, soy ${this.nombre} y vivo en ${ciudad}`);
}

const persona = {
  nombre: "Ale"
};

saludar.call(persona, "Lima");
```

✅ Resultado:

```
Hola, soy Ale y vivo en Lima
```

🔑 Aquí **forzamos** que `this === persona`.

### `apply()`

- Es casi igual a `call`  
- La diferencia es que los argumentos se pasan en **un arreglo**

Sintaxis

```js
funcion.apply(thisArg, [arg1, arg2])
```

Ejemplo

```js
saludar.apply(persona, ["Cusco"]);
```

✅ Resultado:

```
Hola, soy Ale y vivo en Cusco
```

📌 **Cuándo usar `apply`**

- Cuando ya tienes los argumentos en un array
    

## `bind()` (MUY importante en React)

- **NO ejecuta la función**  
- Devuelve **una nueva función**  
- `this` queda **fijado permanentemente**

Sintaxis

```js
const nuevaFuncion = funcion.bind(thisArg);
```

Ejemplo

```js
const saludarAle = saludar.bind(persona);

saludarAle("Cuenca");
```

✅ Resultado:

```
Hola, soy Ale y vivo en Cuenca
```

📌 `bind` es ideal para:

- callbacks
- eventos
- React
- setTimeout / setInterval

Problema clásico que `bind` soluciona

```js
const persona = {
  nombre: "Ale",
  saludar() {
    console.log(this.nombre);
  }
};

setTimeout(persona.saludar, 1000);
```

❌ Resultado:

```
undefined
```

Solución

```js
setTimeout(persona.saludar.bind(persona), 1000);
```

✔️ Ahora `this` apunta correctamente a `persona`.

### Comparación rápida 🧠

|Método |Ejecuta inmediatamente|Retorna función|Argumentos|
|-------|----------------------|---------------|----------|
|call   |✅ Sí                 |❌ No          |Separados |
|apply  |✅ Sí                 |❌ No          |Array     |
|bind   |❌ No                 |✅ Sí          |Separados |

### `this` + arrow function vs `bind`

📌 Muchas veces **arrow function reemplaza a `bind`**

```js
setTimeout(() => {
  console.log(this.nombre);
}, 1000);
```

✔️ Más limpio  
✔️ Más moderno  
✔️ Muy usado en clases y React

### Ejercicios rápidos (muy recomendados)

🔹 Ejercicio 1

¿Qué imprime?

```js
const obj = {
  nombre: "Ale",
  saludar() {
    console.log(this.nombre);
  }
};

// Se crea una copia (referencai)
const f = obj.saludar;
// Y la copia pierde el contexto del objeto
f();
```

❌ `undefined`  
Porque se pierde el contexto del objeto.

🔹 Ejercicio 2

Arréglalo usando `bind`

```js
const f = obj.saludar.bind(obj);
f();
```

✅ Resultado:

```
Ale
```

🔹 Ejercicio 3

¿Por qué esto falla?

```js
const obj = {
  nombre: "Ale",
  saludar: () => {
    console.log(this.nombre);
  }
};
```

❌ Porque las arrow functions **no tienen `this` propio**  
Heredan el `this` global.

### Regla de oro final (guárdala)

> 🔑 **`this` depende de cómo se llama una función, no de dónde se define.**  
> 🔑 **Las arrow functions heredan `this`.**  
> 🔑 **`bind` fija `this` para siempre.**
