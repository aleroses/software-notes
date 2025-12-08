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
    return `${firstname} ${restArgs.join(' ')}`;
  };

  const superman = fullName('Clark', 'Joseph', 'Kent');

  console.log({ superman });
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
2. ¿La siguiente función válida en TypeScript?
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

```

`./bases/index.html`

```html
```

### 5.6

`./bases/objetos/objects.ts`

```ts

```

`./bases/index.html`

```html
```

### 5.7

`./bases/objetos/objects.ts`

```ts

```

`./bases/index.html`

```html
```

### 5.8

`./bases/objetos/objects.ts`

```ts

```

`./bases/index.html`

```html
```

### 5.9

`./bases/objetos/objects.ts`

```ts

```

`./bases/index.html`

```html
```

### 5.10

`./bases/objetos/objects.ts`

```ts

```

`./bases/index.html`

```html
```

### 5.11
### 5.12










`./bases/objetos/objects.ts`

```ts

```

`./bases/index.html`

```html
```



















`./bases/funciones/functions.ts`

```ts

```

`./bases/index.html`

```html
```

### 4.10

`./bases/funciones/functions.ts`

```ts

```

`./bases/index.html`

```html
```


```
```

```
```

```
```

👈🏼👀

👈🏼👀
🔥
📌
☢️