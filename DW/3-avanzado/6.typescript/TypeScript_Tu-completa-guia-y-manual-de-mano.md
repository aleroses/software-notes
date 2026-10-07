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

#### ☢️ Advertencia

> 🔥 Como recomendación personal instala y usa TypeSript con los siguiente pasos, ya que a partir de cierto punto la configuración del curso da muchos problemas. En todo caso si continuas con esa configuración e instalación y luego tienes problemas, regresa aquí y sigue los pasos que te muestro.

##### Usando la consola de VSC 

**TypeScript (sin frameworks) + Node + ES Modules + Hot Reload**

⭐ PASO 1 — Crear el proyecto

```bash
mkdir ts-course
cd ts-course
npm init -y
```

⭐ PASO 2 — Instalar dependencias

```bash
npm install --save-dev typescript ts-node @types/node nodemon
```

⭐ PASO 3 — Generar tsconfig.json

```bash
npx tsc --init
```

Ahora cambia esto en el archivo `tsconfig.json`:

```json
{
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist",
    
    "module": "NodeNext",
    "target": "ES2022",
    "moduleResolution": "NodeNext",

    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,

    "sourceMap": true
  },
  "include": ["src"]
}
```

Lo demás dejalo por defecto.

📌 **Tip:** No uses `"outFile"` salvo casos MUY específicos.  
Provoca problemas y genera muchos archivos innecesarios.

Si lo siguiente no te da problemas, déjalo:

> 🔥 _No usamos_ `"exactOptionalPropertyTypes": true`  
> Evita los errores innecesarios de optional chaining.

⭐ PASO 4 — Configurar nodemon (hot reload)

Crea un archivo `nodemon.json`:

```json
{
  "watch": ["src"],
  "ext": "ts",
  "exec": "node --loader ts-node/esm ./src/index.ts"
}
```

Esto hace:

✔ Recarga automática al guardar  
✔ Compatible con ES Modules  
✔ Sin errores de ts-node-dev

⭐ PASO 5 — Script en package.json

Edita tu `package.json`:

```json
{
  "type": "module",
  "scripts": {
    "dev": "nodemon",
    "build": "tsc", // generates the dist folder
    "start": "node dist/index.js"
  }
}
```

Ahora puedes usar:

```shell
npm run dev
npm run build
npm start
```

⭐ PASO 6 — Estructura del proyecto

```bash
my-ts-project
├── src
│   └── index.ts
├── nodemon.json
├── package.json
└── tsconfig.json
```

⭐ PASO 7 — Probar

Crea un archivo `src/index.ts`:

```ts
console.log("Hola TypeScript + Node + ESM 😎");
```

Ejecuta:

```bash
npm run dev
```

Resultado esperado (consola de VSC):

```bash
[nodemon] starting `node --loader ts-node/esm ./src/index.ts`
Hola TypeScript + Node + ESM 😎
```

Y si modificas el archivo…

✔ Se recarga solo  
✔ No tira errores  
✔ Funciona con imports modernos  
✔ No rompe con ESM

##### Usando un Navegador (sin frameworks)

Ahora, **si quieres que TypeScript produzca código que se muestre en un navegador**, debes:

1. Escribir TypeScript
2. Compilarlo a JavaScript
3. Cargar ese JavaScript en un archivo HTML
4. Abrir ese HTML en un servidor (live server o similar)

🔹 1. Estructura correcta

Reorganiza tu proyecto así:

```bash
project/
├── src/
│   └── index.ts
├── dist/
│   └── index.js
├── public/
│   └── index.html
└── tsconfig.json
```

🔹 2. Código TypeScript para el navegador

`src/index.ts`:

```ts
const title = document.createElement("h1");

title.textContent = "Hi Ale from TypeScript on the web";
document.body.appendChild(title);
```

🔹 3. Compilar TypeScript

```bash
npx tsc
```

Esto genera tu carpeta:

```bash
dist/
  index.js
```

🔹 4. HTML que carga tu JS

`public/index.html`:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Proyecto TS para Web</title>
</head>
<body>
  <script src="../dist/index.js"></script>
