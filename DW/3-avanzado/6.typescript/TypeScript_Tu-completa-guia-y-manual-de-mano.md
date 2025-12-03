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
// Object.defineProperty(exports, '__esModule', { value: true });
const msg = 'Hi world';
console.log(msg);
//# sourceMappingURL=app.js.map
```

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

## 3. 

### 3.1

```
```

```
```

```
```

```
```

```
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