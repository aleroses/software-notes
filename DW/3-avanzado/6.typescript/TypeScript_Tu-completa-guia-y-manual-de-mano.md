# TypeScript: Tu completa guía y manual de mano

## 1. Introducción a TypeScript

### 1.1 Introducción a TypeScript

### 1.2 ¿Cómo funcionará el curso?

### 1.3 ¿Cómo hacer preguntas?

### 1.4 Instalaciones necesarias

[Instalaciones recomendadas](https://gist.github.com/Klerith/384b707f9b08698655280a3d4cc4da12)

### 1.5 ¡Únete a Nuestra Comunidad de DevTalles en Discord!

Te invitamos a que formes parte de nuestra comunidad de DevTalles en Discord, un espacio donde tendrás la oportunidad de establecer conexiones con otros estudiantes, compartir y colaborar.

**¿Cómo unirse?**

- Haz clic en el siguiente enlace de invitación: [Comunidad DevTalles](https://discord.gg/pBjEVYTC7t)

- Una vez dentro, cuéntanos un poco de ti en el canal de bienvenida(#preséntate).  

Estamos entusiasmados de tener nuevos miembros y crecer juntos como comunidad.

¡Esperamos verte pronto en Discord!

Atentamente,

El equipo de DevTalles

---

## 2. Introducción a TypeScript

### 2.1 Introducción a la sección

En esta sección comenzaremos nuestros primeros pasos para comprender TypeScript y su sintaxis, pero nuevamente es básicamente JavaScript con tipado de variables, funciones, clases y nuevos tipos que no existen en JavaScript.

Antes de comenzar, personalmente me gusta mucho trabajar con TypeScript, ayuda mucho a cometer menos errors de programación por el costo de más código y tiempo de desarrollo, pero lo recuperamos a la hora de refactorizar o encontrar errores en nuestro programa a la hora de escribirlo.

En esta sección vamos a realizar ejercicios iniciales, exposiciones y generalidades que nos permitan seguir trabajando en el curso.

### 2.2 Instalación de TypeScript


[TypeScript](https://www.typescriptlang.org/)

Instalar de manera global:

```bash
npm install -g typescript
tsc --version
```

En Windows abrir la CLI como administrador.

### 2.3 Hola Mundo en TypeScript

Estructura:

```bash
typescript
└── bases
    ├── app.js 👈🏼👀 # Created at the end
    ├── app.ts
    └── index.html
```

`./bases/app.ts`

```ts
const msg: string = 'Hi world';

console.log(msg);
```

`./bases/index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />
    <title>Bases de TypeScript</title>
  </head>
  <body>
    <!-- First, we try with app.ts -->
    <script src="./app.js" 👈🏼👀></script>
  </body>
</html>
```

```bash
# Create the app.js file
cd bases
tsc app
```

`./bases/app.js`

```js
var msg = 'Hi world';

console.log(msg);
```

`Ctrl + Shift + I`

Al inicio referenciamos el archivo `app.ts` dentro de la etiqueta `script` lo que da un error, pero al crearse el archivo `app.js` e invocándolo se soluciona mostrándonos el mensaje en consola.

### 2.4 TSConfig.json

Estructura:

```bash
typescript
└── bases
    ├── app.d.ts
    ├── app.d.ts.map
    ├── app.js
    ├── app.js.map
    ├── app.ts
    ├── index.html
    └── tsconfig.json 👈🏼👀
```

```bash
tsc --init
tsc # Transpile everything
```

Esto crea automáticamente varios archivo `.map` y `.d.ts`, pero esto no afecta en nada.

```json
{
  // Visit https://aka.ms/tsconfig to read more about this file
  "compilerOptions": {
    // File Layout
    // "rootDir": "./src",
    // "outDir": "./dist",

    // Environment Settings
    // See also https://aka.ms/tsconfig/module
    "module": "nodenext",
    "target": "esnext",
    "types": [],
    // For nodejs:
    // "lib": ["esnext"],
    // "types": ["node"],
    // and npm install -D @types/node

    // Other Outputs
    "sourceMap": true,
    "declaration": true,
    "declarationMap": true,

    // Stricter Typechecking Options
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true,

    // Style Options
    // "noImplicitReturns": true,
    // "noImplicitOverride": true,
    // "noUnusedLocals": true,
    // "noUnusedParameters": true,
    // "noFallthroughCasesInSwitch": true,
    // "noPropertyAccessFromIndexSignature": true,

    // Recommended Options
    "strict": true,
    "jsx": "react-jsx",
    "verbatimModuleSyntax": true,
    "isolatedModules": true,
    "noUncheckedSideEffectImports": true,
    "moduleDetection": "force",
    "skipLibCheck": true
  }
}
```

También notamos que se añadieron algunas cosas en `app.js`.

```js
'use strict';
Object.defineProperty(exports, '__esModule', { value: true });
const msg = 'Hi world';
console.log(msg);
//# sourceMappingURL=app.js.map
```

🐞 Si tienes este error:

```bash
Uncaught ReferenceError: exports is not defined
    <anonymous> http://127.0.0.1:5500/bases/app.js:2
```

Lo solucioné de la siguiente manera:

1. Edité el `tsconfig.json` cambiando solo:
	`"module": "nodenext",` por `"module": "esnext",`
	
2. Dentro del `index.html` añadí `type="module"` al `script`.
	`<script src="./app.js" type="module"></script>`

### 2.5 Modo observador - Watch mode

Transpilar automáticamente:

```bash
# Within bases
tsc --watch

# Also
tsc -w
```

`./bases/app.ts`

```ts
const msg: string = 'Hi world';

const hero = {
  name: 'Ironman',
  age: 45,
};

// Detects the change in data type.
// hero.age = '50'; 👈🏼👀

console.log(hero.age);
```

---

## 3. Tipos básicos

### 3.1 ¿Qué veremos en esta sección?

En esta sección aprenderemos:

1. ¿Qué son los tipos de datos?
2. Una introducción a los diferentes tipos de datos que existen en TypeScript.
3. Booleanos.
4. Números.
5. Strings.
6. Tipo Any.
7. Arreglos.
8. Tuplas.
9. Enumeraciones
10. Retorno void
11. Null
12. Undefined

Y al final un exámen práctico y seguidamente un examen teórico.

### 3.2 Introducción a los tipos de datos

Tipos de datos:

Primitivos:

- String
- Number
- Boolean
- Symbol

Compuestos:

- Objetos literales
- Funciones
- Clases
- Arreglos

Permite:

- Crear nuevos tipos
- Interfaces
- Genéricos
- Tuplas

### 3.3 Más información sobre los tipos de datos

A continuación explicaremos todos los tipos de datos que soporta TypeScript uno por uno.

Si desean tener más información, pueden ver la documentación oficial de TypeScript sobre los tipos de datos aquí:

[Documentación Oficial](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html)

### 3.4 Inferir tipos y modo estricto

`tsconfig.json`

```json
{
  // Visit https://aka.ms/tsconfig to read more about this file
  "compilerOptions": {
    // File Layout
    // "rootDir": "./src",
    // "outDir": "./dist",

    // Environment Settings
    // See also https://aka.ms/tsconfig/module
    // "module": "nodenext",
    "module": "esnext",
    "target": "esnext",
    "types": [],
    // For nodejs:
    // "lib": ["esnext"],
    // "types": ["node"],
    // and npm install -D @types/node

    // Other Outputs
    "sourceMap": true,
    "declaration": true,
    "declarationMap": true,

    // Stricter Typechecking Options
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true,

    // Style Options
    // "noImplicitReturns": true,
    // "noImplicitOverride": true,
    // "noUnusedLocals": true,
    // "noUnusedParameters": true,
    // "noFallthroughCasesInSwitch": true,
    // "noPropertyAccessFromIndexSignature": true,

    // Recommended Options
    "strict": true,
    "noImplicitAny": true, 👈🏼👀
    "jsx": "react-jsx",
    "verbatimModuleSyntax": true,
    "isolatedModules": true,
    "noUncheckedSideEffectImports": true,
    "moduleDetection": "force",
    "skipLibCheck": true
  }
}
```

`./bases/app.ts`

```ts
(() => {
  const a: number = 10;
  let b: string;

  console.log(a);
})();
```

📌 Nota: Para evitar que se creen archivos como `.d.ts`, `.d.ts.map` o similares, cambia esto en el archivo `tsconfig.json`.

```json
{
  // Visit https://aka.ms/tsconfig to read more about this file
  "compilerOptions": {
    // File Layout
    // "rootDir": "./src",
    // "outDir": "./dist",

    // Environment Settings
    // See also https://aka.ms/tsconfig/module
    // "module": "nodenext",
    "module": "esnext",
    "target": "esnext",
    "types": [],
    // For nodejs:
    // "lib": ["esnext"],
    // "types": ["node"],
    // and npm install -D @types/node

    // Other Outputs
    "sourceMap": false, 👈🏼👀
    "declaration": false, 👈🏼👀
    "declarationMap": false, 👈🏼👀

    // Stricter Typechecking Options
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true,

    // Style Options
    // "noImplicitReturns": true,
    // "noImplicitOverride": true,
    // "noUnusedLocals": true,
    // "noUnusedParameters": true,
    // "noFallthroughCasesInSwitch": true,
    // "noPropertyAccessFromIndexSignature": true,

    // Recommended Options
    "strict": true,
    // "noImplicitAny": true,
    "jsx": "react-jsx",
    "verbatimModuleSyntax": true,
    "isolatedModules": true,
    "noUncheckedSideEffectImports": true,
    "moduleDetection": "force",
    "skipLibCheck": true
  }
}
```

### 3.5 Booleans - Booleanos

Estructura:

```bash
.
└── bases
    ├── app.d.ts
    ├── app.d.ts.map
    ├── app.js
    ├── app.js.map
    ├── app.ts
    ├── index.html
    ├── tipos
    │   ├── booleans.d.ts
    │   ├── booleans.d.ts.map
    │   ├── booleans.js 🔥
    │   ├── booleans.js.map
    │   └── booleans.ts 👈🏼👀 # We create
    └── tsconfig.json
```

`./bases/tipos/booleans.ts`

```ts
(() => {
  let isSuperman: boolean = true;
  isSuperman = true && false;

  console.log({ isSuperman });
})();
```

`./bases/index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />
    <title>Bases de TypeScript</title>
  </head>
  <body>
    <script src="./tipos/booleans.js" type="module"></script>
  </body>
</html>
```

📌 Nota: Es importante que dentro del `src` llamemos al archivo `.js` de lo contrario no funcionará.

### 3.6 Numbers - Números

`./bases/tipos/numbers.ts`

```ts
(() => {
  let avengers: number = 10;

  console.log(avengers);

  const villians: number = 20;

  avengers < villians
    ? console.log("We're in trouble")
    : console.log("We're salved");

  avengers = Number('123A'); // NaN
  console.log({ avengers });

  // NaN is considered a number.
})();
```

`./bases/index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />
    <title>Bases de TypeScript</title>
  </head>
  <body>
    <script src="./tipos/numbers.js" type="module"></script>
  </body>
</html>
```

####  ☢️ Cuidado con `Number()` en JavaScript ☣️

`Number()` es una **función global** que **convierte cualquier valor** a un **número**.

👉 Se usa para transformar cadenas, booleanos, o incluso `null` y `undefined` en un valor numérico.

Cuando llamas a `Number(valor)`, JavaScript intenta convertir ese valor siguiendo reglas específicas.

##### Conversión de valores comunes

1. **Strings → Número**

Si la cadena representa un número válido:

```js
Number("123")   // 123
Number("3.14")  // 3.14
```

Si la cadena NO representa un número válido:

```js
Number("hola")  // NaN
Number("123abc") // NaN
```

2. **Booleanos**

```js
Number(true)  // 1
Number(false) // 0
```

3. **null**

```js
Number(null) // 0
```

4. **undefined**

```js
Number(undefined) // NaN
```

5. **Arreglos**

Reglas especiales:

- Un array vacío → **0**
- Un array con 1 elemento numérico → ese número
- Otros casos → **NaN**

```js
Number([])        // 0
Number([5])       // 5
Number([1,2,3])   // NaN
Number(["10"])    // 10
```

6. **Objetos**

Casi siempre devuelven `NaN`:

```js
Number({})        // NaN
Number({ a: 1 })  // NaN
```

📌 ¿Qué pasa si ya es un número?

No lo cambia:

```js
Number(10)   // 10
Number(3.5)  // 3.5
```

📌 ¿Qué pasa si lo usas sin argumentos?

```js
Number() // 0
```

##### ¿Para qué se usa normalmente?

✔ Convertir valores del input (que vienen como string)

```js
const edad = Number("25");  // 25
```

✔ Evitar concatenación de strings

```js
"2" + 2      // "22"
Number("2") + 2 // 4
```

✔ Validar datos

```js
if (Number(valor) === NaN) { ... }  // (aunque NaN se compara diferente)
```

⚠ IMPORTANTE: `NaN` es “Not-a-Number”

Si la conversión falla:

```js
Number("x") // NaN
```

Para comprobarlo:

```js
Number.isNaN(Number("x")) // true
```

##### 🎯 Resumen corto

|Valor        |Resultado de Number() |
|-------------|----------------------|
|`"10"`      |10                   |
|`"10a"`     |NaN                  |
|`true`      |1                    |
|`false`     |0                    |
|`null`      |0                    |
|`undefined` |NaN                  |
|`[]`        |0                    |
|`[5]`       |5                    |
|`{}`        |NaN                  |

### 3.7 Strings - Cadenas de caracteres

`./bases/tipos/strings.ts`

```ts
(() => {
  const batman: string = 'Batman';
  const linternaVerde: string = 'Linterna Verde';
  const volcanNegro: string = `Héroe: Volcan Negro`;
  const abc = 123;

  console.log(`I'm ${batman}, ${abc}`);

  console.log(batman.toUpperCase().length);
  console.log(batman[10]?.toUpperCase() || 'Not present!');
})();
```

`./bases/index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />
    <title>Bases de TypeScript</title>
  </head>
  <body>
    <script src="./tipos/strings.js" type="module"></script>
  </body>
</html>
```

### 3.8

`./bases/tipos/booleans.ts`

```ts

```
👈🏼👀
🔥
📌
☢️
### 3.9

`./bases/app.ts`

```ts

```

```
```


👈🏼👀
🔥
📌
### 3.10

`./bases/app.ts`

```ts

```
👈🏼👀
🔥
📌
### 3.11

`./bases/app.ts`

```ts

```

### 3.12

`./bases/app.ts`

```ts

```

### 3.13

`./bases/app.ts`

```ts

```

```
```
👈🏼👀
### 3.14

`./bases/app.ts`

```ts

```

```
```

### 3.15

`./bases/app.ts`

```ts

```

### 3.16

`./bases/app.ts`

```ts

```
👈🏼👀
### 3.17

`./bases/app.ts`

```ts

```

```
```

### 3.18

`./bases/app.ts`

```ts

```

```
```

```
```

```
```

```
```

👈🏼👀