</body>
</html>
```

🔹 5. Abrir el HTML en un navegador

El navegador mostrará:

```
Hola Ale desde TypeScript en la web
```

🔹 6. Usar Live Server para auto recarga

En VSCode:

✔ Instala la extensión: **Live Server**  
✔ Clic derecho en `public/index.html` → **Open with Live Server**

Ahora cada cambio se refleja automáticamente.

##### Iniciar un proyecto TypeScript CON frameworks

React + TypeScript + Vite:

```bash
npm create vite@latest
# elige React + TypeScript
```

Node.js + Express + TS

```bash
npm init -y
npm i express
npm i -D typescript ts-node @types/node @types/express
npx tsc --init
```

Svelte + TS

```bash
npm create vite@latest
# elige Svelte + TypeScript
```

Next.js + TS

```bash
npx create-next-app@latest --ts
```

#### Module y Targets en tsconfig.json

1️⃣ **module: "nodenext"**

Este modo hace que TypeScript copie **exactamente** el comportamiento de Node respecto a módulos:

- Requiere extensiones `.js` al importar
- Interpreta `.ts` como si fueran `.js` o `.mts` dependiendo
- Puede usar CJS y ESM al mismo tiempo
- Respeta `"type": "module"` del package.json
- Puede producir errores como:  
    ❌ _Must use import to load ES Module_  
    ❌ _Cannot use ECMAScript imports in a CommonJS file_
    

👉 **Este modo tiene reglas muy estrictas**  
Es útil para proyectos grandes o bibliotecas NPM, pero **demasiado complejo si solo quieres aprender TS o hacer apps básicas**.

2️⃣ **module: "ESNext"**

Esto genera **módulos ESM modernos y sencillos**.

Uso:

```ts
import express from "express";
export class Foo {}
```

- No mezcla CommonJS
- No depende de reglas internas de Node
- TypeScript simplemente produce ESM puro
- Compatible con browsers, Bun, Deno y Node

👉 **Es lo más simple para 2024–2025**  
Recomendado para este curso, solo quita `"moduleResolution": "NodeNext",` o usa NodeNext, por el momento no he notado problemas.

3️⃣ target: "esnext"

Significa:

> “Compila Output usando las características más nuevas del lenguaje”.  
> Incluso si no están soportadas por todos los runtimes.

Puede generar cosas que **tu versión de Node no soporte aún**.

Ejemplo:  
Nueva sintaxis, decorators experimentales, nuevas colecciones, etc.

👉 Es moderno, pero **no siempre estable**.

4️⃣ target: "ES2022"

Node 18, 20 y 22 soportan completamente ES2022.

Incluye:

- Top-level await
    
- `class fields`
- `Object.hasOwn()`
- `RegExp match indices`
- `Error.cause`
- Otras características modernas **ya completamente estandarizadas**

No incluye sintaxis experimental.

👉 Es moderno, estable y compatible.

Resumen:

|Configuración|Moderno|Estable|Recomendada|
|---|---|---|---|
|**module: "nodenext"**|Sí|Sí|Solo para proyectos complejos|
|**module: "ESNext"**|⭐ Más moderno|⭐ Simple|⭐ Recomendada|
|**target: "esnext"**|⭐ Ultra moderno|❌ No estable|Solo si sabes lo que haces|
|**target: "ES2022"**|Muy moderno|⭐ Estable|⭐ Recomendada|

⭐ CONCLUSIÓN FINAL

✔ Para aprender TS, crear proyectos simples, usar ESM:

Usa esto:  Para evitar errores comenta `"moduleResolution": "NodeNext",`

```json
"module": "ESNext",
"target": "ES2022",
```

✔ Para bibliotecas o compatibilidad estricta con Node:

Usa esto:

```json
"module": "NodeNext",
"target": "esnext",
```

### 2.4 TSConfig.json

> 🔥 En este punto hasta antes de la sección 7 usé la configuración del curso, luego cambié a la mostrada anteriormente.

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

1. Edité el `tsconfig.json` cambiando:
	`"module": "nodenext",` por `"module": "esnext",`
	
2. Quita o comenta `"moduleResolution": "NodeNext",`
	
3. Dentro del `index.html` añadí `type="module"` al `script`.
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

### 3.8 Tipo Any

`./bases/tipos/any.ts`

```ts
(() => {
  let avenger: any;
  const exists: boolean = false;
  let power;

  avenger = 'Dr. Strange';
  console.log(avenger[0]);
  console.log(avenger.charAt(0));
  console.log((avenger as string).charAt(0));

  avenger = 150.2344;
  console.log((<number>avenger).toFixed(2));
  console.log(<number>avenger.toFixed(2));
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
    <script src="./tipos/any.js" type="module"></script>
  </body>
</html>
```

El casteo en TypeScript

Es la práctica de decirle al compilador que trate una variable como un tipo diferente, aunque el valor subyacente no cambia en tiempo de ejecución. Se usa principalmente con tipos `any` o `unknown`, o cuando TypeScript no puede inferir el tipo automáticamente. La forma recomendada es usar la palabra clave `as` (`let variable as Tipo`), aunque también se puede usar la sintaxis `<Tipo>variable`, que no funciona en archivos JSX. 

Métodos de casteo

```ts
let value: any = "esto es una cadena";

// Usando la palabra clave 'as' (recomendado)
let strLength: number = (value as string).length;

// Usando la sintaxis de corchetes angulares
// let strLength: number = <string>value.length;
```

Cuándo usar casteo

- **Tipos `any` o `unknown`**: Cuando necesitas trabajar con una variable de tipo `any` o `unknown` y estás seguro de su tipo.
- **Librerías externas**: Para trabajar con API externas o bibliotecas cuyos valores no están bien tipados.
- **Anulación de tipos**: Cuando necesitas decirle al compilador que ignore un tipo y lo trate como otro, por ejemplo, al trabajar con elementos del DOM

### 3.9 Arrays - Arreglos

`./bases/tipos/arrays.ts`

```ts
(() => {
  // const numbers:(number| string | boolean)[] = [1, 2, '3', 4, 5];
  const numbers: number[] = [1, 2, 3, 4, 5];
  const villians = ['Omega Rojo', 'Dormammu', 'Duende Verde'];

  numbers.push(6, 7);

  console.log(numbers);

  villians.forEach((villian) =>
    console.log(villian.toUpperCase())
  );
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
    <script src="./tipos/arrays.js" type="module"></script>
  </body>
</html>
```

### 3.10 Tuples - Tuplas

`./bases/tipos/tuples.ts`

```ts
(() => {
  const hero: [string, number] = ['Dr. Strange', 100];
  const villain: [string, number, boolean] = [
    'Dr. Strange',
    100,
    true,
  ];

  villain[0] = 'IronMan';
  villain[1] = 50;
  villain[2] = true;

  console.log({ hero, villain });
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
    <script src="./tipos/tuples.js" type="module"></script>
  </body>
</html>
```

Una tupla en TypeScript es una colección ordenada de elementos que puede almacenar diferentes tipos de datos, y donde tanto el tamaño como el tipo de cada elemento son conocidos de antemano. A diferencia de los arrays convencionales, que típicamente contienen elementos del mismo tipo, las tuplas permiten mezclar tipos y garantizan el orden en que se deben encontrar. 

### 3.11 Enum - Enumeraciones

`./bases/tipos/enums.ts`

```ts
(() => {
  enum AudioLevel {
    min,
    medium,
    max,
  }

  const currentAudio = AudioLevel.medium;
  // const currentAudio = AudioLevel[0]; // min


  console.log(currentAudio);
  console.log(AudioLevel);
})();

// We obtain
1
Object { 
  0: "min",
  1: "medium",
  2: "max",
  min: 0,
  medium: 1,
  max: 2
}
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
    <script src="./tipos/enums.js" type="module"></script>
  </body>
</html>
```

```ts
(() => {
  enum AudioLevel {
    min = 1,
    medium,
    max = 10,
  }

  // const currentAudio = AudioLevel.min; // 1
  // const currentAudio = AudioLevel.medium; // 2
  // const currentAudio = AudioLevel[1]; // 1
  // let currentAudio: AudioLevel = 10;
  let currentAudio: AudioLevel = AudioLevel.medium;

  console.log(currentAudio);
  console.log(AudioLevel);
})();
```

Un enum en TypeScript es una característica que permite crear un tipo de dato para un conjunto de constantes con nombre. Esto hace el código más legible, fácil de mantener y ayuda a evitar errores al usar valores predefinidos como, por ejemplo, los estados de un sistema o los tipos de una variable. Las enumeraciones pueden basarse en números, en cadenas de texto o incluso una combinación de ambos.

### 3.12 Void - Vacío

`./bases/tipos/void.ts`

```ts
(() => {
  const callBatman = (): void => {
    return; // undefined
  };

  const callSuperman = (): void => {
    return undefined;
  };

  const a = callBatman();

  console.log(a);
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
    <script src="./tipos/void.js" type="module"></script>
  </body>
</html>
```

En TypeScript, `void` se usa para indicar que una función no devuelve ningún valor. Se utiliza para funciones que realizan una acción, como imprimir en la consola, en lugar de calcular y devolver un resultado. Es un tipo de retorno que declara explícitamente que no se debe devolver ningún valor.

### 3.13 Never - Nunca

`./bases/tipos/never.ts`

```ts
(() => {
  const error = (message: string): never => {
    throw new Error(message);
  };

  error('Auxilio');

  // It doesn't get to that point.
  const help = (message: string): never | number => {
    if (false) {
      throw new Error(message);
    }

    return 1;
  };

  help('Help me!');

  // It doesn't get to that point.
  console.log('Hi world!');
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
    <script src="./tipos/never.js" type="module"></script>
  </body>
</html>
```

En TypeScript, `never` representa un valor que **nunca ocurre**. Se usa para funciones que nunca terminan normalmente, ya sea porque lanzan un error, tienen un bucle infinito o una sentencia de salida como `process.exit()`. Es un tipo especial que indica que el programa nunca llegará a un estado de retorno en ese punto.

### 3.14 Null y Undefined

`./bases/tipos/null-undefined.ts`

```ts
(() => {
  // strictNullChecks = false
  let nothing: undefined = undefined;

  console.log(nothing);
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
    <script
      src="./tipos/null-undefined.js"
      type="module"
    ></script>
  </body>
</html>
```

En TypeScript, tanto `null` como `undefined` representan la ausencia de un valor, pero se diferencian principalmente en su **intencionalidad** y cómo aparecen en el código. 

- `undefined`: Indica que una variable ha sido **declarada, pero aún no se le ha asignado un valor**. Suele ser el valor predeterminado o automático para parámetros opcionales, propiedades de objetos inexistentes o funciones sin un `return` explícito.
- `null`: Se utiliza para indicar la **ausencia intencional y explícita de un valor**. Es un valor que el programador asigna deliberadamente para declarar que una variable o propiedad está "vacía" o "desconocida" en un momento dado, pero se espera que eventualmente pueda tener un valor válido. 

Diferencias Clave

|Característica      |`undefined`|`null`|
|--------------------|-----------|-------|
|**Significado**     |Valor no asignado/no inicializado.|Ausencia intencional de un valor u objeto.|
|**Asignación**      |Mayormente automática (por el motor de JS/TS).|Asignado explícitamente por el programador.|
|**`typeof`**        |`"undefined"`|`"object"` (un error histórico de JavaScript).|
|**JSON.stringify()**|La propiedad se omite del JSON resultante.|El valor `null` se mantiene en el JSON resultante.|

Uso en TypeScript

La forma en que se manejan `null` y `undefined` en TypeScript depende de la configuración del compilador `strictNullChecks` en el archivo `tsconfig.json`. 

- **Con `strictNullChecks: true` (recomendado):** Los tipos `null` y `undefined` son distintos de otros tipos. Una variable de tipo `string` solo puede ser una cadena. Si también puede ser nula o indefinida, debes indicarlo explícitamente usando una unión de tipos, como `string | null` o `string | undefined`. Esto ayuda a prevenir errores comunes en tiempo de ejecución (`TypeError: Cannot read properties of undefined`).
- **Con `strictNullChecks: false`:** `null` y `undefined` son considerados subtipos de cualquier otro tipo (por ejemplo, puedes asignar `null` a una variable `number` sin error), lo que reduce la seguridad de tipos. 

Para verificaciones en tu código, la comparación con operador de igualdad débil `== null` es una práctica común, ya que comprueba si un valor es `null` o `undefined` simultáneamente. 

```ts
let valor: string | null | undefined;

// Comprueba si es null O undefined
if (valor == null) {
    console.log("No tiene un valor definido ni nulo"); 
}

// Comprueba estrictamente solo para undefined
if (valor === undefined) {
    // ...
}

// Comprueba estrictamente solo para null
if (valor === null) {
    // ...
}

null == undefined // true
null === undefined  // false
```

Para más detalles sobre cómo configurar tu proyecto, puedes consultar la [documentación oficial de TypeScript](https://www.typescriptlang.org/tsconfig/strictNullChecks.html) sobre `strictNullChecks`.

### 3.15 Ejercicio práctico #1.

Descargar el archivo adjunto

La explicación de la tarea se las explico en el siguiente video

Recursos de la lección:

- [app.ts.zip](https://import.cdn.thinkific.com/643563/courses/1870132/appts-220520-123101.zip)

### 3.16 Tarea y Resolución del Ejercicio #1

`./app.ts`

```ts
(() => {
  // Tipos
  const batman: string = 'Bruce';
  const superman: string = 'Clark';

  const existe: boolean = false;

  // Tuplas
  const parejaHeroes: [string, string] = [batman, superman];
  const villano: [string, number, boolean] = [
    'Lex Lutor',
    5,
    true,
  ];

  // Arreglos
  const aliados: string[] = [
    'Mujer Maravilla',
    'Acuaman',
    'San',
    'Flash',
  ];

  //Enumeraciones
  // Si no tienen valor debe ir en orden
  enum Power {
    acuaman = 0,
    batman = 1,
    flash = 5,
    superman = 100,
  }

  const flashPower: Power = Power.flash;
  // const fuerzaFlash = 5;
  // const fuerzaSuperman = 100;
  // const fuerzaBatman = 1;
  // const fuerzaAcuaman = 0;

  // Retorno de funciones
  function activarBatiseñal(): string {
    return 'activada';
  }

  function pedirAyuda(): void {
    console.log('Auxilio!!!');
  }

  // Aserciones de Tipo
  const poder: any = '100';
  const largoDelPoder: number = (poder as string).length;
  console.log(largoDelPoder);
})();
```

### 3.17 Exámen teórico #1

A continuación, vamos a repasar un poco todo lo aprendido hasta el momento...

### 3.18 Quiz 1: Exámen teórico #1

1.  ¿Quién es el fundador de TypeScript?
	- Microsoft
2. ¿Cómo se define un arreglo de Strings en TypeScript?  
	- `var arreglo = ["texto","texto","texto","texto"]`
	- `let arreglo = ["texto","texto","texto","texto"]`
	- `var arreglo:string[ ] = ["texto","texto","texto","texto"]`
	- `let arreglo:string[ ] = ["texto","texto","texto","texto"]`
	- ✅ Todas las anteriores
3. ¿El siguiente código es válido en TypeScript?  
	```ts
	let arr:string[] = ["Text", "Text", "Text"];
	arr.push("10");
	```
	- Verdadero
4. ¿El siguiente código es válido en TypeScript?  
	`let arr:number = [1,2,3,4,5,6,7,8,9,10];`
	- Falso
5. ¿El siguiente código es válido en TypeScript?  
	`let arr:any = [1,2,3,4,5,6,7,8,9,10];`
	- Verdadero
6. ¿Qué es esto?  
	`let variable:[number,string,boolean] = [10,"texto",true];`
	- Tupla
7. ¿El siguiente código es una declaración válida de un string?  
	```ts
	let string = `2.
    3.
    4.
    5.
    6.`;
	```  
	- Verdadero  
8. ¿El siguiente código es válido en TypeScript?  
	`let vacio:null = undefined;`
	- Falso  
9. Dada la siguiente enumeración, que valor tiene "C"  
	```ts
	enum Enumeracion {
	a,
	b,
	c,
	d
	}
	```
	- 2
10. Dada la siguiente enumeración, ¿Qué valor tiene "d"?  
	```ts
	enum Enumeracion {
	  a = 10,
	  b,
	  c = 9,
	  d
	}
	```
	- 10: Como "c" es igual a 9, el siguiente valor es 10, no importa que se repita el valor de la enumeración.

---

## 4. Funciones y objetos

### 4.1. ¿Qué veremos en esta sección?

Esta sección está enfocada en aprender como trabajan las funciones en TypeScript y también nos enfocaremos en aplicar buenas prácticas a la hora de crearlas.

Puntualmente tenemos:

1. Declaraciones básicas de funciones
2. Parámetros obligatorios
3. Parámetros opcionales
4. Parámetros por defecto
5. Parámetros REST
6. Tipo de datos "Function"

Al final de la sección, tendremos el examen práctico y el examen teórico.

### 4.2. Funciones básicas

`./bases/funciones/functions.ts`

```ts
(() => {
  const hero: string = 'Flash';

  function returnName(): string {
    return hero;
  }

  const activeBatiSignal = (): string => {
    return 'Bat-signal Activated!';
  };

  console.log(typeof activeBatiSignal);

  const heroName = returnName();
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
    <script
      src="./funciones/functions.js"
      type="module"
    ></script>
  </body>
</html>
```

### 4.3 Parámetros obligatorios de las funciones

`./bases/funciones/args-required.ts`

```ts
(() => {
  const fullName = (
    firstName: string,
    lastName: string | boolean
  ): string => {
    return `${firstName} ${lastName}`;
  };

  // Variable "noName" is used before being assigned
  let noName: string;
  // const name = fullName('Tony', 'Stark');
  const name = fullName(noName, 'Stark');

  console.log({ name });
  // undefined, Stark
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
    <script
      src="./funciones/args-required.js"
      type="module"
    ></script>
  </body>
</html>
```

Parámetros obligatorios

- Son los que **siempre** se deben proporcionar al llamar a la función.
- Se declaran de forma estándar, sin ningún modificador especial. 

```js
// 'nombre' es obligatorio
function obtenerNombreCompleto(nombre: string, apellido: string): string {
  return `${nombre} ${apellido}`;
}
```

### 4.4 Parámetros opcionales de las funciones

`./bases/funciones/args-optional.ts`

```ts
(() => {
  const fullName = (
    firstName: string,
    lastName?: string | boolean
  ): string => {
    return `${firstName} ${lastName || 'no lastname'}`;
  };

  const name = fullName('Tony');

  console.log({ name });
  // Tony undefined
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
    <script
      src="./funciones/args-optional.js"
      type="module"
    ></script>
  </body>
</html>
```

Los parámetros **obligatorios** son los que siempre deben pasarse al llamar a una función, mientras que los **opcionales** pueden omitirse. Para declarar un parámetro opcional en TypeScript, se añade un signo de interrogación (`?`) después de su nombre en la firma de la función. 

> Es importante que los parámetros opcionales se listen después de los obligatorios. 

```ts
// Ejemplo con parámetros obligatorios y opcionales
function saludar(nombre: string, saludo?: string): void {
  if (saludo) {
    console.log(`${saludo}, ${nombre}`);
  } else {
    console.log(`Hola, ${nombre}`);
  }
}

saludar("Mundo"); // Salida: Hola, Mundo
saludar("Universo", "Buenos días"); // Salida: Buenos días, Universo
```

Parámetros opcionales

- Pueden **omitirse** al llamar a la función.
- Se marcan con un signo de interrogación (`?`) después de su nombre en la definición de la función.
- Deben declararse **después** de los parámetros obligatorios en la firma de la función.
- Si se omite un parámetro opcional, su valor dentro de la función será `undefined`. 

```ts
// 'edad' es opcional
function saludarConEdad(nombre: string, edad?: number): void {
  if (edad === undefined) {
    console.log(`Hola, ${nombre}`);
  } else {
    console.log(`Hola, ${nombre}. Tienes ${edad} años.`);
  }
}

saludarConEdad("Ana"); // Salida: Hola, Ana
saludarConEdad("Carlos", 30); // Salida: Hola, Carlos. Tienes 30 años.
```

### 4.5 Parámetros por defecto

`./bases/funciones/args-default.ts`

```ts
(() => {
  const fullName = (
    firstName: string,
    lastName?: string | boolean,
    upper: boolean = false
  ): string => {
    if (upper) {
      return `${firstName} ${
        lastName || '-----'
      }`.toUpperCase();
    }

    return `${firstName} ${lastName || 'no lastname'}`;
  };

  const name = fullName('Tony', 'Stark', true);

  console.log({ name });
  // Tony undefined
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
    <script
      src="./funciones/args-default.js"
      type="module"
    ></script>
  </body>
</html>
```

### 4.6 Parametros REST

`./bases/funciones/args-rests.ts`

```ts
(() => {
  const fullName = (
    firstname: string,
    ...restArgs: string[]
  ): string => {
    console.log(restArgs);
    return `${firstname} ${restArgs.join(' ')}`;
  };

  const superman = fullName('Clark', 'Joseph', 'Kent');

  console.log({ superman });
})();

// En consola
[ 'Joseph', 'Kent' ] // restArgs
{ superman: 'Clark Joseph Kent' }
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
    <script
      src="./funciones/args-rests.js"
      type="module"
    ></script>
  </body>
</html>
```

Los parámetros `rest` en TypeScript permiten que una función acepte un número indefinido de argumentos, agrupándolos automáticamente en un array con el tipo especificado (ej. `...nombres: string[]`), lo cual es útil para manejar entradas variables, deben ser el último parámetro en la lista, y mejoran la flexibilidad y tipado de funciones.

### 4.7 Tipo Función

`./bases/funciones/functions-type.ts`

```ts
(() => {
  const addNumber = (a: number, b: number) => {
    return a + b;
  };
  const greet = (name: string) => {
    return `Hi ${name}`;
  };
  const saveTheWorld = () => {
    return `The world is saved!`;
  };

  // let myFunction: (y: number, z: number) => number;
  // let myFunction: (y: string) => string;
  let myFunction: () => string;

  // myFunction = addNumber;
  // console.log(myFunction(1, 2));

  // myFunction = greet;
  // console.log(myFunction('Ale'));

  myFunction = saveTheWorld;
  console.log(myFunction());
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
    <script
      src="./funciones/functions-type.js"
      type="module"
    ></script>
  </body>
</html>
```

### 4.8 Tarea y Resolución del ejercicio práctico #2

`./app.ts`

```ts
// Funciones Básicas
const sumar = (a: number, b: number): number => {
  return a + b;
};

const contar = (heroes: string[]): number => {
  return heroes.length;
};

const superHeroes: string[] = [
  'Flash',
  'Arrow',
  'Superman',
  'Linterna Verde',
];

contar(superHeroes);

//Parametros por defecto
const llamarBatman = (llamar: boolean = true): void => {
  if (llamar) {
    console.log('Batiseñal activada');
  }
};

llamarBatman();

// Rest?
const unirheroes = (...personas: string[]): string => {
  return personas.join(', ');
};

// Tipo funcion
const noHaceNada = (
  numero: number,
  texto: string,
  booleano: boolean,
  arreglo: string[]
) => {};

// Crear el tipo de funcion que acepte la funcion "noHaceNada"
let noHaceNadaTampoco: (
  numero: number,
  texto: string,
  booleano: boolean,
  arreglo: string[]
) => void;
noHaceNadaTampoco = noHaceNada;
```

-  [app.ts.zip](https://import.cdn.thinkific.com/643563/courses/1870132/appts-221018-132842.zip)

### 4.9 Quiz 2: Examen teórico #2

Examen teórico #2

Afianzando los conocimientos de la teoría.

### 4.10 Quiz 2: Examen teórico #2

1. ¿Toda función en JavaScript, es código válido de TypeScript?
	- Verdadero
2. ¿La siguiente función es válida en TypeScript?
	```ts
	function saludar(): string {
	  console.log("Hi world!");
	}
	```
	- Falso
3. ¿En TypeScript es posible obligar al desarrollador que debe de cumplir todos los parámetros de una función?
	- Verdadero
4. ¿En JavaScript, todos los parámetros son obligatorios?
	- Falso
5. ¿Con qué caracter especifico un parámetro opcional?
	- ?
6. ¿Qué es un parámetro por defecto?
	- Es un parámetro que es necesario en la función, pero puede ser enviado o no al momento de ser llamada.
7. ¿Los parámetros por defecto sólo pueden ser tipos primitivos?
	- Falso
8. ¿Qué imprime en consola el siguiente código de TypeScript?
	```ts
	function saludar(mensaje: string = "mundo"){
	  console.log("Hola" + mensaje);
	}
	
	saludar("hola");
	```
	- Hola hola
9. ¿Qué es un parámetro REST?
	- Es un arreglo que contiene el resto de parámetros enviados como argumentos a la función.
10. ¿Una función es, a su vez, un tipo en TypeScript?
	- Verdadero

---

## 5. Objetos y tipos personalizados en TypeScript

### 5.1 ¿Qué veremos en esta sección?

Aprenderemos a utilizar los objetos en TypeScript, su uso y mantener nuestro código bien limpio mediante tipos personalizados.

Los temas serán:

1. Objetos básicos
2. Crear objetos con tipos específicos
3. Crear métodos dentro de objetos
4. Tipos personalizados
5. Crear variables que soporten varios tipos a la vez.
6. Comprobar el tipo de un objeto.

Al final, el respectivo examen práctico y teórico.

### 5.2 Objetos básicos

`./bases/objetos/objects.ts`

```ts
(() => {
  let flash = {
    name: 'Barry Allen',
    age: 24,
    powers: ['Súper Velocidad', 'Viajar en el tiempo'],
  };

  flash = {
    name: 'Clark Kent',
    age: 60,
    powers: ['Súper fuerza'],
  };

  console.log(flash);
})();

// Result:
Object { name: "Clark Kent", age: 60, powers: (1) […] }
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
    <script src="./objetos/objects.js" type="module"></script>
  </body>
</html>
```

### 5.3 ¿Cómo crear objetos con tipos específicos?

`./bases/objetos/objects.ts`

```ts
(() => {
  let flash: {
    name: string;
    age?: number; 👈🏼👀
    powers: string[];
  } = {
    name: 'Barry Allen',
    age: 24,
    powers: ['Súper Velocidad', 'Viajar en el tiempo'],
  };

  flash = {
    name: 'Clark Kent',
    // age: 60, 👈🏼👀
    powers: ['Súper fuerza'],
  };

  console.log(flash);
})();
```

### 5.4 Métodos dentro de los objetos

`./bases/objetos/objects.ts`

```ts
(() => {
  let flash: {
    name: string;
    age?: number;
    powers: string[];
    // getName?: Function;
    getName?: () => string;
  } = {
    name: 'Barry Allen',
    age: 24,
    powers: ['Súper Velocidad', 'Viajar en el tiempo'],
  };

  flash = {
    name: 'Clark Kent',
    // age: 60,
    powers: ['Súper fuerza'],
    getName() {
      return 'Hi world!';
    },
  };

  console.log(flash.getName?.());
  // Hi world!
})();
```

### 5.5 Problema con la definición en línea

`./bases/objetos/objects.ts`

```ts
(() => {
  let flash: {
    name: string;
    age?: number;
    powers: string[];
    getName?: () => string;
  } = {
    name: 'Barry Allen',
    age: 24,
    powers: ['Súper Velocidad', 'Viajar en el tiempo'],
  };

  let superman: {
    name: string;
    age?: number;
    powers: string[];
    getName?: () => string;
  } = {
    name: 'Clark Kent',
    age: 34,
    powers: ['Súper Velocidad'],
  };
})();
```

Repetimos mucho código, para evitar eso podemos usar `type`.

### 5.6 Tipos personalizados

`./bases/objetos/type.ts`

```ts
(() => {
  type Hero = {
    name: string;
    age?: number;
    powers: string[];
    getName?: () => string;
  };

  let flash: Hero = {
    name: 'Barry Allen',
    age: 24,
    powers: ['Súper Velocidad', 'Viajar en el tiempo'],
  };

  let superman: Hero = {
    name: 'Clark Kent',
    age: 34,
    powers: ['Súper Velocidad'],
    getName: () => 'Hi Superman!!!',
  };

  console.log(superman.getName?.());
  // Hi Superman!!!
})();
```

### 5.7 Multiples tipos permitidos

`./bases/objetos/union-types.ts`

```ts
(() => {
  type Hero = {
    name: string;
    age?: number;
    powers: string[];
    getName?: () => string;
  };

  let myCustomVariable: string | number | Hero = 'Ale';
  console.log(myCustomVariable);
  // Ale
  console.log(typeof myCustomVariable);
  // string

  myCustomVariable = 20;
  console.log(typeof myCustomVariable);
  // number

  myCustomVariable = {
    name: 'Ale',
    age: 43,
    powers: ['Agua'],
  };
  console.log(typeof myCustomVariable);
  // object
})();
```

### 5.8 Ejercicio práctico #3

Descargue el material adjunto, trabaje con los tipos de datos y la información que aprendió en esta sección.

Sea lo más especifico en los tipos posible y reutilice el primer tipo de dato (el del automóvil)

Recurso de la lección:

- [app.ts.zip](https://import.cdn.thinkific.com/643563/courses/1870132/appts-220520-182525.zip)

### 5.9 Tarea y Resolución del ejercicio práctico #3

`./app.ts`

```ts
// Objetos

type Car = {
  carroceria: string;
  modelo: string;
  antibalas: boolean;
  pasajeros: number;
  disparar?: () => void;
};

const batimovil: Car = {
  carroceria: 'Negra',
  modelo: '6x6',
  antibalas: true,
  pasajeros: 4,
};

const bumblebee: Car = {
  carroceria: 'Amarillo con negro',
  modelo: '4x2',
  antibalas: true,
  pasajeros: 4,
  disparar() {
    // El metodo disparar es opcional
    console.log('Disparando');
  },
};

// Villanos debe de ser un arreglo de objetos personalizados
type Villano = {
  nombre: string;
  edad: number | undefined;
  mutante: boolean;
};

const villanos: Villano[] = [
  {
    nombre: 'Lex Luthor',
    edad: 54,
    mutante: false,
  },
  {
    nombre: 'Erik Magnus Lehnsherr',
    edad: 49,
    mutante: true,
  },
  {
    nombre: 'James Logan',
    edad: undefined,
    mutante: true,
  },
];

// Multiples tipos
// cree dos tipos, uno para charles y otro para apocalipsis

type Charles = {
  poder: string;
  estatura: number;
};

const charles: Charles = {
  poder: 'psiquico',
  estatura: 1.78,
};

type Apocalipsis = {
  lider: boolean;
  miembros: string[];
};

const apocalipsis: Apocalipsis = {
  lider: true,
  miembros: ['Magneto', 'Tormenta', 'Psylocke', 'Angel'],
};

// Mystique, debe poder ser cualquiera de esos dos mutantes (charles o apocalipsis)
let mystique: Charles | Apocalipsis;

mystique = charles;
mystique = apocalipsis;
```

### 5.10 Quiz 3: Examen teórico #3

Examen teórico #3

Vamos a repasar lo aprendido en la sección.

### 5.11 Quiz 3: Examen teórico #3

1. ¿Qué tipo de objeto es el batimovil?
	```ts
	var batimovil = {
	  puertas: 10,
	  marca: "Sedan",
	}
	```
	- `marca: string, puertas: number` El orden no afecta en los objetos.
2. ¿Es posible agregar métodos dentro de los tipos?
	- Verdadero
3. ¿El siguiente código es válido en TypeScript?
	```ts
	let batimovil: { getNombre: () => string } = {
	  getNombre(carro){
		  return carro.toUpperCase();
	  }
	}
	```
	- False: Si se fijan, en la definición del tipo, estamos solicitando que el `getNombre` no reciba parámetros, pero en la implementación de la función, estamos utilizando un parámetro que nos dará problemas en TypeScript.
4. ¿Es posible especificar en TypeScript que una variable puede ser de 4 tipos a la vez?
	- Verdadero
5. ¿El siguiente código de TypeScript es válido?
	```ts
	// Tupla
	let mutable: [string | string[]];
	
	// Estos no soy una tupla
	mutable = ["Hola", "Hola"];
	mutable = "hola";
	```
	- Falso: Si te fijas, en la declaración estamos diciendo que es una "Tupla" y no una unión de tipos, recuerda que la unión de tipos no lleva llaves cuadradas.
6. ¿El siguiente código es válido TypeScript?
	```ts
	// Multiples tipos
	let mutable: number | string[];
	
	mutable = ["Adios", "Hola"];
	mutable = 123;
	```
	- Verdadero.
7. ¿Qué instrucción nos permite saber que tipo de dato contiene una variable?
	- typeof
8. ¿Con qué palabra podemos crear tipos específicos?
	- type
9. ¿Un tipo de dato puede tener métodos obligatorios?
	- Verdadero
10. ¿Los tipos son traducidos a JavaScript?
	- Falso: Los tipos solo existen en TypeScript para brindarnos control sobre los objetos.

### 5.12 Código fuente de la sección

Les dejo mi código fuente por si lo llegan a necesitar o comparar con el mío

[Github - Fin-seccion-5](https://github.com/Klerith/ts-bases/tree/fin-seccion-5)

- [ts-bases-fin-seccion-5.zip](https://import.cdn.thinkific.com/643563/courses/1870132/tsbasesfinseccion5-220520-190151.zip)

---

## 6. Depuración de Errores y el archivo tsconfig.json

### 6.1 ¿Qué veremos en esta sección?

La sección se enfoca en la depuración de errores y comprender el archivo de configuración de TypeScript (el tsconfig.json)

Puntualmente:

1. Aprenderemos el ¿por qué siempre compila a JavaScript?
2. Para que nos puede servir el archivo de configuración de TypeScript
3. Realizaremos depuración de errores directamente a nuestros archivos de TypeScript
4. Removeremos todos los comentarios en nuestro archivo de producción.
5. Restringiremos al compilador que sólo vea ciertos archivos o carpetas
6. Crearemos un archivo final de salida
7. Aprenderemos a cambiar la version de JavaScript de salida

Adicionalmente tendrán el conocimiento necesario para compilar automáticamente cualquier archivo que se vaya creando al momento de ser insertado a nuestro proyecto.

### 6.2 ¿Qué es el archivo tsconfig y para qué nos puede servir?

El archivo `tsconfig.json` es el archivo de configuración central para un proyecto de TypeScript y le dice al compilador TypeScript cómo transformar tu código TS en JavaScript (JS). Sirve para definir rutas de archivos, configurar el rigor de las comprobaciones de tipos modo estricto, elegir la versión de JS de salida target, manejar módulos y ajustar otras opciones que mejoran la calidad, productividad y mantenibilidad del código, permitiendo un control preciso sobre la compilación.

[Enlace oficial de TypeScript](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)

### 6.3 ¿Es posible la depuración del código de TypeScript?

En TypeScript, los archivos `.map` más comunes son los **Source Maps**, que son archivos de texto generados durante la compilación para **mapear el código JavaScript (salida) de vuelta al código TypeScript original (entrada)**, permitiendo una depuración eficiente en navegadores, y también existen los **tipos mapeados**, una característica del lenguaje para crear nuevos tipos basados en otros.

Clases atrás desactivamos la creación de estos, pero puedes volver a crearlos dentro del archivo `tsconfig.json` 

```ts
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
    "sourceMap": true, 👈🏼👀
    "declaration": false,
    "declarationMap": false,

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

Ahora, cada vez que revises la consola verás exactamente, de que archivo `.ts` están viniendo esos datos y podrás debuggear desde ahí mismo.

- Ver en Obsidian: [[debugging-devtools#14. Reproduciendo y reparando un bug]]
- Ver en GitHub: [Reproduciendo y reparando un bug](https://github.com/aleroses/software-notes/blob/master/DW/2-intermedio/025.debugging-devtools/debugging-devtools.md#14-reproduciendo-y-reparando-un-bug)

### 6.4 Remover los comentarios de los archivos de JavaScript

Para remover comentarios en TypeScript, la forma más efectiva es configurar tu archivo `tsconfig.json` con la opción `"removeComments": true`, lo cual elimina todos los comentarios al compilar a JavaScript

### 6.5 Incluir y excluir carpetas y/o archivos

Para incluir y excluir carpetas/archivos en TypeScript, usas las propiedades `include`, `exclude` y `files` dentro de tu archivo `tsconfig.json`, especificando patrones glob para directorios o nombres de archivos que el compilador debe procesar o ignorar, siendo `include` para lo que sí y `exclude` para lo que no, aunque `exclude` solo afecta a lo que `include` ya seleccionó.

```ts
{
  // Visit https://aka.ms/tsconfig to read more about this file
  "compilerOptions": {
    "...",
  },
  "include": [
    "src/**/*.ts", // Incluye todos los archivos .ts dentro de la carpeta 'src' y sus subcarpetas
    "utils/helper.ts" // Incluye un archivo específico
  ],
  "exclude": [
    "node_modules", // Excluye la carpeta node_modules
    "dist", // Excluye la carpeta de salida
    "src/tests/**/*.ts" // Excluye archivos de pruebas
  ],
  "files": [
    "index.ts" // Incluye solo este archivo si no se usan include/exclude
  ]
}
```

Los **Glob Patterns en TypeScript** (y en general en desarrollo) son **cadenas de texto con caracteres comodín** (_wildcards_) como `*`, `?`, `**`, y `[]`, usados para **encontrar y seleccionar grupos de archivos o directorios** de forma flexible y poderosa, especialmente en tareas como compilación, pruebas o empaquetado de código, siendo muy comunes en herramientas como VS Code, Node.js (con `glob` o `globby`), y sistemas de compilación como Gulp para definir qué archivos incluir o excluir. 

¿Cómo funcionan?

- `*`: Coincide con cualquier carácter cero o más veces (excepto separadores de ruta como `/`).
- `?`: Coincide con un solo carácter.
- `**`: Coincide con directorios y subdirectorios (recursivo).
- `{a,b,c}`: Coincide con una de las opciones entre las llaves.
- `[abc]`: Coincide con cualquier carácter dentro de los corchetes (rango).

[A Beginner's Guide: Glob Patterns](https://www.malikbrowne.com/blog/a-beginners-guide-glob-patterns/)

### 6.6 outFile - Archivo de salida

La función de `outFile` en TypeScript es **concatenar múltiples archivos TypeScript (o JavaScript) en un único archivo de salida (.js)** durante la compilación, creando un solo paquete, lo que es útil para simplificar la carga en navegadores (especialmente con módulos como `AMD` o `System`), pero solo funciona con ciertos tipos de módulos y no con CommonJS o ES6 por defecto. 

Características y uso de `--outFile`:

- **Unificación:** Agrupa varios archivos en un solo `.js`, reduciendo la cantidad de solicitudes HTTP.
- **Modo de uso:** Se configura en el `tsconfig.json` o se pasa como flag en la línea de comandos (`tsc --outFile <nombre_salida.js> <archivo1.ts> <archivo2.ts>`).
- **Compatibilidad de módulos:** Solo funciona cuando el `module` se configura como `None`, `AMD`, o `System`. No es compatible con `CommonJS` o `ES6` por defecto para agrupar módulos.
- **Namespace y Módulos:** Se utiliza comúnmente con `namespaces` para generar un único archivo JavaScript que encapsula todo el código, permitiendo que se incluya en una sola etiqueta `<script>` en HTML.

Estructura:

```bash
.
└── bases
    ├── app.ts
    ├── funciones
    │   ├── args-default.ts
    │   ├── args-optional.ts
    │   ├── args-required.ts
    │   ├── args-rests.ts
    │   ├── functions.ts
    │   └── functions-type.ts
    ├── index.html
    ├── main.js 👈🏼👀
    ├── main.js.map
    ├── objetos
    │   ├── objects.ts
    │   ├── type.ts
    │   └── union-types.ts
    ├── tipos
    │   ├── any.ts
    │   ├── arrays.ts
    │   ├── booleans.ts
    │   ├── enums.ts
    │   ├── never.ts
    │   ├── null-undefined.ts
    │   ├── numbers.ts
    │   ├── strings.ts
    │   ├── tuples.ts
    │   └── void.ts
    └── tsconfig.json
```

Primero modificas el archivo `tsconfig.json` y luego eliminas los archivos `.map` y `.js`.

```json
{
  // Visit https://aka.ms/tsconfig to read more about this file
  "compilerOptions": {
    // File Layout
    // "rootDir": "./src",
    "outFile": "./main.js", 👈🏼👀
    // "outDir": "./dist",

    // Environment Settings
    "module": "amd", 👈🏼👀
    "target": "esnext",
    "types": [],

    // Other Outputs
    "sourceMap": true,
    "declaration": false,
    "declarationMap": false,

    "removeComments": true,

    // Stricter Typechecking Options
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true,

    // Recommended Options
    "strict": true,
    "jsx": "react-jsx",
    "verbatimModuleSyntax": false, 👈🏼👀
    "isolatedModules": false, 👈🏼👀
    "noUncheckedSideEffectImports": true,
    "moduleDetection": "force",
    "skipLibCheck": true
  },
  "exclude": [
    "node_modules", // Excluye la carpeta node_modules
    "dist", // Excluye la carpeta de salida
    "src/tests/**/*.ts" // Excluye archivos de pruebas
  ]
}
```

> Si estás usando una librería o framework, esto ya viene por defecto. 

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
    <script src="./main.js" type="module"></script>
  </body>
</html>
```

Recuerda que el archivo `app.ts` debe estar dentro de:

```ts
(()=> {
  ...
})()
```

Ahora el contenido de todos los otros archivos se va al main.js unificando el contenido.

📌 Nota: No he logrado ver los `console.log` en la web, debido a un error con `define` que no está definido. 🤷🏽‍♂️ Por lo demás sí se logra crear el `main.js`.

---

## 7. Características de ES6 o JavaScript2015 disponibles a través TypeScript

### 7.1 ¿Qué veremos en esta sección?

JavaScript va actualizando año con año, y tenemos que estar enterados de todo lo nuevo para saber cómo le sacamos el máximo provecho!

Esta sección esta orientada a enseñarles un par de cosas muy útiles y necesarias del ES6 (ES2015 o ECMAScript 6), que ya podemos utilizar con toda confianza en TypeScript.

Aprenderemos sobre:

1. Diferencia entre declarar variables con VAR y con LET
2. Uso de constantes
3. Plantillas literales
4. Funciones de flecha
5. Destructuración de objetos
6. Destructuración de Arreglos
7. Nuevo ciclo, el FOR OF
8. Conocer sobre la programación orientada a objetos
9. Clases

Al final, un examen práctico y teórico para afianzar los conocimientos.

### 7.2 Variables LET

> 🔥 En la clase anterior tuve problemas con la configuración de TypeScript así que esta vez intentaré con dos métodos diferentes, mostrados en el punto 2.3.

#### Var Let Const

En TypeScript, `var`, `let`, y `const` son palabras clave para declarar variables, pero difieren en su **ámbito (scope)** y **mutabilidad**: `var` tiene alcance de función/global y permite redeclaración; `let` tiene alcance de bloque (llaves `{}`) y permite reasignación, pero no redeclaración; y `const` también tiene alcance de bloque, pero su valor no puede ser reasignado (es de solo lectura), siendo la mejor opción por defecto para indicar intención y prevenir errores.

1. `var` (Antigua)

- **Ámbito (Scope):** Funcional o global. Se eleva (hoisting) al inicio de la función o script, permitiendo acceso antes de la declaración.
- **Mutabilidad:** Se puede reasignar y redeclarar dentro del mismo ámbito.
- **Uso:** No se recomienda en código moderno por su comportamiento impredecible, prefiriendo `let` y `const`.

2. `let` (Moderna)

- **Ámbito (Scope):** De bloque `{}`. Solo existe dentro de las llaves donde se declara (ej. `if`, `for`).
- **Mutabilidad:** Se puede reasignar (cambiar su valor), pero no redeclarar en el mismo ámbito.
- **Uso:** Ideal para variables cuyo valor necesita cambiar, como contadores en bucles.

3. `const` (Moderna)

- **Ámbito (Scope):** De bloque `{}` (igual que `let`).
- **Mutabilidad:** No se puede reasignar su valor. Debe ser inicializada al declararla.
- **Uso:** Para valores que no deben cambiar (constantes). Es la opción preferida por defecto, usar `let` solo si se necesita reasignar.

Recomendación en TypeScript

- **Usa `const` por defecto.** Si necesitas que el valor cambie, entonces usa `let`.
- **Evita `var`.** `let` y `const` ofrecen un manejo de ámbitos más predecible y seguro, mejorando la mantenibilidad del código.

#### Function vs Arrow function

En TypeScript, las funciones tradicionales y las funciones flecha (arrow functions) definen bloques de código reutilizables, pero las **arrow functions (`=>`)** ofrecen una sintaxis más concisa, son anónimas por naturaleza, y lo más importante, **capturan el contexto de `this`** del entorno donde se definen (en lugar de su propio `this`), lo que las hace ideales para callbacks y métodos cortos, mientras que las funciones tradicionales tienen su propio `this` (dinámico) y se usan más para constructores o métodos de clase. TypeScript añade la **tipificación fuerte** a ambas, permitiendo definir tipos para parámetros y retornos, mejorando la seguridad del código.

1. Funciones Tradicionales (Declaración y Expresión)

- **Sintaxis:** Usan la palabra clave `function`.
- **`this`:** Su `this` depende de cómo se llama (dinámico: objeto, constructor, global, etc.).
- **Uso:** Constructores de clases, métodos de objetos, funciones que necesitan su propio `this`.

Ejemplo:

```ts
function sumar(a: number, b: number): number {
    return a + b;
}
const restar = function(a: number, b: number): number {
    return a - b;
};
```

2. Funciones Flecha (Arrow Functions)

- **Sintaxis:** `(params) => { body }` o `(params) => expression` (retorno implícito).
- **`this`:** Léxico (hereda el `this` del scope padre).
- **Uso:** Callbacks (map, filter, reduce), funciones de una línea, métodos cortos.
- **Variantes:**
    - **Sin llaves (retorno implícito):** `(a, b) => a + b`.
    - **Con llaves (retorno explícito):** `(a, b) => { const res = a + b; return res; }`.
    - **Sin parámetros:** `() => console.log("Hola")`.
    - **Un parámetro (sin paréntesis):** `n => n * 2` (si hay varios, los paréntesis son obligatorios).

Ejemplo:

```ts
const multiplicar = (a: number, b: number): number => a * b;
const saludar = (nombre: string): void => {
    console.log(`Hola, ${nombre}`);
};
```

### 7.3 Desestructuración de Objetos

```ts
/* Destructuring */

type Avengers = {
  nick: string;
  ironman: string;
  vision: string;
  activo: boolean;
  poder: number;
};

const avengers: Avengers = {
  nick: 'Samuel L. Jackson',
  ironman: 'Robert Downey Jr.',
  vision: 'Paul Bettany',
  activo: true,
  poder: 123.123,
};

const { poder, vision } = avengers;

console.log(poder.toFixed(2), vision.toUpperCase());

const printAvenger = ({ ironman, ...rest }: Avengers) => {
  console.log(ironman);
  console.log({ rest });
  // Using Ctrl + Spacebar brings up the available options.
};

printAvenger(avengers);

// Console
Robert Downey Jr.
{
  rest: {
    nick: 'Samuel L. Jackson',
    vision: 'Paul Bettany',
    activo: true,
    poder: 123.123
  }
}
```

📌 Nota: al hacer `Ctrl + Barra espaciadora` aparecen las opciones disponibles del objeto.

La desestructuración en TypeScript es una característica de JavaScript que permite **desempaquetar valores de objetos o arrays en variables individuales de forma concisa**, haciendo el código más limpio y legible, especialmente al extraer propiedades o elementos dentro de funciones, aunque requiere anotar el tipo de la estructura completa (no de las variables individuales desestructuradas) para mantener la seguridad de tipos de TypeScript. 

¿Cómo funciona?

- **En Objetos**: En lugar de `const nombre = persona.nombre;`, usas `const { nombre } = persona;` para extraer la propiedad `nombre` directamente.
- **En Arrays**: Puedes extraer elementos en orden, como si fueran tuplas: `const [primero, segundo] = [1, 2];`.
- **En Parámetros de Funciones**: Desestructura los argumentos directamente en la firma de la función para acceder a sus propiedades sin usar `props.propiedad`, mejorando la legibilidad del cuerpo de la función. 

Consideraciones con TypeScript:

- **Anotación de Tipo**: No puedes anotar el tipo de cada variable individualmente tras la desestructuración (ej: `const { nombre: string } = persona;`). Debes anotar el tipo de la estructura completa.
    - **Ejemplo Incorrecto:** `const { nombre: string } = { nombre: "Ana" };`
    - **Ejemplo Correcto:** `const { nombre } = { nombre: "Ana" } as { nombre: string };` o mejor, definir un tipo/interfaz antes.
- **Mejor Práctica**: Define tipos o interfaces explícitas para tus objetos (ej: `interface Persona { nombre: string; edad: number; }`) y luego desestructura usando ese tipo, asegurando la tipificación estricta de TypeScript. 

Ejemplo:

```ts
interface Usuario {
  id: number;
  nombre: string;
}

function mostrarUsuario({ id, nombre }: Usuario) { // Desestructuración con anotación de tipo
  console.log(`ID: ${id}, Nombre: ${nombre}`);
}

const usuario = { id: 1, nombre: "Carlos" };
mostrarUsuario(usuario); // Salida: ID: 1, Nombre: Carlos
```

En resumen, la desestructuración es una forma elegante de manejar datos en JS/TS, y TypeScript te ayuda a hacerlo de forma segura mediante la tipificación de la estructura original.

### 7.4 Desestructuración de Arreglos

```ts
const avengersArr: string[] = [
  'Cap. América',
  'Ironman',
  'Hulk',
];

// Note the space between , , 👈🏼👀
const [ironman, , hulk] = avengersArr;
console.log({ ironman, hulk });

// We obtain
{ ironman: 'Cap. América', hulk: 'Hulk' }
```

### 7.5 Ciclo - For of

```ts
// For... of

type Avenger = {
  name: string;
  weapon: string;
};

const ironMan: Avenger = {
  name: 'Ironman',
  weapon: 'Armorsuit',
};

const captainAmerica: Avenger = {
  name: 'Captain America',
  weapon: 'Shield',
};

const thor: Avenger = {
  name: 'Thor',
  weapon: 'Mjolnir',
};

const avengers: Avenger[] = [ironMan, thor, captainAmerica];

for (const hero of avengers) {
  console.log(hero);
}

for (const { name, weapon } of avengers) {
  console.log(name, weapon);
}

// We obtain
{ name: 'Ironman', weapon: 'Armorsuit' }
{ name: 'Thor', weapon: 'Mjolnir' }
{ name: 'Captain America', weapon: 'Shield' }

Ironman Armorsuit
Thor Mjolnir
Captain America Shield
```

### 7.6 Clases en ES6

Para esta clase como estoy trabajando con otra configuración y viendo los cambios con Node desde la terminal integrada de VSC, debo hacer estas modificaciones:

`nodemon.json`

```json
{
  "watch": ["src"],
  "ext": "ts", // 👈🏼👀👇🏼 change ts to js (index.js)
  "exec": "node --loader ts-node/esm ./src/index.js"
}
```

`src/index.js`

```js
// Classes es6.js
class Avenger {
  // name; 👈🏼👀
  // power; 👈🏼👀

  constructor(name = 'No name', power = 123) {
    this.name = name;
    this.power = power;
  }
}

class FlyingAvenger extends Avenger {
  // flying; 👈🏼👀

  constructor(name = 'No name', power = 0) {
    super(name, power);
    this.flying = true;
  }
}

const hulk = new Avenger('Hulk', 9001);
const falcon = new FlyingAvenger('Falcon', 50);

console.log(hulk);
console.log(falcon);

// We obtain
Avenger { name: 'Hulk', power: 9001 }
FlyingAvenger { name: 'Falcon', power: 50, flying: true }
```

📌 Nota: en JS puedo comentar `name, power y flying`, pero si estuviera con TS no lo permite y marca error.

```bash
// to see the changes
npm run dev
```

### 7.7 Examen teórico #4

Practicando lo visto en clase.

### 7.8 Quiz 4: Examen teórico #4

1. ¿Las clases son una característica nueva del ES6?
	- Verdadero
2. ¿El siguiente código es válido en TypeScript?
	```ts
	const numero: number = 10;
	
	if(numero > 0) {
	  const numero: number = 10;
	}
	```
	- Verdadero: El IF, crea un nuevo scope o ámbito de la variable, por lo que si es válido.
3. ¿La desestructuración de arreglos permite extraer valores y asignarlos directamente a variables?
	- Verdadero
4. ¿Qué hace el siguiente código?
	```ts
	let frutas: string[] = ["Pera", "Manzana"];
	let [ pera, manzana ] = frutas;
	```
	- Crea dos variables con los nombres, pera y manzana, con los valores de pera y manzana respectivamente.
5. ¿La desestructuración de objetos permite extraer las propiedades directamente de un objeto?
	- Verdadero
6. ¿Puedo reemplazar VAR por LET en mis futuros desarrollos usando TypeScript?
	- Verdadero
7. En una función de flecha, ¿Qué valor tiene el objeto "THIS"?
	- Mantiene puntero de la referencia al "THIS" antes de entrar a la función.
	- En una función de flecha (arrow function) en JavaScript, `this` no tiene un valor propio, sino que hereda y mantiene el valor de `this` del contexto léxico que la rodea, es decir, del ámbito donde fue definida. Esto las hace muy útiles para evitar los problemas comunes de vinculación de `this` en callbacks y métodos anidados, manteniendo la referencia al `this` del padre o contenedor.
8. ¿Qué hace la siguiente línea de código?
	```ts
	let funcion = () => {};
	```
	- Declara una variable de tipo función que no hace nada.
9. ¿Por qué es importante conocer sobre las actualizaciones de JavaScript o ECMAScript?
	- Porque nos permite hacer más con menos código
	- Porque aprendemos sobre las nuevas bondades que podremos usar en un futuro cercano.
	- Porque así sabemos que podemos usar y que no en navegadores que no están tan actualizados.
	- ✅ Todas las anteriores
10. ¿Qué son las plantillas literales (Templates literales)?
	- Son strings que soportan multi línea, y permite incrustar variables o el producto de funciones dentro del mismo string.

### 7.9 Código fuente de la sección

Aquí les dejo el código fuente de la sección como material adjunto o bien el enlace al repositorio de Github del proyecto

[Klerith/ts-bases/tree/fin-seccion-7](https://github.com/Klerith/ts-bases/tree/fin-seccion-7)

---

## 8. Clases en TypeScript

### 8.1 ¿Qué veremos en esta sección?

La programación orientada a objetos es un tema sumamente importante, especialmente si nuestras aplicaciones van de mediana a gran escala. TypeScript trae toda la potencia de una programación orientada a objetos a la web.

Toda la sección se enfoca en enseñar sobre el uso de clases.

Puntualmente aprenderemos sobre:

1. Crear clases en TypeScript
2. Constructores
3. Accesibilidad de las propiedades:
    1. Públicas
    2. Privadas
    3. Protegidas
4. Métodos de las clases que pueden ser:
    1. Públicos
    2. Privados
    3. Protegidos
5. Herencia
6. Llamar funciones del padre, desde los hijos
7. Getters 
8. Setters
9. Métodos y propiedades estáticas
10. Clases abstractas
11. Constructores privados.

### 8.2 Definición de una clase básica en TypeScript

Estructura:

```bash
.
├── nodemon.json
├── package.json
├── package-lock.json
├── src
│   ├── classes
│   │   └── basic.ts
│   └── index.ts
└── tsconfig.json
```

`src/classes/basic.ts`

```ts
export class Avenger {
  private name: string;
  private team: string;

  // Si no se coloca nada por defecto es public
  // If nothing is set by default, it is public.
  public realName?: string | undefined;
  static avgAge: number = 35;

  constructor(name: string, team: string, realName?: string) {
    this.name = name;
    this.team = team;
    this.realName = realName;
  }
}

export const antman: Avenger = new Avenger(
  'Antman',
  'Capitan'
);

console.log(Avenger.avgAge);
```

`src/index.ts`

```ts
import { antman, Avenger } from './classes/basic.js';

console.log(Avenger.avgAge);
console.log(antman);
```

La consola de vsc muestra:

```bash
35
Avenger { name: 'Antman', team: 'Capitan', realName: undefined }
```

En JavaScript, `static`, `public` y `private` definen el **ámbito y la accesibilidad** de las propiedades y métodos dentro de una clase: `public` es accesible desde cualquier lugar; `private` (con `#`) solo dentro de la clase; y `static` hace que la propiedad pertenezca a la clase misma, no a las instancias, siendo accesible sin crear un objeto y útil para datos compartidos como cachés o configuraciones, aunque `private static` restringe su acceso solo a la clase, según MDN Web Docs, Stack Overflow y SitePoint. 

Modificadores de acceso (Public / Private)

- **`public` (por defecto):** La propiedad o método es accesible y modificable desde _cualquier_ parte del código, tanto dentro como fuera de la clase. Es el comportamiento por defecto si no se especifica nada.
- **`private` (con `#`):** La propiedad o método solo es accesible y modificable _dentro de la misma clase_. Esto se implementa en JS añadiendo un `#` delante del nombre (ej. `#miPropiedad`) y ayuda a ocultar detalles de implementación (encapsulamiento). 

Modificador de instancia (Static)

- **`static`:** La propiedad o método pertenece a la _clase en sí misma_, no a las instancias individuales de la clase.
    - Se puede acceder directamente usando el nombre de la clase (ej. `MiClase.miDato`) sin necesidad de crear un objeto (`new MiClase()`).
    - Es ideal para almacenar datos o funciones que son compartidos por todas las instancias, como constantes, contadores o cachés. 

Combinaciones comunes

- **`public static`:** Un dato compartido por todas las instancias, accesible desde cualquier lugar (ej. `MiClase.config = {...}`).
- **`private static`:** Un dato compartido por la clase pero inaccesible desde fuera, solo desde métodos estáticos o de la propia clase (ej. `#contadorInterno`).
- **`public` (sin `static`):** Una propiedad normal que existe en cada instancia (ej. `this.nombre = '...'`), común para datos específicos de cada objeto. 

**En resumen:** `static` define si es de la clase o la instancia, mientras que `public`/`private` define quién puede verlo/usarlo.

### 8.3 Forma corta de asignar propiedades

`src/classes/basic.ts`

```ts
export class Avenger {
  static avgAge: number = 35;

  constructor(
    private name: string,
    private team: string,
    public realName?: string
  ) {}
}

export const antman: Avenger = new Avenger(
  'Antman',
  'Capitan',
  'Scott Lang'
);
```

La consola de vsc muestra:

```bash
35
Avenger { name: 'Antman', team: 'Capitan', realName: 'Scott Lang' }
```

### 8.4 Métodos públicos y privados

`src/classes/basic.ts`

```ts
export class Avenger {
  static avgAge: number = 35;
  
  // El método static vive en la clase, no en los objetos
  static getAvgAge() {
    // This es la clase Avenger
    // Obtener el nombre de la clase
    return this.name;
  }

  constructor(
    private name: string,
    private team: string,
    public realName?: string
  ) {}

  // es public por defecto
  bio() {
    return `${this.name} (${this.team})`;
  }
}

export const antman: Avenger = new Avenger(
  'Antman',
  'Capitan',
  'Scott Lang'
);
```

`src/index.ts`

```ts
import { antman, Avenger } from './classes/basic.js';

console.log(Avenger.avgAge);
console.log(antman);
console.log(antman.bio());

// Por eso los métodos statics se obtienen de esta manera
console.log(Avenger.getAvgAge());
```

La consola de vsc muestra:

```bash
35
Avenger { name: 'Antman', team: 'Capitan', realName: 'Scott Lang' }
Antman (Capitan)
Avenger // resultado de método static getAvgAge this.name
```

#### `this.name` dentro de `bio()`

```ts
bio() {
  return `${this.name} (${this.team})`;
}
```

El `this` que está dentro de `bio()` apunta a la instancia creada por el constructor.

En este caso:

```ts
const antman = new Avenger('Antman', 'Capitan', 'Scott Lang');
```

Entonces:

```ts
this === antman
this.name === 'Antman'
```

- El constructor **inicializa** las propiedades  
- `this` en métodos de instancia **siempre es la instancia**

Resultado:

```bash
Antman (Capitan)
```

#### `this.name` dentro de un método `static`

```ts
static getAvgAge() {
  return this.name;
}
```

El `this` que está dentro del método `static` apunta a la clase `Avenger`. Y la clase tiene una propiedad por defecto que se llama `"name"`, por eso es que al retornar `this` se muestra `"Avenger"`.

En un método `static`:

```ts
// No existe instancia aquí
this === Avenger
```

Entonces:

```ts
this.name === Avenger.name
```

#### Dato sobre Funciones

Todas las clases en JavaScript son funciones y traen por defecto algunas propiedades:

- name
- length

Internamente:

```ts
class Avenger {}
```

Es equivalente a:

```js
function Avenger() {}
```

Y **todas las funciones en JS tienen una propiedad `name`**:

```ts
Avenger.name === 'Avenger'
```

Por eso:

```ts
static getAvgAge() {
  return this.name;
}
```

retorna:

```bash
Avenger
```

Más preciso sería decir:

> La clase `Avenger`, al ser una función, hereda la propiedad `name` de las funciones de JavaScript.

#### 💡 Recomendación (buena práctica)

Este método puede confundir:

```ts
static getAvgAge() {
  return this.name;
}
```

Sería más claro:

```ts
static getClassName() {
  return Avenger.name;
}
```

O mejor aún, usarlo solo con fines didácticos 👍

### 8.5 Herencia, super y extends

`src/classes/extends.ts`

```ts
class Avenger {
  constructor(public name: string, public realName: string) {
    console.log('Avenger Constructor!!!');
  }

  protected getFullname() {
    // this es/apunta al objeto instanciado (hero.name)
    return `${this.name} ${this.realName}`;
  }
}

class Xmen extends Avenger {
  constructor(
    name: string,
    realName: string,
    public isMutant: boolean
  ) {
    // Ejecuta el constructor del padre, pasandole los datos que necesita
    super(name, realName);

    console.log('Xmen Constructor (Son)!!!');
    console.log('Son: ', this.getFullname());
  }

  getFullnameDesdeXmen() {
    // Object:  Xmen { name: 'Wolverine', realName: 'Logan', isMutant: true }
    console.log('Object: ', this);
    
    // Super ejecuta la versión del método que está en Avenger
    console.log('Super: ', super.getFullname());
    
    // This busca getFullname empezando desde el objeto
    console.log('This: ', this.getFullname());
    // JS busca en Xmen, no lo encuentra, sube al prototipo Avenger
    // lo ejecuta. Resultado: el mismo método
  }
}

// El constructor se ejecuta al instanciar
const hero = new Avenger('Ghost', 'Ale');
const wolverine = new Xmen('Wolverine', 'Logan', true);

console.log(hero);

console.log(wolverine);
wolverine.getFullnameDesdeXmen();
```

`src/index.ts`

```ts
import "./classes/extends.js"
```

La consola de VSC muestra:

```bash
Avenger Constructor!!!
Avenger Constructor!!!
Xmen Constructor (Son)!!!
Son:  Wolverine Logan
Avenger { name: 'Ghost', realName: 'Ale' }
Xmen { name: 'Wolverine', realName: 'Logan', isMutant: true }
Object:  Xmen { name: 'Wolverine', realName: 'Logan', isMutant: true }
Super:  Wolverine Logan
This:  Wolverine Logan
```

#### Constructor

```ts
class Avenger {
  constructor(
    protected name: string,
    protected power: number
  ) {}
}

class Xmen extends Avenger {
  constructor(
    name: string,
    power: number,
    public team: string
  ) {
    super(name, power);
  }
}
```

🔹 En `Avenger`

```ts
class Avenger {
  constructor(
    protected name: string,
    protected power: number
  ) {}
}
```

El constructor:

- Se ejecuta **cuando haces `new Avenger(...)`**
- Inicializa el estado interno del objeto
- Crea y asigna las propiedades `name` y `power`

👉 Sin constructor, la clase **no sabría cómo inicializar sus datos**.

🔹 En `Xmen`

```ts
class Xmen extends Avenger {
  constructor(
    name: string,
    power: number,
    public team: string
  ) {
    super(name, power);
  }
}
```

El constructor de `Xmen`:

- Inicializa **sus propias propiedades** (`team`)
- Y **delegará** la inicialización de `name` y `power` al constructor de `Avenger`

📌 Importante:

> El constructor del padre **NO se ejecuta automáticamente** si el hijo tiene constructor.

#### Extends

```ts
class Xmen extends Avenger
```

`extends` indica **herencia**

Esto quiere decir:

- `Xmen` **hereda** propiedades y métodos de `Avenger`
- `Xmen` es un tipo de `Avenger`

👉 En términos simples:

> Todo `Xmen` es un `Avenger`, pero no todo `Avenger` es un `Xmen`.

📌 `extends` **sí pertenece a JavaScript (ES6)**  
TypeScript **solo agrega tipado**, no cambia el comportamiento.

#### Protected

```ts
protected name: string;
```

❌ No pertenece a JavaScript  
✔️ Es **TypeScript puro**

|Modificador  |Acceso desde la clase  |Acceso desde hijos|Acceso externo|
|-------------|-----------------------|------------------|--------------|
|`public`    |✅                    |✅                |✅            |
|`protected` |✅                    |✅                |❌            |
|`private`   |✅                    |❌                |❌            |

`protected` permite que:

- `Avenger` use `name`
- `Xmen` también use `name`
- Pero **nadie desde fuera pueda acceder**

```ts
class Xmen extends Avenger {
  showName() {
    return this.name; // ✅ permitido
  }
}
```

En Programación Orientada a Objetos (POO), un método `protected` es aquel que es accesible **dentro de la misma clase** donde se define y en **todas las clases que heredan (subclases)** de ella, incluso si están en paquetes diferentes, pero no es accesible desde clases externas o ajenas a la jerarquía de herencia, permitiendo una encapsulación intermedia entre `public` y `private` para compartir lógica interna con descendientes.

#### super

```ts
super(name, power);
```

`super` es una **referencia a la clase padre (`Avenger`)**. Si el hijo no tiene constructor, **hereda el del padre automáticamente**

📌 En un constructor:

> `super(...)` **ejecuta el constructor del padre**

En JavaScript:

- Si una clase hija tiene constructor
- **DEBE llamar a `super()`**
- Antes de usar `this`

❌ Esto sería error:

```ts
constructor(...) {
  this.team = 'Xmen'; // ❌
  super(name, power);
}
```

✔️ El orden correcto:

```ts
constructor(...) {
  super(name, power);
  this.team = 'Xmen';
}
```

¿Por qué pasar otra vez los mismos datos de padre a hijo?

> “¿Por qué nuevamente pasamos `name` y `power` en el constructor de `Xmen`?”

🔹 Respuesta corta:

Porque **el padre los necesita para inicializarse**

🔹 Qué está pasando realmente

```ts
new Xmen('Wolverine', 900, 'X-Men');
```

1️⃣ Se llama al constructor de `Xmen`  
2️⃣ `Xmen` **NO sabe** cómo inicializar `name` y `power`  
3️⃣ Entonces dice:

```ts
super(name, power);
```

4️⃣ Se ejecuta el constructor de `Avenger`  
5️⃣ `Avenger` asigna:

```ts
this.name = name;
this.power = power;
```

📌 **Cada clase es responsable de inicializar sus propios datos**

Analogía sencilla (muy importante)

Imagina una fábrica:

- `Avenger` → fabrica cuerpos
- `Xmen` → fabrica cuerpos + uniformes

```ts
super(name, power);
```

Es como decir:

> “Primero construye el cuerpo como sabe hacerlo Avenger, luego yo agrego lo mío”

Resumen mental definitivo

✔️ `constructor`  
→ Inicializa el objeto

✔️ `extends`  
→ Herencia (ES6, JS real)

✔️ `protected`  
→ Solo TypeScript (control de acceso)

✔️ `super()`  
→ Llama al constructor del padre

✔️ Pasar datos a `super`  
→ El padre **no recibe magia**, recibe datos

### 8.6 Gets y Sets

`./src/classes/extends.ts`

```ts
class Avenger {
  constructor(public name: string, public realName: string) {
    console.log('Avenger Constructor!!!');
  }

  protected getFullname() {
    // this es/apunta al objeto instanciado (hero.name)
    return `${this.name} ${this.realName}`;
  }
}

class Xmen extends Avenger {
  constructor(
    name: string,
    realName: string,
    public isMutant: boolean
  ) {
    // Ejecuta el constructor del padre
    super(name, realName);

    console.log('Xmen Constructor (Son)!!!');
  }

  get fullName() { 👈🏼👀👇🏼
    return `${this.name} - ${this.realName}`;
  }

  set fullName(name: string) { 👈🏼👀👇🏼
    if (name.length < 3) {
      throw new Error(
        'El nombre debe de ser mayor a 3 letras!'
      );
    }

    // No regresa nada y recibe un solo argumento
    this.name = name;
  }

  getFullnameDesdeXmen() {
    // Super ejecuta la versión del método que está en Avenger
    console.log('Super: ', super.getFullname());
  }
}

// El constructor se ejecuta al instanciar
const wolverine = new Xmen('Wolverine', 'Logan', true);

wolverine.fullName = 'Ale'; 👈🏼👀
console.log(wolverine.fullName);
```

`src/index.ts`

```ts
import './classes/extends.js';
```

La consola de VSC muestra:

```bash
Avenger Constructor!!!
Xmen Constructor (Son)!!!
Ale - Logan
```

Los **getters** y **setters** en JavaScript son métodos especiales (`get` y `set`) que controlan el acceso a las propiedades de un objeto, permitiendo leer (get) y escribir (set) valores de forma controlada, validar datos, o realizar cálculos antes de devolverlos o asignarlos, simulando el acceso directo a una propiedad, pero ejecutando lógica interna. Son clave para la encapsulación, ocultando la implementación interna y exponiendo una interfaz pública para manipular atributos, a menudo guardados en una propiedad privada (con `_` al inicio). 

- **Getter (`get`)** → _leer_ una propiedad
- **Setter (`set`)** → _modificar_ una propiedad

¿Cómo funcionan?

- **`get` (Getter):** Una función que se ejecuta cuando intentas **leer** el valor de una propiedad. No toma argumentos y devuelve un valor.
- **`set` (Setter):** Una función que se ejecuta cuando intentas **asignar** un valor a una propiedad. Toma un argumento (el nuevo valor) y puede validarlo o procesarlo antes de guardarlo. 

Ejemplo práctico:

```js
let persona = {
  nombre: 'Juan',
  apellidos: 'Pérez',
  
  // Getter para obtener el nombre completo
  get nombreCompleto() {
    return this.nombre + ' ' + this.apellidos;
  },
  
  // Setter para cambiar nombre y apellidos
  set nombreCompleto(valor) {
    const partes = valor.split(' ');
    this.nombre = partes[0];
    this.apellidos = partes[1];
  }
};

// Usando el getter (se llama como una propiedad)
console.log(persona.nombreCompleto); // Salida: Juan Pérez

// Usando el setter (se llama como una asignación)
persona.nombreCompleto = 'Ana García';
console.log(persona.nombre); // Salida: Ana
console.log(persona.apellidos); // Salida: García
```

Ventajas:

- **Encapsulación:** Controlas qué y cómo se accede a los datos de un objeto, protegiéndolos de modificaciones inválidas.
- **Validación:** Puedes asegurar que solo se asignen valores válidos (ej. un número entre 1 y 6).
- **Cálculos "perezosos":** Puedes calcular un valor solo cuando se necesita, no al crear el objeto.
- **Abstracción:** Ocultas la complejidad interna al usuario del objeto, que interactúa con propiedades simples.

### 8.7 Clases Abstractas

`./src/classes/abstract.ts`

```ts
abstract class Mutant {
  constructor(public name: string, public realName: string) {}
}

class Xmen extends Mutant { 👈🏼👀
  greetWorld() {
    return 'Greet world!';
  }
}

class Villian extends Mutant {
  conquerWorld() {
    return 'Conquer World!';
  }
}

// Esto es un error 👀👇🏼
// const newMutant = new Mutant('Ale', 'Ghost');

const wolverine = new Xmen('Wolverine', 'Logan'); 👈🏼👀
const magneto = new Villian('Magneto', 'Magnus');

console.log(wolverine);
console.log(wolverine.greetWorld());
console.log(magneto.conquerWorld());

const printName = (character: Mutant) => { 👈🏼👀
  console.log(character.realName);
};

printName(wolverine);
printName(magneto);

// Sirven para:
// Crear, extender otras clases
// Asegurarse que otras clases hagan lo que se espera
// Especificar que espero una clase, objeto o argumento
// que haya sido extendido de un tipo
```

`src/index.ts`

```ts
import './classes/abstract.js';
```

La consola de VSC muestra:

```bash
Avenger Constructor!!!
Xmen Constructor (Son)!!!
Ale - Logan
```

Las clases abstractas en TypeScript son **plantillas para otras clases que no se pueden instanciar directamente**, sirviendo como base para la herencia y definiendo una estructura común para las subclases, que deben implementar sus métodos abstractos (sin cuerpo), mientras que la clase base puede tener métodos concretos ya implementados, reutilizando lógica y forzando un contrato de implementación. 

Características clave:

- **No instanciables:** No puedes crear un objeto `new MiClaseAbstracta()`.
- **`abstract` keyword:** Se usa `abstract class` para declararla y `abstract method()` para un método sin implementación.
- **Herencia obligatoria:** Las clases que heredan (`extends`) de una clase abstracta deben implementar todos sus métodos abstractos.
- **Métodos concretos:** Pueden tener métodos normales con código (no abstractos) para compartir lógica entre subclases.
- **Uso:** Definen un "contrato" o "molde" para un grupo de clases relacionadas (ej: `Animal` con método `hacerSonido()`, que luego implementan `Perro`, `Gato`, etc.). 

Ejemplo:

```ts
abstract class Animal {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    // Método concreto (implementado)
    mostrarNombre(): void {
        console.log(`Soy un animal llamado ${this.name}`);
    }

    // Método abstracto (debe ser implementado por las subclases)
    abstract hacerSonido(): void;
}

class Perro extends Animal {
    constructor(name: string) {
        super(name);
    }

    // Implementación del método abstracto
    hacerSonido(): void {
        console.log("¡Guau guau!");
    }
}

// let miAnimal = new Animal("Genérico"); // ERROR: No se puede instanciar

let miPerro = new Perro("Fido");
miPerro.mostrarNombre(); // Salida: "Soy un animal llamado Fido"
miPerro.hacerSonido();    // Salida: "¡Guau guau!"
```

### 8.8 Constructores privados

Implementación del patrón Singleton:

Garantiza que solo exista UNA única instancia de la clase durante toda la ejecución del programa.

`./src/classes/private-constructor.ts`

```ts
// Implementación del patrón Singleton
// Garantiza que solo exista UNA única instancia de la clase
// durante toda la ejecución del programa.

// Clase que solo puede tener una instancia
class Apocalipsis {
  // Propiedad estática (pertenece a la clase, no a la instancia)
  // Guarda la única instancia de la clase Singleton
  // “La caja donde guardamos al único Apocalipsis que puede existir”
  static instance: Apocalipsis;

  // Constructor privado:
  // Impide crear instancias usando `new` desde fuera de la clase
  // Solo la propia clase puede crear instancias
  private constructor(public name: string) {}

  // Método estático:
  // Es static → se llama desde la clase, no desde una instancia
  // Es el único punto de acceso para obtener la instancia
  static callApocalipsis(): Apocalipsis {
    // Si aún no existe la instancia, se crea
    if (!Apocalipsis.instance) {
      Apocalipsis.instance = new Apocalipsis(
        'Soy apocalipsis'
      );
      // El `new` solo se ejecuta una sola vez
    }

    // Si ya existe, se reutiliza
    // Siempre devuelve la misma referencia en memoria
    return Apocalipsis.instance;
  }

  // Método de instancia
  // Usa `this` → apunta a la instancia única
  // Modifica el estado del Singleton
  changeName(newName: string): void {
    this.name = newName;
  }
  // Si cambias el nombre aquí, se refleja en todas las referencias
}

// Uso del Singleton

// Único punto de acceso
// Primera llamada → no existe instancia, se crea
// name = 'Soy apocalipsis'
const apocalipsis = Apocalipsis.callApocalipsis();
console.log(apocalipsis);

// Se modifica el estado de la instancia única
apocalipsis.changeName('Xavier');

// Todas las llamadas devuelven el mismo objeto
// NO se crean objetos nuevos, todos apuntan al mismo objeto en memoria
const apoca1 = Apocalipsis.callApocalipsis();
const apoca2 = Apocalipsis.callApocalipsis();
const apoca3 = Apocalipsis.callApocalipsis();

// Todas las variables apuntan a la misma instancia
console.log({ apoca1, apoca2, apoca3 });

// Resultado
// ✔️ Misma instancia
// ✔️ Mismo nombre
// ✔️ Mismo estado

// Resumen
// - static instance → guarda la única instancia
// - constructor private → bloquea el uso de `new`
// - método static → controla la creación
// - siempre devuelve/reutiliza el mismo objeto
```

📌 Nota: `callApocalipsis()` funciona, pero en proyectos reales suele llamarse `getInstance()`

`src/index.ts`

```ts
import './classes/private-constructor.js';
```

La consola de VSC muestra:

```bash
Apocalipsis { name: 'Soy apocalipsis' }
{
  apoca1: Apocalipsis { name: 'Xavier' },
  apoca2: Apocalipsis { name: 'Xavier' },
  apoca3: Apocalipsis { name: 'Xavier' }
}
```

Los constructores privados en TypeScript son un patrón de diseño que **restringe la creación de instancias de una clase desde fuera**, permitiendo que solo se creen internamente, idealmente para implementar el patrón Singleton (una sola instancia) o para controlar la inicialización compleja, a menudo usando un método estático (`getInstance()`) para gestionar la creación controlada del objeto único.

¿Cómo funcionan?

1. **Declaración**: Se define el constructor con la palabra clave `private`, por ejemplo: `private constructor() { ... }`.
2. **Restricción**: Esto impide que otras partes del código usen `new MiClase()` directamente, lanzando un error de compilación.
3. **Singleton**: Para permitir la creación controlada, se añade:
    - Una propiedad estática privada (`private static instance: MiClase;`) para guardar la única instancia.
    - Un método estático público (`public static getInstance()`) que verifica si la instancia existe; si no, la crea usando el constructor privado y la guarda; si ya existe, la devuelve. 

Usos comunes

- **Patrón Singleton**: Asegurar que una clase solo tenga una instancia (por ejemplo, para una conexión a base de datos o un gestor de configuración).
- **Inicialización compleja**: Cuando la creación de un objeto necesita lógica asíncrona o dependencias que deben resolverse antes de poder instanciar la clase.
- **Clases de utilidad**: Para clases que solo contienen métodos estáticos, como la clase `Math`, para evitar que se instancien objetos innecesarios. 

Ejemplo (Singleton)

```ts
class Singleton {
  private static instance: Singleton;
  public message: string;

  private constructor() {
    // Constructor privado
    this.message = '¡Soy la única instancia!';
    // Aquí podría haber lógica de inicialización costosa
  }

  public static getInstance(): Singleton {
    // Método estático para obtener la instancia
    if (!Singleton.instance) {
      Singleton.instance = new Singleton(); // Solo se crea aquí
    }
    return Singleton.instance;
  }
}

// No se puede hacer: const s1 = new Singleton(); // Error: Constructor privado

const s1 = Singleton.getInstance(); // Correcto
const s2 = Singleton.getInstance(); // Devuelve la misma instancia

console.log(s1.message); // "¡Soy la única instancia!"
console.log(s1 === s2); // true
```

### 8.9 Código fuente de la sección

Les dejo el código del proyecto hasta este punto y también el repositorio de GitHub por si lo quieren tener a la mano.

[Github- Fin-seccion-8](https://github.com/Klerith/ts-bases/tree/fin-seccion-8)

- [ts-bases-fin-seccion-8.zip](https://import.cdn.thinkific.com/643563/courses/1870132/tsbasesfinseccion8-220523-092546.zip)

## 9. Interfaces

### 9.1 ¿Qué veremos en esta sección?

Esta sección está dedicada a crear interfaces, las cuales nos permitirán crear reglas o planos de como se deben de construir clases, métodos u objetos.

Puntualmente aprenderemos:

1. ¿Por qué es necesario una interfaz?
2. ¿Cómo creamos una interfaz básica?
3. Crear propiedades opcionales
4. Crear métodos
5. Asignar interfaces a las clases

Al final, tendremos un examen práctico y teórico sobre las interfaces.

### 9.2 Interfaz básica

`./src/interfaces/basic.ts`

```ts
interface Hero {
  name: string;
  age?: number;
  powers: number[];
  getName?: () => string;
}

let flash: Hero = {
  name: 'Barry Allen',
  age: 24,
  powers: [1, 2],
};

console.log(flash.name);
```

`src/index.ts`

```ts
import './interfaces/basics.js';
```

La consola de VSC muestra:

```bash
Barry Allen
```

Se usa `interface` para definir la **forma de objetos**, contratos para clases y aprovechar la **fusión de declaraciones**; mientras que `type` es más versátil para **alias** de tipos primitivos, uniones (`|`), intersecciones (`&`), tuplas y tipos complejos que `interface` no puede manejar directamente, siendo la elección personal a menudo una cuestión de preferencia, aunque TS recomienda `interface` por defecto para objetos. 

Usa `interface` cuando:

- **Defines la forma de un objeto:** Es ideal para describir la estructura de datos, como `{ nombre: string, edad: number }`.
- **Necesitas extensión:** Permite extender otras interfaces (usando `extends`) y se pueden fusionar interfaces del mismo nombre para añadir propiedades, una característica útil para librerías.
- **Trabajas con clases (contratos):** Define contratos para que las clases implementen.
- **Prefieres la convención:** La recomendación general es usar `interface` por defecto para objetos. 

```ts
// interface
interface Usuario {
  id: number;
  nombre: string;
}

interface Admin extends Usuario { // Extiende Usuario
  permisos: string[];
}
```

Usa `type` cuando:

- **Necesitas uniones (OR) o intersecciones (AND):** Crea tipos complejos como `type ID = string | number` o `type PersonaCompleta = Usuario & { email: string }`.
- **Creas alias para tipos primitivos:** `type Email = string;`.
- **Trabajas con tuplas:** `type Coordenadas = [number, number];`.
- **No necesitas fusión de declaraciones:** `type` no permite la fusión de declaraciones del mismo nombre.
- **Creas tipos primitivos o complejos que no son objetos:** Como `type Estado = 'activo' | 'inactivo';` o `type Resultado = string | null;`. 

```ts
// type
type Estado = 'activo' | 'inactivo'; // Unión
type Coordenadas = [number, number]; // Tupla
type ID = string | number; // Unión
```

Conclusión:

- **Predeterminado:** Usa `interface` para objetos y `type` para uniones/intersecciones o tipos primitivos.
- **Consistencia:** Lo más importante es elegir uno y ser consistente en tu proyecto para mantener la claridad.

[Differences Between Type Aliases and Interfaces](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#differences-between-type-aliases-and-interfaces)

### 9.3 Estructuras complejas

`./src/interfaces/complex.ts`

```ts
interface Client {
  name: string;
  age?: number;
  address: Adress;
}

interface Adress {
  id: number;
  zip: string;
  city: string;
}

const client: Client = {
  name: 'Ale',
  age: 25,
  address: {
    city: 'Toronto',
    id: 120,
    zip: 'K2S U2A',
  },
};
```

### 9.4 Métodos en la interfaz

`./src/interfaces/complex.ts`

```ts
interface Client {
  name: string;
  age?: number;
  address: Address;
  // Correcto para objetos/clases 👀👇🏼
  getFullAddress(id: string): string;
  // Tipo función 👀👇🏼
  // getFullAddress: (id: string) => void;
}

interface Address {
  id: number;
  zip: string;
  city: string;
}

const client: Client = {
  name: 'Ale',
  age: 25,
  address: {
    city: 'Toronto',
    id: 120,
    zip: 'K2S U2A',
  },
  getFullAddress(id: string) {
    return this.address.city;
  },
};
```

No confundir con tipo función:

```ts
let getFullAddress: (id: string) => void;

getFullAddress = (name) => {
  console.log(name);
};
```

Ver [[TypeScript_Tu-completa-guia-y-manual-de-mano#4.7 Tipo Función]]

#### Formas de declarar métodos en una `interface`

1. **método (method signature)**

```ts
getFullAddress(id: string): void;
```

Esto significa:

> “Esta interfaz tiene un **método** llamado `getFullAddress` que recibe un `string` y **retorna void**”

Es la forma **clásica**, similar a una clase.

✔ Ventajas:

- Más legible
- Mejor para métodos que usan `this`
- Es la forma recomendada para **interfaces de objetos/clases**

2. **propiedad cuyo valor es una función**

```ts
getFullAddress: (id: string) => void;
```

Esto significa:

> “Esta interfaz tiene una **propiedad** llamada `getFullAddress`, y su valor es una función”

Aquí **no es un método**, es una propiedad que guarda una función.

✔ Ventajas:

- Muy usada en **callbacks**
- Común en React, Zustand, handlers, etc.

#### Diferencia CLAVE entre ambas

`this` NO se comporta igual

- Método (correcto para objetos)

```ts
getFullAddress(id: string): void {
  console.log(this.address.city);
}
```

➡️ `this` apunta correctamente al objeto `client`.

- Propiedad con arrow function

```ts
getFullAddress: (id: string) => {
  console.log(this.address.city);
}
```

🚨 **Problema**:  
Las arrow functions **NO tienen su propio `this`**  
`this` se toma del contexto externo → puede romperse fácilmente.

👉 Por eso **para objetos con estado**, se recomienda la forma de **método**.

#### ¿Cuándo usar cada forma?

🧠 **Regla simple**:

- 🔹 **Objetos / clases / modelos** → usa **métodos**
    
    ```ts
    metodo(): tipo
    ```
    
- 🔹 **Callbacks / handlers / funciones externas** → usa **propiedad función**
    
    ```ts
    handler: () => tipo
    ```

### 9.5 Interfaces en las clases

`./src/interfaces/classes.ts`

```ts
interface Xmen {
  name: string;
  realName: string;
  mutantPower(id: number): string;
}

interface Human {
  age: number;
}

class Mutant implements Xmen, Human {
  constructor(
    public name: string,
    public realName: string,

    public age: number
  ) {}

  public mutantPower(id: number) {
    return this.name + ' ' + this.realName;
  }
}
```

En TypeScript, `implements` es una palabra clave que **obliga a una clase a cumplir con un "contrato" definido por una interfaz**, asegurando que la clase implemente todas las propiedades y métodos declarados en esa interfaz, proporcionando sus propias implementaciones concretas para ellos, a diferencia de `extends` que hereda código directamente.

¿Qué hace `implements`?

- **Garantía de Contrato:** Actúa como un contrato. Si una clase declara que implementa una InterfazA, debe incluir todas las firmas (nombres y tipos) de las propiedades y métodos definidos en `InterfazA`.
- **Compromiso de Implementación:** La clase debe proporcionar el cuerpo (la lógica) para todos esos métodos que estaban definidos solo como firmas en la interfaz.
- **Errores de Compilación:** Si la clase omite una propiedad o método, o si la firma no coincide, TypeScript marcará un error, asegurando la consistencia.

### 9.6 Interfaces para las funciones

`./src/interfaces/functions.ts`

```ts
interface addTwoNumbers {
  (a: number, b: number): number;
}

let addNumbersFunction: addTwoNumbers;

addNumbersFunction = (a: number, b: number) => {
  return 10;
};
```

### 9.7 Ejercicio práctico #5: Implementación de interfaces

Por favor descarguen y descompriman el archivo adjunto y procedan a la siguiente clase donde les daré la introducción de lo que quiero que hagan

- [app.ts.zip](https://import.cdn.thinkific.com/643563/courses/1870132/appts-220523-102530.zip)

### 9.8 Tarea y Resolución del ejercicio práctico #5

`./src/app.ts`

```ts
// Crear interfaces

// Cree una interfaz para validar el auto (el valor enviado por parametro)
interface Auto {
  encender: boolean;
  velocidadMax: number;
  acelerar(): void;
}

const conducirBatimovil = (auto: Auto): void => {
  auto.encender = true;
  auto.velocidadMax = 100;
  auto.acelerar();
};

const batimovil: Auto = {
  encender: false,
  velocidadMax: 0,
  acelerar() {
    console.log('...... gogogo!!!');
  },
};

// Cree una interfaz con que permita utilzar el siguiente objeto
// utilizando propiedades opcionales

interface Guason {
  reir?: boolean;
  comer?: boolean;
  llorar?: boolean;
}

const guason: Guason = {
  reir: true,
  comer: true,
  llorar: false,
};

const reir = (guason: Guason): void => {
  if (guason.reir) {
    console.log('JAJAJAJA');
  }
};

// Cree una interfaz para la siguiente funcion

interface CityFn {
  (ciudadanos: string[]): number;
}

const ciudadGotica: CityFn = (
  ciudadanos: string[]
): number => {
  return ciudadanos.length;
};

// Cree una interfaz que obligue crear una clase
// con las siguientes propiedades y metodos

interface Person {
  nombre: string;
  edad: number;
  sexo: 'M' | 'F';
  estadoCivil: string;
  imprimirBio(): void;
}

/*
  propiedades:
    - nombre
    - edad
    - sexo
    - estadoCivil
    - imprimirBio(): void // en consola una breve descripcion.
*/
class Persona implements Person {
  constructor(
    public nombre: string,
    public edad: number,
    public sexo: 'M' | 'F',
    public estadoCivil: string
  ) {}

  public imprimirBio(): void {}
}
```

### 9.9 Quiz 5: Examen teórico #5

Reforzando los conocimientos.

### 9.10 Quiz 5: Examen teórico #5

1. ¿Qué son las interfaces?  
	- Son como contratos que nos obligan a respetar las reglas que establezcamos.
	
2. ¿Es posible crear interfaces para permitir o denegar qué podemos asignar a una función?  
	- Verdadero
	
3. ¿Este es el producto de la interfaz "Carro" en JavaScript?  
	```ts
	// TypeScript
	interface Carro {
	  nombre: string;
	}
	
	// JavaScript
	function Carro(carro) {
	  this.carro = carro;
	}
	```
	- Falso: Las interfaces solo existen en TypeScript, por lo que no crea nada en JavaScript
	
4. ¿Con qué palabra reservada podemos implementar una interface en una clase?  
	- implements
	
5. ¿Cuál es el objetivo de una implementación de una interface en una clase?  
	- Nos obliga a que la clase que implemente la interfaz tenga al menos las propiedades y métodos definidos en dicha interfaz.
	
6. ¿Es posible asignar a una variable, el tipo de una interfaz?  
	- Verdadero
	
7. En una interfaz, ¿Solo hay que definir las propiedades y métodos que son obligatorios?  
	- Falso: Pueden tener propiedades o métodos opcionales.
	
8. En la creación de un método de una interfaz, ¿Qué puedo detallar?  
	- Los tipos de los parámetros de entrada y el tipo de la salida.
	
9. ¿Con qué caracter definimos que una propiedad o método puede ser opcional en la interfaz?  
	- `?`
	
10. ¿El siguiente código es válido en TypeScript?  
	```ts
	interface Carro {
	  llantas: number;
	  modelo: string;
	}
	
	interface Volvo extends Carro {
	  seguro: boolean;
	}
	
	var volvo: Volvo = {
	  llantas: 4,
	  modelo: 'sedan',
	  seguro: true,
	};
	```
	- Verdadero: Es posible heredar interfaces con la palabra "extends"

### 9.11 Código fuente de la sección

Aquí les dejo el código fuente por si lo llegan a necesitar o comparar contra el mío

[GitHub Fin Sección 8](https://github.com/Klerith/ts-bases/tree/fin-seccion-8)

**Nota:**

Por favor, este curso ha tenido actualizaciones desde hace más de 5 años de forma gratuita y están viendo una actualización mayor en la cual regrabé cada clase del curso sin costo para ustedes, les pediría que me ayuden volviendo a calificar el curso y si pueden recomendarlo a otras personas, me serviría bastante porque eso es lo que mantiene vivos los cursos míos

Si quieren saber qué cursos tengo que usan TypeScript, lo pueden ver aquí:

[Cursos que utilizan TypeScript](https://fernando-herrera.com/#/search/typescript)

## 10. NameSpaces

### 10.1 ¿Qué veremos en esta sección?

TypeScript, es un lenguaje de programación web, que nos permite crear objetos que nos servirán a lo largo de nuestro programa. Los namespaces, existen para ayudarnos en la re utilización de nuestras variables, constantes y métodos.

Puntualmente aprenderemos sobre:

1. Explicación del ¿por qué son necesarios los namespaces?
2. Crear namespaces
3. Multiples namespaces en un mismo proyecto
4. Importar namespaces
5. Problemática que se puede presentar utilizando un namespace.

### 10.2 Creando un Namespace

`./src/namespaces/validations.ts`

```ts
namespace Validations {
  export const validateText = (text: string): boolean => {
    return text.length > 3 ? true : false;
  };

  export const validateDate = (myDate: Date): boolean => {
    return isNaN(myDate.valueOf()) ? false : true;
  };
}

console.log(Validations.validateText('Ale'));
// false
```

`./src/index.ts`

```ts
import './namespaces/validations.js';
```

Los **Namespaces** en TypeScript son una forma de **organizar el código en bloques lógicos** para agrupar clases, funciones, interfaces y variables relacionadas, **evitando conflictos de nombres** (contaminación del ámbito global) y creando tipos únicos, especialmente útiles en aplicaciones grandes o al trabajar con bibliotecas externas. Funcionan como **contenedores** para agrupar funcionalidades bajo un nombre común, similar a los módulos, pero se usan más para organización interna o con código más antiguo, ya que los módulos modernos son la forma preferida para la mayoría de los casos.

**Características clave:**

- **Agrupación:** Permiten encapsular elementos relacionados bajo un mismo nombre (ej. `namespace Validation { ... }`).
- **Prevención de Colisiones:** Aseguran que un `class` o `function` llamado `MyClass` dentro de `MyNamespace` no choque con otro `MyClass` en otro lugar.
- **Jerarquía:** Crean una jerarquía lógica, facilitando la lectura y mantenimiento del código.
- **Palabra Clave:** Se definen usando la palabra reservada `namespace` y se accede a sus miembros con el nombre del namespace como prefijo (ej. `MyNamespace.MyClass`).
- **Exportar Elementos:** Se usa `export` para hacer accesibles elementos (clases, interfaces, etc.) fuera del namespace.

**Ejemplo:**

```ts
namespace Geometria {
  export interface Punto {
    x: number;
    y: number;
  }
  export class Circulo {
    constructor(public centro: Punto, public radio: number) {}
    area(): number {
      return Math.PI * this.radio * this.radio;
    }
  }
}

let miPunto: Geometria.Punto = { x: 0, y: 0 };
let miCirculo = new Geometria.Circulo(miPunto, 5);
console.log(miCirculo.area()); // Acceso al método y la clase dentro del namespace
```

Aunque son útiles, en proyectos modernos se prefieren los **módulos de ECMAScript** (archivos separados con `export`/`import`), que son la forma estándar de organizar código en JavaScript/TypeScript, pero los namespaces siguen siendo relevantes para código heredado o ciertas estructuras internas, señala una publicación en Medium.

### 10.3 Inicio de proyecto - Módulos y Webpack

```bash
git clone git@github.com:Klerith/curso-typescript.git
cd curso-typescript
npm i
npm start
```

Opcional:

```bash
// Fix vulnerabilities
npm audit fix --force
```

Estructura:

```bash
.
├── assets
│   ├── css
│   │   └── style.css
│   └── img
│       └── favicon.png
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
├── README.md
├── src
│   ├── classes
│   │   └── Hero.ts
│   └── index.ts
├── tsconfig.json
└── webpack.config.js
```

> Este proyecto usa Webpack, si quieres usar Vite, revisa los apuntes de abajo.

- Ver en GitHub: [TypeScript con frameworks](https://github.com/aleroses/software-notes/blob/master/DW/3-avanzado/6.typescript/TypeScript_Tu-completa-guia-y-manual-de-mano.md#iniciar-un-proyecto-typescript-con-frameworks)
- Ver en Obsidian: [[TypeScript_Tu-completa-guia-y-manual-de-mano#2. Introducción a TypeScript#Iniciar un proyecto TypeScript CON frameworks]]

[Repositorio](https://github.com/Klerith/curso-typescript/tree/codigo-inicial)

### 10.4 Imports y Exports

`src/classes/Hero.ts`

```ts
export class Hero {
  constructor(
    public name: string,
    public powerId: number,
    public age: number
  ) {}
}
```

`src/index.ts`

```ts
import { Hero } from './classes/Hero';

const ironman = new Hero('Ale', 1, 55);

console.log(ironman);
```

### 10.5 Export default y exportación con alias

`src/classes/Hero.ts`

```ts
export class Hero {
  constructor(
    public name: string,
    public powerId: number,
    public age: number
  ) {}
}
```

`src/data/powers.ts`

```ts
export interface Power {
  id: number;
  desc: string;
}

const powers: Power[] = [
  {
    id: 1,
    desc: 'Money',
  },
  {
    id: 2,
    desc: 'Drugs',
  },
  {
    id: 3,
    desc: 'Money',
  },
];

export default powers;
```

`src/index.ts`

```ts
// Option 01
// import { Hero as SuperHero } from './classes/Hero';

// Option 02
import * as HeroClasses from './classes/Hero';

// Option 03
import powers, { Power } from './data/powers';

const ironman = new HeroClasses.Hero('Ale', 1, 55);

console.log(ironman);
console.log(powers);

// { name: "Ale", powerId: 1, age: 55 }
// Array(3) [ {…}, {…}, {…} ]
// 0: Object { id: 1, desc: "Money" }
// 1: Object { id: 2, desc: "Drugs" }
// 2: Object { id: 3, desc: "Money" }
```

### 10.6 Tarea - Resolver errores en TypeScript

`src/classes/Hero.ts`

```ts
import powers from '../data/powers';

export class Hero {
  constructor(
    public name: string,
    public powerId: number,
    public age: number
  ) {}

  // return string
  get power(): string {
    return (
      powers.find((power) => power.id === this.powerId)
        ?.desc || 'not found'
    );
  }
}
```

`src/data/powers.ts`

```ts
export interface Power {
  id: number;
  desc: string;
}

const powers: Power[] = [
  {
    id: 1,
    desc: 'Money',
  },
  {
    id: 2,
    desc: 'Drugs',
  },
  {
    id: 3,
    desc: 'Money',
  },
];

export default powers;
```

`src/index.ts`

```ts
import { Hero } from './classes/Hero';

const ironman = new Hero('Ale', 1, 55);

console.log(ironman);
console.log(ironman.power);

// Object { name: "Ale", powerId: 1, age: 55 }
// Money
```

En TypeScript, el signo de interrogación `?` se usa para declarar propiedades opcionales o para el "Optional Chaining" (acceso seguro a propiedades que pueden ser `null` o `undefined`), mientras que el signo de exclamación `!` (Non-null Assertion Operator) se usa para decirle al compilador que una variable **no** es `null` o `undefined`, forzando el tipo y evitando errores, aunque se debe usar con precaución porque quita la seguridad de tipos. 

El signo de interrogación `?`

- **Propiedades Opcionales:** En la definición de una interfaz o tipo, `propiedad?: tipo;` indica que la propiedad es opcional y puede existir o no.
- **Optional Chaining (`?.`):** Al acceder a una propiedad, `objeto?.propiedad`, si `objeto` es `null` o `undefined`, la expresión devuelve `undefined` en lugar de lanzar un error, permitiendo encadenar accesos de forma segura. 

```ts
interface Usuario {
  nombre: string;
  edad?: number; // edad es opcional
}

const usuario1: Usuario = { nombre: "Ana" }; // OK
const usuario2: Usuario = { nombre: "Luis", edad: 30 }; // OK

// Optional Chaining
const usuario3: Usuario | null = null;
const edadUsuario3 = usuario3?.edad; // edadUsuario3 será undefined, no error
```

El signo de exclamación `!`

- **Operador de Asertencia No Nulo (Non-null Assertion Operator):** `variable!` le dice a TypeScript que confíes en que la `variable` no será `null` o `undefined` en ese punto, eliminando esa comprobación de seguridad.
- **Uso:** Útil cuando sabes algo que el compilador no puede deducir, pero es peligroso si te equivocas (puede causar errores en tiempo de ejecución).

```ts
let nombre: string | null = "Carlos";
console.log(nombre.length); // Error si nombre es null

let nombreSeguro = nombre!; // Asumiendo que sabemos que no es null
console.log(nombreSeguro.length); // OK, TypeScript confía en nosotros
```

En resumen, `?` añade seguridad opcional, mientras que `!` elimina la seguridad de tipos cuando estás seguro de que el valor está presente.

### 10.7 Código fuente de la sección 

Aquí les dejo el código fuente y repositorio de GitHub por si quieren tenerlo a la mano o compararlo contra el mío

[Github - Fin-seccion-10](https://github.com/Klerith/curso-typescript/tree/fin-seccion-10)

**Recursos de la lección:**

- [curso-typescript-fin-seccion-10.zip](https://import.cdn.thinkific.com/643563/courses/1870132/cursotypescriptfinseccion10-220523-140125.zip)

## 11. Genéricos - Generics

### 11.1 ¿Qué veremos en esta sección?

JavaScript por ser un lenguaje dinámico, conlleva a tener varios problemas por esa misma flexibilidad, pero a su vez, permite resolver problemas de una forma muy sencilla. Esta sección esta destinada a comprender como mantener la programación estructurada del TypeScript con el dinamismo de JavaScript.

Puntualmente aprenderemos sobre:

1. Uso de los genéricos
2. Funciones genéricas
3. Ejemplos prácticos sobre los genéricos
4. Arreglos genéricos
5. Clases genéricas

### 11.2 Introducción a los Genéricos

`src/generics/generics.ts`

```ts
export const printObject = (argument: any) => {
  console.log(argument);
};

export function genericFunction(argument: any) {
  return argument;
}
```

`src/index.ts`

```ts
import {
  printObject,
  genericFunction,
} from './generics/generics';

// printObject(123);
// printObject(new Date());
// printObject({ a: 1, b: 2, c: 3 });
// printObject([1, 2, 3]);
// printObject("Hi world");

console.log(genericFunction(3.141).toFixed(2));
// 3.14
```

```bash
npm start
```

### 11.3 Funciones Genéricas

`src/generics/generics.ts`

```ts
export const printObject = (argument: any) => {
  console.log(argument);
};

export function genericFunction<T>(argument: T): T {
  return argument;
}

export const genericFunctionArrow = <T>(argument: T) => {
  return argument;
};
```

`src/index.ts`

```ts
import {
  printObject,
  genericFunction,
  genericFunctionArrow,
} from './generics/generics';

const name: string = 'Ale Ghost';

console.log(genericFunction(3.141).toFixed(2));
console.log(genericFunction(name).toUpperCase());
console.log(genericFunction(new Date()).getDate());

console.log(genericFunctionArrow(new Date()).getDate());
// 3.14
// ALE GHOST
// 25
// 25
```

En TypeScript, los genéricos (`<>`) son una característica que permite crear componentes reutilizables (funciones, clases, interfaces) que pueden trabajar con **cualquier tipo de dato** de forma segura, usando **marcadores de posición (como `T`)** que se sustituyen por tipos reales al usar el componente, lo que ofrece flexibilidad sin perder la seguridad de tipos. Son como **plantillas de tipos** que puedes definir una vez y usar en muchos escenarios, mejorando la reutilización y mantenibilidad del código. 

¿Cómo funcionan?

1. **Marcadores de posición (Parámetros de Tipo)**: Usas un nombre como `T`, `K`, `V` (o el que elijas) dentro de `<>` en la definición.
2. **Uso en el Componente**: Este marcador se usa como si fuera un tipo normal dentro de la función, clase o interfaz.
3. **Inferencia o Especificación de Tipo**: Cuando usas el componente, TypeScript puede inferir el tipo o puedes especificarlo explícitamente (ej: `miFuncion<string>(...)` o `miFuncion(10)` donde TypeScript infiere `number`). 

Ejemplo simple en una función

```ts
function obtenerPrimerElemento<T>(arr: T[]): T {
  return arr[0];
}

const numeros = [1, 2, 3];
const primerNumero = obtenerPrimerElemento<number>(numeros); // T se convierte en 'number'

const palabras = ["hola", "mundo"];
const primeraPalabra = obtenerPrimerElemento<string>(palabras); // T se convierte en 'string'
```

Beneficios clave

- **Reutilización**: Escribes una función que sirve para `number[]`, `string[]`, `boolean[]`, etc..
- **Seguridad de tipos**: TypeScript verifica que los tipos sean consistentes, evitando errores comunes.
- **Código adaptable**: Permite crear estructuras de datos y lógica que se adaptan a diferentes tipos de datos sin necesidad de `any`. 

En resumen, los genéricos son una herramienta poderosa para escribir código flexible, robusto y fácil de mantener en TypeScript, permitiendo que tus componentes sean compatibles con múltiples tipos de forma controlada.

### 11.4 Ejemplo de función genérica en acción

`src/interfaces/villain.ts`

```ts
export interface Villain {
  name: string;
  dangerLevel: number;
}
```

`src/interfaces/hero.ts`

```ts
export interface Hero {
  name: string;
  realName: string;
}
```

`src/generics/generics.ts`

```ts
export const printObject = (argument: any) => {
  console.log(argument);
};

export function genericFunction<T>(argument: T): T {
  return argument;
}

export const genericFunctionArrow = <T>(argument: T) => {
  return argument;
};
```

`src/index.ts`

```ts
import { genericFunctionArrow } from './generics/generics';
import { Hero } from './interfaces/hero';
import { Villain } from './interfaces/villain';

// Este objeto, a pesar de tener una propiedad de mas en cuanto a las
// interfaces Villain y Hero, puede cumplir cualquiera de las dos
const deadpool = {
  name: 'Deadpool',
  realName: 'Wade Winston Wilson',
  dangerLevel: 130,
};

console.log(genericFunctionArrow<Hero>(deadpool).realName);
console.log(
  genericFunctionArrow<Villain>(deadpool).dangerLevel
);

// Error
// console.log(genericFunctionArrow<Hero>(deadpool).dangerLevel);

// Wade Winston Wilson
// 130
```

### 11.5 Agrupar exportaciones

Estructura:

```ts
.
├── assets
│   ├── css
│   │   └── style.css
│   └── img
│       └── favicon.png
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
├── README.md
├── src
│   ├── backs
│   │   └── generics.ts
│   ├── classes
│   │   └── Hero.ts
│   ├── data
│   │   └── powers.ts
│   ├── generics
│   │   └── generics.ts
│   ├── index.ts
│   └── interfaces
│       ├── hero.ts
│       ├── index.ts // 👈🏼👀 Archivo barril
│       └── villain.ts
├── tsconfig.json
└── webpack.config.js
```

`src/interfaces/index.ts`

```ts
// Primero importa los archivos que necesitas y luego cambia el `import` por `export`
export { Hero } from './hero';
export { Villain } from './villain';
```

`src/backs/generics.ts`

```ts
import { genericFunctionArrow } from '../generics/generics';
import { Hero, Villain } from '../interfaces'; 👈🏼👀

// import { Hero } from './interfaces/hero';
// import { Villain } from './interfaces/villain';

const deadpool = {
  name: 'Deadpool',
  realName: 'Wade Winston Wilson',
  dangerLevel: 130,
};

console.log(genericFunctionArrow<Hero>(deadpool).realName);
console.log(
  genericFunctionArrow<Villain>(deadpool).dangerLevel
);
```

Los archivos de barril (barrel files) en JavaScript/TypeScript son un patrón donde un único archivo (generalmente `index.js` o `index.ts`) dentro de un directorio **centraliza y re-exporta múltiples módulos** de ese directorio, creando un punto de acceso simplificado para importar esos elementos desde otras partes del proyecto, limpiando así las importaciones y facilitando la organización. Aunque populares por su conveniencia, su uso excesivo puede tener desventajas en el rendimiento debido a que los _bundlers_ (como Webpack) pueden cargar código innecesario (tree-shaking).

Cómo funcionan

- **Centralización:** En lugar de importar `componenteA`, `componenteB` y `utilidadC` desde archivos separados, creas un `index.js` en la carpeta `src/utils`.
- **Re-exportación:** Dentro de ese `index.js`, usas `export * from './componenteA';`, `export * from './componenteB';`, etc..
- **Importación simplificada:** En otro archivo, solo necesitas `import { componenteA, utilidadC } from './utils';`. 

Ventajas

- **Código más limpio:** Reduce la verbosidad y la longitud de las rutas de importación.
- **Facilita la refactorización:** Si mueves un archivo interno, solo necesitas actualizar el barril, no todos los importadores.
- **Mejor organización:** Agrupa lógicamente módulos relacionados (ej. todos los componentes de una UI). 

Desventajas (y por qué a veces evitarlos)

- **Problemas de rendimiento:** Pueden impedir que el _tree-shaking_ elimine código muerto, obligando a cargar módulos no usados, lo que aumenta el tamaño del _bundle_ final.
- **Ciclos de dependencia:** Pueden introducir dependencias circulares si no se manejan con cuidado, especialmente en TypeScript.
- **Visibilidad:** Las herramientas de análisis pueden tener dificultades para rastrear las dependencias, y no es claro de dónde proviene una exportación. 

Alternativas y buenas prácticas

- **Importar directamente:** Para proyectos pequeños o módulos muy específicos, la importación directa es más eficiente.
- **Usar barriles con moderación:** Son útiles para APIs públicas de bibliotecas o para agrupar componentes de alto nivel, pero no para todo el código interno.
- **Ser explícito:** A veces, es mejor ser explícito con las importaciones para mantener la claridad y el rendimiento.

[Barrel files in JS](https://flaming.codes/es/posts/barrel-files-in-javascript)

### 11.6 Ejemplo aplicado de genéricos

```bash
npm i axios
```

`src/generics/get-pokemon.ts`

```ts
import axios from 'axios';

export const getPokemon = async (pokeID: number) => {
  const response = await axios.get(
    `https://pokeapi.co/api/v2/pokemon/${pokeID}`
  );
  const data = response.data;

  return data;
};
```

`src/index.ts`

```ts
import { getPokemon } from './generics/get-pokemon';

getPokemon(2)
  .then((response) => console.log(response))
  .catch((error) => console.log(error))
  .finally(() => console.log('The end getPokemon!'));
```

`then`, `catch` y `finally` son métodos para manejar los resultados de una Promesa en JavaScript: `then()` maneja la resolución exitosa (cuando la promesa se cumple), `catch()` captura cualquier error o rechazo, y `finally()` ejecuta código de limpieza _siempre_, sin importar si la promesa fue exitosa o falló, siendo útil para ocultar indicadores de carga o cerrar conexiones, sin acceder al resultado final.

Cómo funcionan en conjunto

La estructura básica es `promesa.then(onFulfilled).catch(onRejected).finally(onFinally)`. 

- **`then(onFulfilled)`**:
    - **Cuándo se ejecuta**: Cuando la promesa se resuelve (se cumple exitosamente).
    - **Qué hace**: Recibe el valor con el que se resolvió la promesa (el `resolve(valor)` del código) y ejecuta la función `onFulfilled` con ese valor.
    - **Encadenamiento**: Puede devolver otro valor o una nueva promesa, continuando la cadena.

- **`catch(onRejected)`**:
    - **Cuándo se ejecuta**: Si la promesa es rechazada (el `reject(error)` se llama) o si un `then` anterior lanza un error.
    - **Qué hace**: Ejecuta la función `onRejected`, recibiendo el error como argumento para manejarlo.
    - **Uso**: Es la forma principal de manejar fallos en la cadena de promesas.

- **`finally(onFinally)`:**
	- **Cuándo se ejecuta**: Siempre, una vez que la promesa termina, ya sea resuelta o rechazada.
	- **Qué hace**: Ejecuta la función `onFinally`, pero **no recibe argumentos** (ni el valor de resolución ni el error), ya que no le importa el resultado, solo el fin de la operación.
	- **Uso**: Ideal para liberar recursos (ej. `spinner.hide()`, `closeDatabaseConnection()`). 

Ejemplo práctico

```js
const miPromesa = new Promise((resolve, reject) => {
  // Simulación de una operación asíncrona
  setTimeout(() => {
    // resolve("¡Éxito!"); // Descomenta para ver el flujo de éxito
    reject("¡Error al cargar datos!"); // O un error
  }, 1000);
});

miPromesa
  .then(resultado => {
    console.log("✅ Éxito:", resultado); // Se ejecuta si resolve() es llamado
    return "Resultado procesado"; // Se pasa al siguiente .then o se ignora si no hay más
  })
  .catch(error => {
    console.error("❌ Error:", error); // Se ejecuta si reject() es llamado
    // No devuelve nada, pero la promesa sigue activa
  })
  .finally(() => {
    console.log("⚙️ Finalizado: Siempre se ejecuta (limpieza)"); // Siempre se ejecuta
  });
```

- [PokeApi](https://pokeapi.co/)
- [Axios](https://www.npmjs.com/package/axios)

### 11.7 Mapear respuestas http

`src/interfaces/pokemon.ts`

```ts
export interface Pokemon {
  abilities: Ability[];
  base_experience: number;
  cries: Cries;
  forms: Species[];
  game_indices: GameIndex[];
  height: number;
  held_items: HeldItem[];
  id: number;
  is_default: boolean;
  location_area_encounters: string;
  moves: Move[];
  name: string;
  order: number;
  past_abilities: PastAbility[];
  past_types: any[];
  species: Species;
  sprites: Sprites;
  stats: Stat[];
  types: Type[];
  weight: number;
}

export interface Ability {
  ability: Species | null;
  is_hidden: boolean;
  slot: number;
}

export interface Species {
  name: string;
  url: string;
}

export interface Cries {
  latest: string;
  legacy: string;
}

export interface GameIndex {
  game_index: number;
  version: Species;
}

export interface HeldItem {
  item: Species;
  version_details: VersionDetail[];
}

export interface VersionDetail {
  rarity: number;
  version: Species;
}

export interface Move {
  move: Species;
  version_group_details: VersionGroupDetail[];
}

export interface VersionGroupDetail {
  level_learned_at: number;
  move_learn_method: Species;
  order: null;
  version_group: Species;
}

export interface PastAbility {
  abilities: Ability[];
  generation: Species;
}

export interface GenerationV {
  'black-white': Sprites;
}

export interface GenerationIv {
  'diamond-pearl': Sprites;
  'heartgold-soulsilver': Sprites;
  platinum: Sprites;
}

export interface Versions {
  'generation-i': GenerationI;
  'generation-ii': GenerationIi;
  'generation-iii': GenerationIii;
  'generation-iv': GenerationIv;
  'generation-ix': GenerationIx;
  'generation-v': GenerationV;
  'generation-vi': { [key: string]: Home };
  'generation-vii': GenerationVii;
  'generation-viii': GenerationViii;
}

export interface Other {
  dream_world: DreamWorld;
  home: Home;
  'official-artwork': OfficialArtwork;
  showdown: Sprites;
}

export interface Sprites {
  back_default: string;
  back_female: null;
  back_shiny: string;
  back_shiny_female: null;
  front_default: string;
  front_female: null;
  front_shiny: string;
  front_shiny_female: null;
  other?: Other;
  versions?: Versions;
  animated?: Sprites;
}

export interface GenerationI {
  'red-blue': RedBlue;
  yellow: RedBlue;
}

export interface RedBlue {
  back_default: string;
  back_gray: string;
  back_transparent: string;
  front_default: string;
  front_gray: string;
  front_transparent: string;
}

export interface GenerationIi {
  crystal: Crystal;
  gold: Gold;
  silver: Gold;
}

export interface Crystal {
  back_default: string;
  back_shiny: string;
  back_shiny_transparent: string;
  back_transparent: string;
  front_default: string;
  front_shiny: string;
  front_shiny_transparent: string;
  front_transparent: string;
}

export interface Gold {
  back_default: string;
  back_shiny: string;
  front_default: string;
  front_shiny: string;
  front_transparent?: string;
}

export interface GenerationIii {
  emerald: OfficialArtwork;
  'firered-leafgreen': Gold;
  'ruby-sapphire': Gold;
}

export interface OfficialArtwork {
  front_default: string;
  front_shiny: string;
}

export interface GenerationIx {
  'scarlet-violet': DreamWorld;
}

export interface DreamWorld {
  front_default: string;
  front_female: null;
}

export interface Home {
  front_default: string;
  front_female: null;
  front_shiny: string;
  front_shiny_female: null;
}

export interface GenerationVii {
  icons: DreamWorld;
  'ultra-sun-ultra-moon': Home;
}

export interface GenerationViii {
  'brilliant-diamond-shining-pearl': DreamWorld;
  icons: DreamWorld;
}

export interface Stat {
  base_stat: number;
  effort: number;
  stat: Species;
}

export interface Type {
  slot: number;
  type: Species;
}
```

`src/interfaces/index.ts`

```ts
export { Hero } from './hero';
export { Pokemon } from './pokemon';
export { Villain } from './villain';
```

`src/generics/get-pokemon.ts`

```ts
import axios from 'axios';
import { Pokemon } from '../interfaces';

export const getPokemon = async (
  pokeID: number
): Promise<Pokemon> => {
  const { data } = await axios.get<Pokemon>(
    `https://pokeapi.co/api/v2/pokemon/${pokeID}`
  );

  return data;
};
```

`src/index.ts`

```ts
import { getPokemon } from './generics/get-pokemon';

getPokemon(2)
  .then((pokemon) =>
    console.log(pokemon.sprites.front_default)
  )
  .catch((error) => console.log(error))
  .finally(() => console.log('The end getPokemon!'));
```

Para usar Quicktype entra en `Open QuickType`, dale un nombre como `Pokemon`, pega la data JSON y elige el lenguaje **TypeScript**:

- Verify JSON.parse results at runtime
- **Interfaces Only**

Enlaces:

- [Quicktype](https://quicktype.io/)
- [Pokeapi](https://pokeapi.co/)

### 11.8 Quicktype.io extensión

`src/interfaces/pokemon.ts`

```ts
export interface Pokemon {
  abilities: Ability[];
  base_experience: number;
  cries: Cries;
  forms: Species[];
  game_indices: GameIndex[];
  height: number;
  held_items: HeldItem[];
  id: number;
  is_default: boolean;
  location_area_encounters: string;
  moves: Move[];
  name: string;
  order: number;
  past_abilities: PastAbility[];
  past_types: any[];
  species: Species;
  sprites: Sprites;
  stats: Stat[];
  types: Type[];
  weight: number;
}

export interface Ability {
  ability: Species | null;
  is_hidden: boolean;
  slot: number;
}

export interface Species {
  name: string;
  url: string;
}

export interface Cries {
  latest: string;
  legacy: string;
}

export interface GameIndex {
  game_index: number;
  version: Species;
}

export interface HeldItem {
  item: Species;
  version_details: VersionDetail[];
}

export interface VersionDetail {
  rarity: number;
  version: Species;
}

export interface Move {
  move: Species;
  version_group_details: VersionGroupDetail[];
}

export interface VersionGroupDetail {
  level_learned_at: number;
  move_learn_method: Species;
  order: null;
  version_group: Species;
}

export interface PastAbility {
  abilities: Ability[];
  generation: Species;
}

export interface GenerationV {
  'black-white': Sprites;
}

export interface GenerationIv {
  'diamond-pearl': Sprites;
  'heartgold-soulsilver': Sprites;
  platinum: Sprites;
}

export interface Versions {
  'generation-i': GenerationI;
  'generation-ii': GenerationIi;
  'generation-iii': GenerationIii;
  'generation-iv': GenerationIv;
  'generation-ix': GenerationIx;
  'generation-v': GenerationV;
  'generation-vi': { [key: string]: Home };
  'generation-vii': GenerationVii;
  'generation-viii': GenerationViii;
}

export interface Other {
  dream_world: DreamWorld;
  home: Home;
  'official-artwork': OfficialArtwork;
  showdown: Sprites;
}

export interface Sprites {
  back_default: string;
  back_female: null;
  back_shiny: string;
  back_shiny_female: null;
  front_default: string;
  front_female: null;
  front_shiny: string;
  front_shiny_female: null;
  other?: Other;
  versions?: Versions;
  animated?: Sprites;
}

export interface GenerationI {
  'red-blue': RedBlue;
  yellow: RedBlue;
}

export interface RedBlue {
  back_default: string;
  back_gray: string;
  back_transparent: string;
  front_default: string;
  front_gray: string;
  front_transparent: string;
}

export interface GenerationIi {
  crystal: Crystal;
  gold: Gold;
  silver: Gold;
}

export interface Crystal {
  back_default: string;
  back_shiny: string;
  back_shiny_transparent: string;
  back_transparent: string;
  front_default: string;
  front_shiny: string;
  front_shiny_transparent: string;
  front_transparent: string;
}

export interface Gold {
  back_default: string;
  back_shiny: string;
  front_default: string;
  front_shiny: string;
  front_transparent?: string;
}

export interface GenerationIii {
  emerald: OfficialArtwork;
  'firered-leafgreen': Gold;
  'ruby-sapphire': Gold;
}

export interface OfficialArtwork {
  front_default: string;
  front_shiny: string;
}

export interface GenerationIx {
  'scarlet-violet': DreamWorld;
}

export interface DreamWorld {
  front_default: string;
  front_female: null;
}

export interface Home {
  front_default: string;
  front_female: null;
  front_shiny: string;
  front_shiny_female: null;
}

export interface GenerationVii {
  icons: DreamWorld;
  'ultra-sun-ultra-moon': Home;
}

export interface GenerationViii {
  'brilliant-diamond-shining-pearl': DreamWorld;
  icons: DreamWorld;
}

export interface Stat {
  base_stat: number;
  effort: number;
  stat: Species;
}

export interface Type {
  slot: number;
  type: Species;
}
```

Para usar la extensión **Paste JSON as Code** dentro de VSC, primero instálala, copia la data JSON, entra a VSC, presiona `F1`, busca **Paste JSON as Code**, presiona `Enter` y escribe el Top level type name, en este caso `Pokemon`, por último vuelve a presionar `Enter`.

Extensión:

- Paste JSON as Code

### 11.9 Código fuente de la sección

Aquí les dejo el código fuente de la sección por si la llegan a necesitar o comparar contra el suyo.

[Github - Fin-seccion-11](https://github.com/Klerith/curso-typescript/tree/fin-seccion-11)

Recursos de la lección:

- [curso-typescript-fin-seccion-11.zip](https://import.cdn.thinkific.com/643563/courses/1870132/cursotypescriptfinseccion11-220523-185258.zip)

## 12. Decoradores

### 12.1 ¿Qué veremos en esta sección?

Los decoradores son una característica nueva en el TypeScript que cada vez es más utilizada por otros frameworks como Angular 2. Pero vamos a aprender a utilizar decoradores en nuestros proyectos.

Puntualmente aprenderemos sobre:

1. ¿Qué son los decoradores?
2. ¿Para qué sirven?
3. Decoradores de clases
4. Decoradores de fabrica
5. Ejemplos prácticos
6. Decoradores anidados
7. Decoradores de métodos
8. Decoradores de propiedades
9. Decoradores de parámetros

### 12.2 Introducción a los decoradores

Un decorador en TypeScript es una **función especial** que se antepone con `@` a una declaración (clase, método, propiedad, parámetro) para **anotar o modificar su comportamiento** en tiempo de diseño o ejecución, permitiendo metaprogramación y reutilización de código, como añadir logging, inyección de dependencias o metadata, muy usado en frameworks como Angular y NestJS.

¿Cómo funcionan?

- **Función de orden superior**: Son funciones que reciben información sobre la declaración que están decorando y pueden devolver una nueva función o modificar el descriptor de la propiedad.
- **Sintaxis `@expresión`**: La `@expresión` debe resolverse en una función que se ejecutará en tiempo de ejecución con la información de la declaración. 

Tipos de decoradores

- **Decorador de clase**: Se aplica al constructor de la clase, pudiendo observar, modificar o reemplazar la definición de la clase.
- **Decorador de método**: Se aplica a un método y puede modificar su lógica, por ejemplo, añadiendo logging antes o después de la ejecución.
- **Decorador de propiedad**: Se aplica a una propiedad, útil para adjuntar metadatos o lógica de inicialización.
- **Decorador de parámetro**: Se aplica a los parámetros de un método o constructor, recibiendo el índice del parámetro.
- **Decorador de accesor (getter/setter)**: Modifica los descriptores de los accesor de propiedades. 

Ejemplo (Decorador de método para loguear)

```ts
function log(target: Object, propertyKey: string, descriptor: any) {
  console.log(`Método "${propertyKey}" llamado en clase`, target.constructor.name);
  return descriptor;
}

class MiClase {
  @log
  saludar(nombre: string) {
    console.log(`Hola, ${nombre}`);
  }
}

const instancia = new MiClase();
instancia.saludar("Mundo");
```

_Salida:_

```
Método "saludar" llamado en clase MiClase
Hola, Mundo
```

Uso en frameworks

Se usan intensivamente en Angular para definir componentes (`@Component`), servicios (`@Injectable`), pipes, etc., y en NestJS para definir controladores, servicios y más, facilitando la programación orientada a aspectos. Para usarlos, a menudo necesitas habilitar la opción `experimentalDecorators` en tu `tsconfig.json`.

[Decoradores de TypeScript](https://www.typescriptlang.org/docs/handbook/decorators.html)

### 12.3 Decoradores de clases

`src/decorators/pokemon-class.ts`

```ts
function printToConsole(constructor: Function) {
  console.log(constructor);
}

@printToConsole 👈🏼👀👇🏼
export class Pokemon {
  public publicApi: string = 'https://pokeapi.co/api/v2/';
  constructor(public name: string) {}
}

// Este decorador se ejecuta al definir la clase
```

`src/index.ts`

```ts
import { Pokemon } from './decorators/pokemon-class';

const charmander = new Pokemon('Charmander');

console.log(charmander);
```

Muestra en consola:

```
class Pokemon { constructor(name) }
  length: 1
  name: "Pokemon"
  prototype: Object { ... }
  
Object {
  name: "Charmander"
  publicApi: "https://pokeapi.co/api/v2/"
}
```

📌 Nota: Dentro del `tsconfig.json` descomenta `"experimentalDecorators": true`. En caso de que el error no se borre, baja la aplicación y nuevamente ejecuta `npm start`.

¿Qué es un decorador en TypeScript?

Un **decorador** es una función especial que se usa para **añadir comportamiento o metadatos** a una clase, método, propiedad o parámetro **sin modificar directamente su código**.

👉 Los **decoradores de clase** se aplican **a la clase completa**.

**Un decorador de clase es una función que recibe el constructor de la clase y puede observarlo, modificarlo o reemplazarlo.**

> Piensa en ellos como una “capa extra” que envuelve a la clase.

Requisito importante

Para usar decoradores, debes activar esto en tu `tsconfig.json`:

```json
{
  "compilerOptions": {
    "experimentalDecorators": true
  }
}
```

Sintaxis básica de un decorador de clase

Un decorador de clase es una función que recibe **el constructor de la clase**.

```ts
function MyDecorator(constructor: Function) {
  console.log('Decorador ejecutado');
}
```

Se usa así:

```ts
@MyDecorator
class User {
  constructor(public name: string) {}
}
```

📌 **Importante**:  
El decorador se ejecuta **cuando la clase es definida**, no cuando se crea una instancia.

Recibe el **constructor de la clase**, lo que permite:

- Leer información de la clase
- Modificar el constructor
- Añadir propiedades o métodos
- Reemplazar la clase por otra

Ejemplo:

```ts
function LogClass(constructor: Function) {
  console.log(constructor);
}
```

Esto imprime la definición de la clase en consola.

#### Decorador que agrega una propiedad a la clase

```ts
function AddVersion(version: string) {
  return function (constructor: Function) {
    constructor.prototype.version = version;
  };
}

@AddVersion('1.0.0')
class App {}

const app = new App();
console.log((app as any).version); // 1.0.0
```

👉 Aquí el decorador:

- Recibe un parámetro (`version`)
- Devuelve la función decoradora real
- Modifica el `prototype` de la clase

#### Decorador que reemplaza la clase

Un decorador puede **devolver una nueva clase**, reemplazando la original.

```ts
function Logger<T extends { new (...args: any[]): {} }>(constructor: T) {
  return class extends constructor {
    createdAt = new Date();
  };
}

@Logger
class User {
  name = 'Henry';
}

const user = new User();
console.log(user.createdAt);
```

📌 Aquí:

- El decorador crea una **subclase**
- Añade la propiedad `createdAt`
- La clase original queda “envuelta”

Este patrón se usa mucho en **frameworks**.

#### Decoradores con frameworks (ejemplo mental)

Esto te va a sonar conocido si usas Angular o NestJS:

```ts
@Controller('users')
class UserController {}
```

Internamente:

- `@Controller` es un decorador de clase
- Registra metadatos
- El framework luego lee esos metadatos

Orden de ejecución

Si tienes varios decoradores:

```ts
@A
@B
class Test {}
```

Se ejecutan así:

1. `B`
2. `A`

👉 De abajo hacia arriba.

✔ Casos comunes para usar decoradores de clase:

- Registrar clases
- Inyección de dependencias
- Añadir metadatos
- Logging
- Validaciones
- Extender comportamiento sin herencia directa

❌ No usar para:

- Lógica de negocio
- Código crítico difícil de depurar

### 12.4 Decoradores de fábrica - Factory decorators

`src/decorators/pokemon-class.ts`

```ts
function printToConsole(constructor: Function) {
  console.log(constructor);
}

const printToConsoleConditional = (
  print: boolean = false
): Function => {
  if (print) {
    return printToConsole;
  }

  return () => {};
};

@printToConsoleConditional(true)
export class Pokemon {
  public publicApi: string = 'https://pokeapi.co/api/v2/';
  constructor(public name: string) {}
}

// Este decorador se ejecuta al definir la clase
```

`src/index.ts`

```ts
import { Pokemon } from './decorators/pokemon-class';

const charmander = new Pokemon('Charmander');

console.log(charmander);
```

En consola:

```
class Pokemon { constructor(name) }
  length: 1
  name: "Pokemon"
  prototype: Object { ... }
  
Object {
  name: "Charmander"
  publicApi: "https://pokeapi.co/api/v2/"
}
```

Los Decoradores de Fábrica en TypeScript son funciones especiales que **devuelven otra función decoradora**, permitiendo crear decoradores parametrizados y reutilizables, como `@factory(param1, param2)`.

### 12.5 Ejemplo de un decorador - Bloquear prototipo

`src/decorators/pokemon-class.ts`

```ts
function printToConsole(constructor: Function) {
  console.log(constructor);
}

const printToConsoleConditional = (
  print: boolean = false
): Function => {
  if (print) {
    return printToConsole;
  }

  return () => {};
};

const bloquearPrototipo = function (constructor: Function) {
  // seal impide añadir o eliminar propiedades
  // No puedes agregar propiedades estáticas a la clase
  Object.seal(constructor);
  // No puedes agregar métodos o propiedades al prototype
  Object.seal(constructor.prototype);
};

@bloquearPrototipo
@printToConsoleConditional(true)
export class Pokemon {
  public publicApi: string = 'https://pokeapi.co/api/v2/';
  constructor(public name: string) {}
}

// Este decorador se ejecuta al definir la clase
```

`src/index.ts`

```ts
import { Pokemon } from './decorators/pokemon-class';

const charmander = new Pokemon('Charmander');

// Error: can't define property "customName": Object is not extensible
(Pokemon.prototype as any).customName = 'Pikachu';

console.log(charmander);
```

En consola:

```
class Pokemon { constructor(name) }
  length: 1
  name: "Pokemon"
  prototype: Object { ... }
  
Uncaught TypeError: can't define Uncaught TypeError: can't define property "customName": Object is not extensible
```

`Object.seal()` en JavaScript sella un objeto, impidiendo la adición o eliminación de nuevas propiedades y marcando las existentes como no configurables, pero **sí permite modificar los valores de las propiedades actuales**. Esto hace que la estructura de propiedades del objeto sea fija, aunque su contenido (los valores) puede seguir cambiando, a diferencia de `Object.freeze()`, que las bloquea por completo. 

Características clave:

- **No se pueden añadir nuevas propiedades**: Si intentas agregar `objeto.nuevaPropiedad = valor;`, fallará silenciosamente o lanzará un error en modo estricto.
- **No se pueden eliminar propiedades**: `delete objeto.propiedad;` no tendrá efecto o lanzará un error.
- **Propiedades existentes son no configurables**: No puedes cambiar descriptores de propiedad (como hacer una propiedad solo de lectura o de escritura), pero sí cambiar sus valores si eran escribibles.
- **Los valores se pueden modificar**: `objeto.propiedadExistente = nuevoValor;` funciona. 

Ejemplo:

```js
const persona = { nombre: 'Ana', edad: 25 };
Object.seal(persona);

// Intentar añadir propiedad
persona.ciudad = 'Madrid'; // No se añade, no hay error (o error en modo estricto)

// Intentar eliminar propiedad
delete persona.edad; // No se elimina, no hay error (o error en modo estricto)

// Modificar valor (¡esto sí funciona!)
persona.nombre = 'Ana María'; // ¡Funciona!

console.log(persona); // { nombre: 'Ana María', edad: 25 }
```

Cuándo usarlo:

- Cuando necesitas asegurar que un objeto mantenga un conjunto fijo de propiedades (ni más ni menos) pero sus valores puedan ser actualizados.
- Para preservar la estructura de un objeto mientras permites flexibilidad en sus datos.

### 12.6 Decoradores de métodos

`src/decorators/pokemon-class.ts`

```ts
function printToConsole(constructor: Function) {
  console.log(constructor);
}

const printToConsoleConditional = (
  print: boolean = false
): Function => {
  if (print) {
    return printToConsole;
  }

  return () => {};
};

const bloquearPrototipo = function (constructor: Function) {
  Object.seal(constructor);
  Object.seal(constructor.prototype);
};

function CheckValidPokemonId() {
  return function (
    target: any, // parent class constructor and method
    propertyKey: string, // method name: savePokemonToDB
    // configurable enumerable writable value
    descriptor: PropertyDescriptor
  ) {
    const originalMethod = descriptor.value;

    // descriptor.value = () => console.log('Hi World!!!');
    // Se dispara con los argumentos de savePokemonToDB
    descriptor.value = (id: number) => {
      if (id < 1 || id > 800) {
        return console.error(
          'The Pokemon Id must be between 1 and 800. '
        );
      }

      return originalMethod(id);
    };
    console.log({ target, propertyKey, descriptor });
  };
}

@bloquearPrototipo
@printToConsoleConditional(false)
export class Pokemon {
  public publicApi: string = 'https://pokeapi.co/api/v2/';
  constructor(public name: string) {}

  @CheckValidPokemonId()
  savePokemonToDB(id: number) {
    console.log(`Pokemon saved in the database ${id}`);
  }
}

// Este decorador se ejecuta al definir la clase

/* 
Decoradores en Ts

Son funciones especiales, que sirven para anotar,  amplicar o modificar el comportamiento de:

- métodos
- clases
- Propiedades
- Parametros


en tiempo de diseño o ejecución.
*/
```

`src/index.ts`

```ts
import { Pokemon } from './decorators/pokemon-class';

const charmander = new Pokemon('Charmander');

// Error:
// (Pokemon.prototype as any).customName = 'Pikachu';

// console.log(charmander.savePokemonToDB(50));
charmander.savePokemonToDB(50);
```

Los decoradores de métodos en TypeScript son funciones especiales (precedidas por `@`) que se aplican a los métodos de una clase para **modificar, observar o reemplazar su comportamiento** en tiempo de diseño, interceptando la definición del método y permitiendo metaprogramación como logging, validación o binding. Se definen como funciones que reciben el prototipo de la clase (`target`), el nombre del método (`propertyName`), y un `PropertyDescriptor`, permitiendo manipular la función original dentro de este descriptor para añadir lógica antes o después de la ejecución. 

¿Qué son y para qué sirven?

- **Funciones de orden superior**: Son funciones que se aplican a miembros de clases (métodos, propiedades, etc.).
- **Metaprogramación**: Permiten escribir código que manipula otro código, añadiendo funcionalidades de forma declarativa sin alterar el código fuente original.
- **Casos de uso**:
    - **Logging**: Registrar cuándo se llama a un método y con qué argumentos.
    - **Validación**: Añadir comprobaciones antes de ejecutar el método.
    - **Binding**: Vincular automáticamente `this` a la instancia.
    - **Reemplazo**: Sustituir el método por una nueva implementación. 

Estructura de un decorador de método

```ts
function miDecorador(target: any, propertyName: string, descriptor: PropertyDescriptor) {
    // target: El prototipo de la clase (o la función constructora para estáticos) [5].
    // propertyName: El nombre del método [5].
    // descriptor: Contiene el 'value' (la función original) y otras propiedades [5, 12].

    const metodoOriginal = descriptor.value; // Guardamos la función original.

    // Reemplazamos el 'value' con una nueva función que envuelve a la original.
    descriptor.value = function(...args: any[]) {
        console.log(`Llamando al método: ${propertyName}`);
        // Llamamos al método original con su contexto (this) y argumentos.
        return metodoOriginal.apply(this, args);
    };
}
```

Ejemplo de uso

```ts
class MiClase {
    @miDecorador // Aplicamos el decorador al método.
    saludar(nombre: string) {
        console.log(`Hola, ${nombre}`);
    }
}

const instancia = new MiClase();
instancia.saludar("Mundo");
// Salida:
// Llamando al método: saludar
// Hola, Mundo [12]
```

Consideraciones

- **Configuración**: Debes habilitar los decoradores en tu `tsconfig.json` (ej: `"experimentalDecorators": true`) para usarlos.
- **Tipos**: Existen decoradores para clases, métodos, propiedades y parámetros, cada uno con sus propios argumentos.

### 12.7 Decoradores de propiedades

`src/decorators/pokemon-class.ts`

```ts
function printToConsole(constructor: Function) {
  console.log(constructor);
}

const printToConsoleConditional = (
  print: boolean = false
): Function => {
  if (print) {
    return printToConsole;
  }

  return () => {};
};

const bloquearPrototipo = function (constructor: Function) {
  Object.seal(constructor);
  Object.seal(constructor.prototype);
};

function CheckValidPokemonId() {
  return function (
    target: any, // parent class constructor and method
    propertyKey: string, // method name: savePokemonToDB
    // configurable enumerable writable value
    descriptor: PropertyDescriptor
  ) {
    const originalMethod = descriptor.value;

    // descriptor.value = () => console.log('Hi World!!!');
    // Se dispara con los argumentos de savePokemonToDB
    descriptor.value = (id: number) => {
      if (id < 1 || id > 800) {
        return console.error(
          'The Pokemon Id must be between 1 and 800. '
        );
      }

      return originalMethod(id);
    };
    console.log({ target, propertyKey, descriptor });
  };
}

function readonly(isWritable: boolean = true): Function {
  // el "descriptor" solo aplica al decorar métodos, no propiedades
  return function (
    target: any,
    propertyKey: string
    // descriptor: PropertyDecorator (devuelve undefined)
  ) {
    const descriptor: PropertyDescriptor = {
      get() {
        console.log(this, 'getter');

        return 'Ale';
      },
      set(this, value) {
        // console.log(this, value);
        Object.defineProperty(this, propertyKey, {
          value: value,
          writable: !isWritable,
          enumerable: false,
        });
      },
    };

    return descriptor;
  };
}

@bloquearPrototipo
@printToConsoleConditional(false)
export class Pokemon {
  @readonly(true)
  public publicApi: string = 'https://pokeapi.co/api/v2/';
  constructor(public name: string) {}

  @CheckValidPokemonId()
  savePokemonToDB(id: number) {
    console.log(`Pokemon saved in the database ${id}`);
  }
}

// Este decorador se ejecuta al definir la clase

/* 
Decoradores en Ts

Son funciones especiales, que sirven para anotar, amplicar o modificar el comportamiento de:

- Métodos
- Clases
- Propiedades
- Parametros

En tiempo de diseño o ejecución.
*/
```

`src/index.ts`

```ts
import { Pokemon } from './decorators/pokemon-class';

const charmander = new Pokemon('Charmander');

// Error:
// (Pokemon.prototype as any).customName = 'Pikachu';

// console.log(charmander.savePokemonToDB(50));
// charmander.savePokemonToDB(50);

charmander.publicApi = 'https://aleroses.com';
console.log(charmander);
```

### 12.8 Código fuente de la sección

Aquí les dejo el código fuente de la sección por si lo llegan a necesitar en algún momento o bien para compararlo contra el mío

[Github - fin-seccion-12](https://github.com/Klerith/curso-typescript/tree/fin-seccion-12)

También lo pueden descargar del material adjunto.

Recursos de la Lección:

- [curso-typescript-fin-seccion-12.zip](https://import.cdn.thinkific.com/643563/courses/1870132/cursotypescriptfinseccion12-220523-190700.zip)

## 13. Usando librerías que no están escritas en TypeScript ( Como jQuery )

### 13.1 ¿Qué veremos en esta sección?

Sabemos muy bien que nuestras aplicaciones web, no serán programadas únicamente con TypeScript puro, por lo cual es importante aprender como utilizar librerías de terceros en nuestros proyectos de TypeScript.

Puntualmente aprenderemos sobre:

1. Configuración de un proyecto utilizando el package.json y realizar instalaciones con node.
    
2. Utilizar archivos de definiciones "*.d.ts" o Typings
    
3. Agregar definiciones de archivos mediante node

### 13.2 Inicio de proyecto - Express API

```bash
mkdir express-api
cd express-api
npm init

# Termina con enter
npm i
```

`package.json`

```json
{
  "name": "express-api",
  "version": "1.0.0",
  "description": "",
  "license": "ISC",
  "author": "",
  "type": "commonjs",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "",
    "start": ""
  }
}
```

`index.js`

```js
console.log('Hi World!!!');
```

```bash
node index
Hi World!!!
```

### 13.3 Creando un Rest API con Express

Entra en Expressjs y ve a `Getting started/Installing`

```bash
npm install express
npm install -g typescript
```

[Next: Express "Hello World" example](https://expressjs.com/en/starter/hello-world.html)

`index.js`

```ts
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
  // Display message
  // res.send('Hello World!');

  // Display object
  res.json({
    ok: true,
    msg: 'So far, so good!',
  });
});

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`);
});
```

Para ver cada cambio usa `Ctrl + C` y nuevamente `node index.js`.

```bash
node index.js
Example app listening on port 3000

# Ctrl + C
# http://localhost:3000/
```

DevTools: Network/Headers/304 GET localhost.../Content-Type

Cambia `index.js` por `index.ts`

```bash
tsc index.ts
# Error + Create index.js file
```

[Expressjs](https://expressjs.com/)

### 13.4 Trabajar con TypeScript en lugar de JavaScript

Borra el archivo `index.js` y crea la carpeta `dist`

```bash
tsc --init
# tsconfig.json
```

En el archivo `tsconfig.json` descomenta `"outDir": "./dist",`.

Si te sale este error:

```
ECMAScript imports and exports cannot be written in a CommonJS file under 'verbatimModuleSyntax'. Adjust the 'type' field in the nearest 'package.json' to make this file an ECMAScript module, or adjust your 'verbatimModuleSyntax', 'module', and 'moduleResolution' settings in TypeScript.
```

Abre el archivo `package.json` y cambia `"type": "commonjs",` por `"type": "module",`.

`index.ts`

```ts
import express from 'express';

const app = express();
const port = 3000;

app.get('/', (req, res) => {
  // Display message
  // res.send('Hello World!');

  res.status(401).json({
    ok: false,
    msg: "There isn't any token in the request",
  });

  // Display object
  // res.json({
  //   ok: true,
  //   msg: 'So far, so good!',
  // });
});

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`);
});
```

Ejecuta `tsc` en la terminal, verás el archivo `index.js` dentro de `dist`.

Ejecuta `node dist/index.js` para revisar la web.

```bash
# http://localhost:3000/
```

Verás un objeto json.

Para refrescar los cambios constantemente usa:

```bash
tsc -w

node dist/index
```

📌 Nota: Recuerda usar `Ctrl + .` sobre los errores para obtener ayuda, incluso puedes intalar cosas necesarias.

## 14. Final del curso

### 14.1 Más información sobre nuestros otros cursos

Idealmente, para que puedas seguir aprendiendo, te invitamos a que revises nuestro plan de estudio para guiarte y así continuar desarrollándote en estas tecnologías.

[DevTalles - Programas de estudio](https://cursos.devtalles.com/pages/programas-fundamentos)

- 🔗 Mi Web personal: [Sitio web con cupones y descuentos](https://fernando-herrera.com/)
- 🎙️ Mi Podcast: [PodCast](https://anchor.fm/fernando-her85)
- 👥 Mi Twitter: [@fernando_her85](https://twitter.com/Fernando_Her85)
- 👨🏻‍🏫 Perfil de instructor | Udemy: [Perfil de Udemy](https://www.udemy.com/user/550c38655ec11/)
- 👨🏻‍💻 {d/t} DevTalles: [Cursos](https://cursos.devtalles.com/)
- 👨🏻‍🎓 {d/t} DevTalles LinkedIn: [Linkedin](https://www.linkedin.com/company/devtalles/)
- 📱 {d/t} DevTalles Twitter: [Twitter oficial de DevTalles](https://twitter.com/DevTalles)
- 🚀 {d/t} DevTalles Comunidad Discord: [Discord](https://discord.com/invite/fNp7KRDkke)

### 14.2 Despedida del curso

Nice!


👈🏼👀
👈🏼👀👇🏼
🔥
📌
☢️