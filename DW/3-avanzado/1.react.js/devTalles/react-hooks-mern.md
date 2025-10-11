# React (Hooks y MERN)

## 🟣 1. Introducción

### 1.1 Introducción al curso

Se recomienda hacer las tareas de cada sección.

### 1.2 ¿Cómo funcionará el curso?

Trata de ver el curso en secuencia.

### 1.3 ¿Cómo hacer preguntas?

Revisa la sección de **Discusión** y crea un **Post**.

> Trata de agregar toda la información de una sola vez y de ser necesario deja tu código en un repositorio alojado en GitHub para que pueda ser revisado por los instructores y así puedan darte mucho mejor soporte.

### 1.4 Instalaciones necesarias y recomendadas

#### Instalaciones Necesarias

* [Google Chrome](https://www.google.com/chrome/)

* [React Developer Tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=es&authuser=1)

* [Redux Devtools](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=es)

* [Visual Studio Code](https://code.visualstudio.com/)

* [Postman](https://www.postman.com/downloads/)

* [Mongo Compass](https://www.mongodb.com/try/download/compass)

* [Git](https://git-scm.com/)

* [Node](https://nodejs.org/es/)

> Revisa la configuración básica de Git: [Apuntes](https://github.com/aleroses/Platzi/blob/master/DW/1-basico/005-git-github/git-github.md#8-crea-un-repositorio-de-git-y-haz-tu-primer-commit)

```bash
git config --list
  - Configuración por defecto de git
  - Vemos que aún no está nuestro nombre ni correo

git config --global user.name "John Lennon"
  - Cambiar usuarios globales

git config --global user.email "john.l@mail.com"
  - Cambiar email
```

#### Extensiones de VSCode

[Activitus Bar](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.activitusbar)

#### Configuración del Bracket Pair Colorizer 2

Brakcet Pair está obsoleto.
[Obsoleto - Bracket Pair Colorizer 2](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2)

Solución:

- Presiona F1 para abrir búsqueda en VS Code.
- Busca Open Settings (UI)
- En Search settings copia y pega esto: 

```
"@id:editor.bracketPairColorization.enabled [@id:editor.guides.bracketPairs](https://id:editor.guides.bracketPairs/)"
```

También puedes usar el atajo `Ctrl + ,` y pegas en el buscador lo mostrado arriba.
  
Ahora asegúrate de que: 

> Editor > Bracket Pair Colorization: Enabled está marcado con un tick mark (activo)

---

> Editor > Guides. Bracket Pairs tiene la opción de "active" seleccionada.

A continuación haz de nuevo F1 y busca Open User Settings (JSON) o usa el atajo `Ctrl + ,` y busca el icono 📄 Open Settings (JSON)

Ahora en el fichero **settings.json** añade la siguiente propiedad al objeto json:

```json
"workbench.colorCustomizations": {
	"editorBracketHighlight.foreground1": "#fafafa",
	"editorBracketHighlight.foreground2": "#9F51B6",
	"editorBracketHighlight.foreground3": "#F7C244",
	"editorBracketHighlight.foreground4": "#F07850",
	"editorBracketHighlight.foreground5": "#97c26c",
	"editorBracketHighlight.foreground6": "#C497D4",
	"editorBracketHighlight.unexpectedBracket.foreground": "#fb6165"
},
```

#### Temas que estoy usando en VSCode:

* [Monokai Night](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-monokai-night)

* [Tokyo Night](https://marketplace.visualstudio.com/items?itemName=enkia.tokyo-night)

* [Iconos](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)

Mi tema: [Material Theme -- Free](https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-material-theme)

#### Instalaciones recomendadas sobre React

* [ES7 React/Redux](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)

* [Simple React Snippets](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets)

* [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)

[Instalaciones recomendadas](https://gist.github.com/Klerith/4a4abfd88a88b2d1f16efd95fea41362)

### 1.5 ¡Únete a Nuestra Comunidad de DevTalles en Discord!

**¿Cómo unirse?**

- Haz clic en el siguiente enlace de invitación: [Comunidad DevTalles](https://discord.gg/pBjEVYTC7t)

## 🟣 2. Introducción a React y conceptos generales

### 2.1 Introducción a la sección

### 2.2 Temas puntuales de la sección

**¿Qué aprenderemos en esta sección?**

- ¿Qué es React?
- Conceptos generales
- Babel
- JSX

Daremos nuestros primeros pasos y una pequeña aplicación que nos ayudará a perderle el miedo a React rápidamente

### 2.3 ¿Qué es React?

- Librería: Para aplicaciones sencillas, intermedias y robustas.
- Declarativa: Es fácil de seguir patrones de diseño y crear UI interactivas.
- Eficiente: Los cambios se hacen solo en el elemento que se modificó.
- Predecible:
- Componentes: Pequeñas piezas encapsuladas fáciles de mantener.
- Server-side con Node
- Aplicaciones móviles con React Native.

¿Cómo luce el código de React?

```html
<div id="root"></div>
```

```jsx
const root = document.querySelector("#root");
ReactDOM.render(<h1>Hola mundo cruel</h1>, root);
```

También:

```html
<div id="root"></div>
```

```jsx
const root = document.querySelector("#root");
const tag = <h1>Hola mundo cruel</h1> // JSX
ReactDOM.render(tag, root);
```

El código JSX se podría crear de la siguiente manera:

```jsx
const tag = document.createElement('h1', null, `Hola, soy ${nombre}`)
```

### 2.4 Primeros pasos en React

Creamos una carpeta para empezar a trabajar:

```bash
.
├── 01-intro-react 👈👀
│   └── index.html
├── 02-intro-js
└── 03-counter-app
```

Abrimos el primer archivo usando Visual Studio Code y añadimos lo siguiente:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />

    <!-- Cargar React -->
    <script
      crossorigin
      src="https://unpkg.com/react@16/umd/react.production.min.js"
    ></script>
    <script
      crossorigin
      src="https://unpkg.com/react-dom@16/umd/react-dom.production.min.js"
    ></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>

    <title>React</title>
  </head>
  <body>
    <div id="root"></div>

    <script type="text/babel">
      const divRoot = document.querySelector("#root");
      const name = "Ale Roses";
      const h1Tag = <h1>Hi {name}</h1>;

      ReactDOM.render(h1Tag, divRoot);
    </script>
  </body>
</html>
```

Primero cargamos las bibliotecas de React y Babel. Añadimos algo de código para empezar a trabajar como se hace con React.

Para que el código no nos dé ningún error debemos agregar `type="text/babel"` dentro de la etiqueta `script`.

Si tienes la extensión `Live Server` solo das clic derecho **Open with live Server**.

Ahora puedes abrir los dev tools con `Ctrl + Shift + i`

[**React-index.html - Demo**](https://gist.github.com/Klerith/b0111f52ba16451d095f38d4c995605b)

### 2.5 Introducción a Babel

#### Babel

Babel es un "compilador" (o transpilador) para JavaScript. Básicamente permite transformar código escrito con las últimas y novedosas características de JavaScript y transformarlo en un código que sea entendido por navegadores más antiguos.

[Babel](https://babeljs.io/)

#### Dato sobre Babel y Vite

Vite reemplaza a Babel o a Webpack en cierto modo. Al contrario que Babel o Webpack, Vite no compila el código de JavaScript durante el desarrollo, sino que realiza la transpilación del código en tiempo real durante el proceso de desarrollo.

Esto se conoce como desarrollo en tiempo real o HMR (Hot Module Replacement). Aunque no reemplaza por completo a Babel o Webpack, Vite sigue siendo una herramienta muy poderosa y rápida para el desarrollo de aplicaciones web modernas.

[**Babeljs.io - Sitio oficial**](https://babeljs.io/)

## 🟣 3. Introducción a JavaScript moderno

### 3.1 Introducción a la sección

Sigan los videos al pie de la letra...

### 3.2 Temas puntuales de la sección

**¿Qué aprenderemos en esta sección?**

- Generar la base sobre JavaScript
- Constantes y variables Let
- Template String
- Objetos literales
- Arreglos
- Desestructruación * (sumamente importante)
- Promesas
- Fetch API
- Ternarios
- Async - Await

Mi objetivo aquí es que tengamos las bases que nos ayuden a que podamos diferenciar fácilmente qué es propio de React y qué es propio de JavaScript. Estos conceptos y ejercicios nos ayudarán a suavizar la curva de aprendizaje de React.

### 3.3 Inicio de proyecto - Bases de JavaScript

Entramos a la carpeta para empezar a trabajar, en este caso con Create React App (CRA):

```bash
.
├── 01-intro-react
│ └── index.html
├── 02-intro-js 👈👀
└── 03-counter-app
```

Para crear un proyecto de React con CRA debemos usar el siguiente comando:

```bash
npx create-react-app 02-intro-js 👈👀
cd 02-intro-js
code .
npm start
```

La estructura de CRA se ve así:

```bash
❯ tree -L 2
.
├── node_modules 👈👀 # Muchos archivos
│   ├── @aashutoshrathi
│   ├── abab
│   ├── accepts 
├── package.json
├── package-lock.json
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── logo192.png
│   ├── logo512.png
│   ├── manifest.json
│   └── robots.txt
├── README.md
└── src 👈👀
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js
    ├── logo.svg
    ├── reportWebVitals.js
    └── setupTests.js

871 directories, 17 files
```

Para el ejemplo borramos todo el contenido de la carpeta `src` y dentro creamos el archivo `index.js`.

[**create-react-app - Official Website**](https://create-react-app.dev/)

### 3.4 Variables y constantes

```js
// Variables y Constantes

const name = "Ale";
const lastName = "Roses";

let value = 5;
value = 4;

console.log(name, lastName, value);

if (true) {
  let value = 10;
  console.log(value);
}

console.log(value);
```

Creamos un respaldo con la siguiente estructura.

```bash
.
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── logo192.png
│   ├── logo512.png
│   ├── manifest.json
│   └── robots.txt
├── README.md
└── src
    ├── bases 👈👀
    │   ├── 01-const-let.js
    │   ├── 02-backticks.js
    │   ├── 03-obj-literal.js
    │   ├── 04-array.js
    │   ├── 05-functions.js
    │   ├── 06-desest-obj.js
    │   ├── 07-desest-arr.js
    │   ├── 08-imp-exp.mjs
    │   ├── 09-promises.js
    │   ├── 10-fetch.js
    │   ├── 11-async-await.js
    │   └── 12-conditional-ternary.js
    ├── data
    │   └── heroes.js
    └── index.js
```

Al final de esta sección tendremos dentro de la carpeta `bases` todos nuestros respaldos.

Para más detalles sobre variables ver los [Apuntes js-básico](https://github.com/aleroses/Platzi/blob/master/DW/2-intermedio/001-js-basico/js-basico.md#4-variables-en-javascript)

### 3.5 Template String

```js
const name = "Ale";
const lastName = "Roses";

const fullName = `${name} ${lastName}`;

console.log(fullName);

function getGreeting(name) {
  return "He " + name;
}

console.log(`This a text: ${getGreeting("Ghost")}`);
```

> Para obtener sugerencias usar `Ctrl + Barra espaciadora`

Recomiendo usar la extensión **JavaScript Auto Backticks** que nos permite añadir Backticks rápidamente.

Si escribimos `"${}"` automáticamente los genera `${name}`

### 3.6 Objetos literales

```js
const person = {
  name: "Ale",
  lastName: "Roses",
  age: 28,
  address: {
    city: "New York",
    zip: 1234,
    lat: 14.2324,
    lng: 34.3003,
  },
};

const human = { ...person };

console.log(person);
console.table(person);
console.log(human);
console.log({ person, human });
```

**Recursividad** para hacer una copia profunda:

```js
const person = {
  name: "Ale",
  lastName: "Roses",
  age: 28,
  address: {
    city: "New York",
    zip: 1234,
    lat: 14.2324,
    lng: 34.3003,
    x: {
      city: "New York",
      zip: 1234,
      lat: 14.2324,
      lng: 34.3003,
    },
    y: [
      "city",
      "New York",
      "zip",
      1234,
      "lat",
      14.2324,
      "lng",
      34.3003,
    ],
  },
};

/* En JS todo es un objeto: {} / []  */
const deepCopy = (obj) => {
  if (typeof obj !== "object" || obj === null) {
    return obj;
  }

  const newObj = Array.isArray(obj) ? [] : {};

  for (const key in obj) {
    if (obj.hasOwnProperty(key)) {
      newObj[key] = deepCopy(obj[key]);
    }
  }

  console.log(newObj);
  return newObj;
};

deepCopy(person);
```

Si quieres probar el código sin salir de VSC puedes usar la extensión **Code Runner**.

### 3.7 Arreglos

```js
// Arreglos en JS
// const newArray = new Array();
const newArray = [1, 2, 3];

// NO recomendado (push)
// newArray.push(1);
// newArray.push(2);
// newArray.push(3);

let newArray2 = [...newArray, 4, 5];
let newArray3 = newArray2.map((n) => n * 2);

console.log(newArray, newArray2, newArray3);
```

[**Mozilla MDN: Array.map()**](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

### 3.8 Funciones

```js
// Functions en Js

function gretting(name) {
  return `Hello, ${name}`;
}

console.log(gretting("Goku"));
```

Otros ejemplos:

```js
const gretting = (name) => {
  return `Hello, ${name}`;
};

console.log(gretting("Goku"));

const getUser = () => ({
  uid: "ABC123",
  username: "The-crazy-man",
});

const user = getUser();
console.log(user);

const getActiveUser = (name) => ({
  uid: "ABC567",
  username: name,
});

const activeUser = getActiveUser("Ale");
console.log(activeUser);
```

### 3.9 Desestructuración de Objetos

```js
// Desestructuración
// Asignación Desestructurante

const person = {
  name: "Ale",
  year: 45,
  key: "Ironman",
  rank: "Soldier",
};

const { year, key, name: nameTwo } = person;

// console.log(nameTwo, year, key);

const useContext = ({
  name,
  key,
  year,
  rank = "Captain",
}) => {
  // const { year, key, name: nameTwo } = user;
  // console.log(name, year, rank);

  return {
    name: key,
    anios: year,
    latlng: {
      lat: 14.1234,
      lng: -12.2323,
    },
  };
};

const {
  name,
  anios,
  latlng: { lat, lng },
} = useContext(person);

// const { lat, lng } = latlng;

console.log(name, anios, lat, lng);
```

[**Mozilla MDN: Asignación Desestructurante**](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

### 3.10 Desestructuración de Arreglos

```js
const characters = ["Goku", "Vegeta", "Trunks"];

const [, , c3] = characters;

console.log(c3);

const showArray = () => {
  return ["ABC", 123];
};

const [one, two] = showArray();

console.log(one, two);

const useState = (value) => {
  return [
    value,
    () => {
      console.log("Hello world");
    },
  ];
};

const [name, setNumber] = useState("Goku");
// arr[1]();

console.log(name);
setNumber();
```

Para seleccionar todas las coincidencias de una palabra, solo debes posar el cursor sobre la palabra en cuestión y presionar:

`Ctrl + Shift + l` o también `Ctrl + d`

Otra opción sería presionar `F2` y darle el nuevo nombre a la variable o fracción de código que se desea modificar.

### 3.11 Import, export y funciones comunes de arreglos

```js
import { heroes } from "../data/heroes.js";

const getHeroById = (id) => {
  return heroes.find((value) => value.id === id);
};

const getHeroesByOwner = (owner) => {
  return heroes.filter((hero) => hero.owner === owner);
};

console.log(getHeroesByOwner("DC"));

export { getHeroById, getHeroesByOwner };
```

`data > heroes.js`

```js
const heroes = [
  {
    id: 1,
    name: "Batman",
    owner: "DC",
  },
  {
    id: 2,
    name: "Spiderman",
    owner: "Marvel",
  },
  {
    id: 3,
    name: "Superman",
    owner: "DC",
  },
  {
    id: 4,
    name: "Flash",
    owner: "DC",
  },
  {
    id: 5,
    name: "Wolverine",
    owner: "Marvel",
  },
];

export { heroes };
```

**[Heroes.js](https://gist.github.com/Klerith/4aeb99d31aedbc29ff4d54bbb77d2d7f)**

[**Mozilla Mdn: Find**](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/find)|

### 3.12 Múltiples exportaciones y exportaciones por defecto

```js
export default heroes;

// Al exportar de las siguientes maneras:
export const owner = ["DC", "Marvel"];
// O, la "importación" se hace usando {}
export { owner };

// También
export { heroes as default, owner };

// ----------------------------------------
// En lo personal no me gusta esta forma
import heroes, { owner } from "../data/heroes.js";

// Prefiero esto
import { heroes, owner } from "../data/heroes.js";
```

En el primer ejemplo, `heroes` es una exportación por defecto y la `owner` no.

### 3.13 Promesas

```js
import { getHeroById } from "./08-imp-exp.mjs";

const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    const data = getHeroById(2);

    resolve(data);
    reject("Id not found");
  }, 2000);
});

promise
  .then((response) => console.log(response))
  .catch((err) => console.warn(err));
```

Otro ejemplo:

```js
import { getHeroById } from "./08-imp-exp.mjs";

const getHeroByIdAsync = (id) => {
  const promise = new Promise((resolve, reject) => {
    setTimeout(() => {
      const data = getHeroById(id);

      data ? resolve(data) : reject("Id not found");
    }, 2000);
  });

  return promise;
};

getHeroByIdAsync(14).then(console.log).catch(console.warn);
```

📌 Si no te sale el `import` automáticamente sitúate en la parte superior y escribe el nombre, en este caso `getHeroeById` y verás como te sale para importar automáticamente. En caso escribas el nombre de la función a importar y no te la importe, puedes abrir el archivo donde está esa función, esto hará que importe y autocomplete la ubicación exacta de esa función.

[**Mozilla MDN: Promesas**](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Promise)

### 3.14 Fetch API

Crea una cuenta en Giphy API y crea un `api key` con los siguientes pasos:

- Entra en **Create an App**
- Selecciona **API Selected**
- **Next** 
- Dale un nombre a la app con su respectiva descripción.
- Por último dale a **Create App**.

Para el ejemplo usaremos [Random Endpoint](https://developers.giphy.com/docs/api/endpoint/#random) que mostrara una imagen de manera aleatoria.

```js
// Ingresa tu Api key en la url antes de pegarla en un navegador
api.giphy.com/v1/gifs/random?api_key=xdCnnfEOEkSz4TEgLmMc09dBClFt99Ou
```

Esto mostrará un objeto con mucha información.

```js
const apiKey = "xdCnnfEOEkSz4TEgLmMc09dBClFt99Ou";
const getGiphy = fetch(
  `https://api.giphy.com/v1/gifs/random?api_key=${apiKey}`
);

getGiphy
  .then((response) => response.json())
  .then(({ data }) => {
    const { url } = data.images.original;

    const img = document.createElement("img");
    img.src = url;

    document.body.append(img);
  })
  .catch(console.warn);
```

[**Giphy API**](https://developers.giphy.com/)

[**Mozilla MDN: Fetch**](https://developer.mozilla.org/es/docs/Web/API/Fetch_API)

### 3.15 Async - Await

Primera forma:

```js
const getImage = () => {
  const promise = new Promise((resolve, reject) => {
    resolve("c");
  });

  return promise;
};

getImage().then(console.log);
```

Otra forma: 

```js
const getImage = async () => {
  return "https://asdffsafs.com";
};
getImage().then(console.log);
```

Otra forma:

```js
const getImage = async () => {
  try {
    const apiKey = "xdCnnfEOEkSz4TEgLmMc09dBClFt99Ou";
    const response = await fetch(
      `https://api.giphy.com/v1/gifs/random?api_key=${apiKey}`
    );
    const { data } = await response.json();

    const img = document.createElement("img");
    // img.src = data.data.images.original.url;
    img.src = data.images.original.url;

    document.body.append(img);

    return data;
  } catch (error) {
    console.error(error);
  }
};

getImage();
```

### 3.16 Operador condicional ternario

```js
const active = true;
// let message = active ? "Active" : "Inactive"
let message = !active && "Active";

console.log(message);
```

### 3.17 Nota sobre JavaScript

#### **Terminamos la sección de reforzamiento de JavaScript**

Pero recuerden que esto es para entrar en calor y que lo temas principales de JavaScript que necesito que conozcan estén cubiertos, pero les recomiendo que cualquier duda adicional sobre el lenguaje, sobre métodos y demás, la consulten aquí

[**https://developer.mozilla.org/es/**](https://developer.mozilla.org/es/)

Como ya les había mencionado, considero esa página la mejor en cuanto a documentación sobre JavaScript.

También si sienten que necesitan más sobre JavaScript en video, mi curso de JavaScript Moderno es el indicado para eso.

En fin!, es momento de empezar con React!

Recursos de la lección:

[**Repositorio de GitHub del proyecto**](https://github.com/Klerith/react-intro-javascript)

## 🟣 4. Primeros pasos en React

### 4.1 Introducción a la sección

### 4.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Nuestra primera aplicación - Hola Mundo
- Exposiciones sobre los componentes
- Creación de componentes (Functional Components)
- Propiedades - Props
- Impresiones en el HTML 
- PropTypes  
- DefaultProps 
- Introducción general a los Hooks  
- useState

Es una sección importante, especialmente para todos los que están empezando de cero en React, ya que dará las bases de cómo segmentar la lógica de nuestra aplicación en pequeñas piezas más fáciles de mantener.

### 4.3 ¿Qué son los componentes?

Pequeña pieza de código encapsulada reutilizable que puede tener estado o no.

Es buena práctica que los componentes se nombren usando `PascalCase`.

- camelCase
- snake_case
- PascalCase

```js
TwitterApp > Router > Screen/Página > Menú > MenuItem
```

El estado es como se encuentra la información del componente en un punto determinado del tiempo.

### 4.4 Primera aplicación de React

```bash
yarn create vite

# Nombrar proyecto
03-counter-app
# Seleccionar un framework
React
# Seleccionar variante
JavaScript
```

Si deseas renombrar una carpeta y estás en Linux lo puedes hacer con la CLI.

```bash
# Renombrar una carpeta:
mv nombre_actual nuevo_nombre
```

Ahora nos movemos al proyecto creado

```bash
cd 03-counter-app
yarn install
code .
yarn dev
```

La estructura del proyecto es la siguiente:

```bash
.
├── index.html
├── node_modules 👈👀 # Muchos archivos
├── package.json
├── public
│   └── vite.svg
├── README.md
├── src
│   ├── App.css
│   ├── App.jsx
│   ├── assets
│   │   └── react.svg
│   ├── index.css
│   └── main.jsx
├── vite.config.js
└── yarn.lock

522 directories, 1281 files
```

Si quieres ver como se hace con CRA puedes revisar la sección 3.

[[react-hooks-mern#3. Introducción a JavaScript moderno#🟣 Inicio de proyecto - Bases de JavaScript]]

[Inicio de proyecto - Bases de JavaScript](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/devTalles/react-hooks-mern.md#-inicio-de-proyecto---bases-de-javascript)

[**Create-React-App - Documentación**](https://create-react-app.dev/)

[**Vite documentation**](https://vitejs.dev/)|

### 4.5 Estructura de directorios - CRA

En los proyectos creados con **NPM** se puede observar que tenemos el archivo `package-lock.json` que nos dice como fueron construidas las dependencias de los módulos de Node.

**[Referencia: Robots.txt](https://developers.google.com/search/docs/advanced/robots/intro?hl=es&visit_id=637909934831052162-4097033822&rd=1)**

**[Google Developers - PWA](https://web.dev/learn/pwa/)**

**[React-Scripts](https://create-react-app.dev/docs/available-scripts/)**

### 4.6 Estructura de directorios - Vite

Ver estructura en [[react-hooks-mern#4. Primeros pasos en React#🟣 Primera aplicación de React]]

Si se creó el proyecto con **Yarn** no se recomienda mezclarlo con **NPM**.

En caso desees cambiar debes borrar el archivo `package-lock.json` o `yarn.lock` y volver a hacer `npm install` o `yarn install`.

El archivo `vite.config.js` sirve para hacer configuraciones propias de vite.

### 4.7 Hola Mundo en React

Abrimos el proyecto `03-counter-app-vite`.

```bash
yarn dev
```

Borramos todos los archivos del folder `src` y creamos un archivo `main.jsx`.

```jsx
import React from "react";
import ReactDOM from "react-dom/client";

// Mala practica
const App = () => {
  return <h1>App</h1>;
};

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

```html
<body>
  <div id="root"></div> 👈👀
  <script type="module" src="/src/main.jsx"></script>
</body>
```

### 4.8 Nuestro primer Componente

Creamos el archivo `App.jsx` dentro del `src`.

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { App } from "./App";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

`src > App.jsx`

```jsx
import React from "react";

// rafc
const App = () => {
  return <h1>App</h1>;
};

export { App };
```

📌 Nota: Si haces una exportación por `defaul`, en el lugar de la **importación** puedes darle el **nombre que quieras**.

```js
export defaul App;

import TestApp👈 from "./App";
```

### 4.9 Tarea - Crear un nuevo componente

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { App } from "./App";
import { FirstTest } from "./FirstTest";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
    <FirstTest />
  </React.StrictMode>
);
```

`src > FirstTest.jsx`

```jsx
const FirstTest = () => {
  return (
    <>
      <h1>Ale Roses</h1>
    </>
  );
};

export { FirstTest };
```

### 4.10 Retornar elementos en el Componente - Fragment

`src > FirstTest.jsx`

```jsx
const FirstTest = () => {
  return (
    <> 👈👀
      <h1>Ale Roses</h1>
      <p>First course with Fernando Herrera.</p>
    </>
  );
};

export { FirstTest };
```

### 4.11 Impresión de variables en el HTML

`src > FirstTest.jsx`

```jsx
const newObject = {
  name: "Ale Roses",
  nickname: "Ghost"
}

const newArray = [0, 1, 2, 3, 4];

const getResult = () => {
  return 4 + 4;
}

const FirstTest = () => {
  return (
    <>
      <h1>{newObject.name}</h1>
      <p>{newObject.nickname}</p>
      <p>{newArray}</p>
      <p>{getResult()}</p>
      <code>{JSON.stringify(newMessage)}</code>
    </>
  );
};

export { FirstTest };
```

### 4.12 Colocar estilos de CSS

Dentro del `src` creamos un archivo `styles.css` donde podremos agregar los estilos que necesitemos.

`src > styles.css`

```css
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

html,
body {
  background-color: #21232a;
  color: white;
  font-family: Helvetica, Arial, sans-serif;
  font-size: 1.3rem;
  padding: 70px;
}

button {
  padding: 5px;
  font-size: 1rem;
  margin: 0.2rem;
}
```

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { App } from "./App";
import { FirstTest } from "./FirstTest";

import "./styles.css"; 👈👀

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
    <FirstTest />
  </React.StrictMode>
);
```

### 4.13 Comunicación entre componentes - Props

`src > FirstTest.jsx`

```jsx
const FirstTest = ({
  title,
  subTitle,
  name,
}) => {
  return (
    <>
      <h1>{title}</h1>
      <p>{subTitle}</p>
      <p>{name}</p>
    </>
  );
};

export { FirstTest };
```

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { App } from "./App";
import { FirstTest } from "./FirstTest";

import "./styles.css"; 👈👀

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
    <FirstTest
      title="Hi, I'm a bot"
      subTitle={"Subject subtitle"}
    />
  </React.StrictMode>
);
```

**Dev tools** ⚛️ Components: Veremos los nombres de los componentes (árbol de componentes / contexto)

![React dev tools](https://i.postimg.cc/9FhNVk3M/react-dev-tools.png)

### 4.14  PropTypes

En Vite no viene instalado por defecto:

```bash
yarn add prop-types 

# Para NPM
npm install prop-types
```

`src > FirstTest.jsx`

```jsx
import PropTypes from "prop-types"; 👈👀

const FirstTest = ({
  title,
  subTitle,
  name,
}) => {
  return (
    <>
      <h1 data-testid="test-title">{title}</h1>
      <p>{subTitle}</p>
      <p>{name}</p>
    </>
  );
};

FirstTest.propTypes = { 👈👀👇
  title: PropTypes.string.isRequired,
  subTitle: PropTypes.string,
};
```

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { App } from "./App";
import { FirstTest } from "./FirstTest";

import "./styles.css"; 👈👀

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
    <FirstTest
      title 👈👀 // True (valor booleano)
      subTitle={"Subject subtitle"}
    />
  </React.StrictMode>
);
```

### 4.15 DefaultProps

`src > FirstTest.jsx`

```jsx
import PropTypes from "prop-types";

const FirstTest = ({
  title = "No title", 👈👀
  subTitle,
  name,
}) => {
  return (
    <>
      <h1 data-testid="test-title">{title}</h1>
      <p>{subTitle}</p>
      <p>{name}</p>
    </>
  );
};

FirstTest.propTypes = {
  title: PropTypes.string.isRequired,
  subTitle: PropTypes.string,
};

FirstTest.defaultProps = {
  subTitle: "New Text", 👈👀
  name: "Ale Roses",
};

export { FirstTest };
```

📌 Nota: El soporte para `defaultProps` será removido y se deberán usar los parámetros predeterminados de JavaScript. Ahora lo aconsejable es colocar el valor por defecto al **desestructurar** directamente las **props** del componente.

### 4.16 Tarea - Componente CounterApp

1. Crear un nuevo componente dentro de la carpeta SRC llamado
    `CounterApp`

2. El `CounterApp` debe de ser un __Functional Component__

3. El contenido del __CounterApp__ debe de ser:
    ```jsx
        <h1>CounterApp</h1>
        <h2> { value } </h2>
    ```

4. Donde `"value"` es una propiedad enviada desde el padre hacia
    el componente __CounterApp__ __(Debe ser númerica validada con PropTypes)__

5. Reemplazar en el `index.js` ó `main.jsx` el componente de `<PrimeraApp />`
    por el componente `<CounterApp />`
        (no se olviden del value que debe de ser un número)

6. Asegúrense de no tener errores ni warnings
    (Cualquier warning no usado, comentar el código)

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { CounterApp } from "./CounterApp";

import "./styles.css";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <CounterApp value={1} />
  </React.StrictMode>
);
```

`src > CounterApp.jsx`

```jsx
import PropTypes from "prop-types";

const CounterApp = ({ value }) => {
  return (
    <>
      <h1>Counter App</h1>
      <h2>{value}</h2>
    </>
  );
};

CounterApp.propTypes = {
  value: PropTypes.number.isRequired,
};

export { CounterApp };
```

[**Tarea - Referencia**](https://gist.github.com/Klerith/e1a731cc595c00a9794a709062eae757)

### 4.17 Evento click (Eventos en general) + useState - Hook

`src > CounterApp.jsx`

```jsx
import React, { useState } from "react";
import PropTypes from "prop-types";

const CounterApp = ({ value }) => {
  const [counter, setCounter] = useState(value);

  const handleAdd = () => {
    // setCounter(counter + 1);
    setCounter((c) => c + 1);
  };

  const handleRest = () => {
    setCounter((c) => c - 1);
  };

  const handleReset = () => {
    setCounter(value);
  };

  return (
    <>
      <h1>Counter App</h1>

      <button onClick={handleAdd}>+1</button>
      <button onClick={handleRest}>-1</button>
      <button onClick={handleReset}>
        Reset
      </button>
      <h2>{counter}</h2>
    </>
  );
};

CounterApp.propTypes = {
  value: PropTypes.number.isRequired,
};

export { CounterApp };
```

Esta funcionalidad está disponible en Obsidian:

[[react-js-desde-cero#**12.** Hooks]] 👈👀

![](https://i.postimg.cc/V6tSbM1f/obsidian.png)

[**Reactjs.org - Eventos**](https://es.reactjs.org/docs/events.html)

[**Reactjs.org - Hooks**](https://es.reactjs.org/docs/hooks-intro.html)

[**Ejemplo - Tarea de desestructuración de arreglos**](https://github.com/Klerith/react-intro-javascript/blob/master/src/bases/07-deses-arr.js)

### 4.18 Código fuente de la sección

[**Github - fin-seccion-4**](https://github.com/Klerith/react-vite-counter-app/tree/fin-seccion-4)

## 🟡 5. Pruebas unitarias y de integración - Probando las secciones anteriores

### 5.1 Introducción a la sección

Probar la ruta crítica:

Probar la ruta crítica de una aplicación se refiere a realizar pruebas exhaustivas y enfocadas en las funciones o flujos de trabajo más críticos o prioritarios dentro de la aplicación. La ruta crítica representa aquellos caminos o secuencias de acciones que deben funcionar correctamente para que la aplicación cumpla con sus objetivos principales.

La idea detrás de probar la ruta crítica es asegurarse de que las funciones esenciales de la aplicación estén correctamente implementadas y sean confiables. Al enfocarse en estos aspectos clave, se puede identificar y solucionar problemas críticos antes de que afecten la experiencia del usuario o el funcionamiento general de la aplicación.

Aquí tienes algunos ejemplos de pruebas de ruta crítica para diferentes tipos de aplicaciones:

1. Aplicación de comercio electrónico:
   - Probar el proceso de inicio de sesión y registro de usuarios.
   - Verificar la funcionalidad del carrito de compras, desde la adición de productos hasta el pago y la generación de una orden.
   - Comprobar la correcta visualización y actualización del inventario de productos.

2. Aplicación bancaria en línea:
   - Realizar pruebas de inicio de sesión y autenticación de usuarios.
   - Probar las funciones de transferencia de fondos, asegurándose de que los saldos se actualicen correctamente.
   - Verificar la visualización precisa del historial de transacciones y la generación de estados de cuenta.

3. Aplicación de reserva de vuelos:
   - Probar la búsqueda y filtrado de vuelos según diferentes criterios, como origen, destino y fechas.
   - Verificar la correcta selección de asientos y opciones de personalización durante el proceso de reserva.
   - Comprobar el flujo de pago, asegurándose de que la transacción se realice correctamente.

### 5.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Introducción a las pruebas
- AAA
	- Arrange: Arreglar
    - Act: Actuar
    - Assert: Afirmar
- Primeras pruebas
- Jest
- Expect
- toBe
- Enzyme
- Comandos útiles en la terminal para pruebas
- Revisar elementos renderizados en el componente
- Simular eventos

Esta sección de pruebas es sumamente importante porque nos dará la base de las pruebas que estaremos haciendo durante el curso, las pruebas irán creciendo en complejidad, por lo que les recomiendo que nos aseguremos de comprender bien todos estos conceptos para que nos sea más fácil las siguientes secciones de pruebas.

### 5.3 Introducción a las pruebas unitarias y de integración

Unitarias: Enfocadas en pequeñas funcionalidades.

Integración: Enfocadas en cómo reaccionan varias piezas en conjunto.

**Características de las pruebas:**

1. Fáciles de escribir
2. Fáciles de leer
3. Confiables
4. Rápidas
5. Principalmente unitarias

Pasos para enfocarnos en que todo trabaje bien entre sí (AAA):
1. Arrange (Arreglar): Inicialización
2. Act (Actuar): Estimulo
3. Assert (Afirmar): Observar el comportamiento

Arrange: Preparamos el estado inicial.
- Inicializamos variables
- Importaciones necesarias

Act: Aplicamos acciones o estímulos.
- Llamar métodos
- Simular clicks
- Realizar acciones sobre el paso anterior

Assert: Observar el comportamiento resultante.
- Son los resultados esperados.
- Ej: Que algo cambie, algo incremente o bien que nada suceda.

### 5.4 Inicio de la sección - Pruebas sobre lo aprendido anteriormente

Para las pruebas usaremos varios ejercicios que vimos en la parte de la introducción a JavaScript. Puedes copiar y pegar la carpeta `bases` del proyecto `02-intro-js` o descargar la carpeta comprimida desde la parte inferior del video. 

Estos archivos los pegamos dentro del `src` del proyecto `03-counter-app`, pero también pueden crear un proyecto totalmente nuevo.

[Download Bases](https://import.cdn.thinkific.com/643563/courses/1901683/basepruebas-220616-140151.zip)

### 5.5 Mi primera prueba y configuraciones iniciales

Para las pruebas usaremos **Jest** y **React Testing Library**, dos herramientas muy populares en el ecosistema de pruebas de JavaScript y React.

#### Jest

##### ¿Qué es Jest?

Jest es un framework de pruebas de JavaScript desarrollado por Facebook. Está diseñado para trabajar con proyectos que utilizan React, aunque también se puede usar para probar aplicaciones JavaScript en general.

##### Características principales de Jest:

- **Configuración mínima**: Jest requiere poca configuración para comenzar a usarlo, lo que facilita su adopción.
- **Velocidad**: Jest ejecuta las pruebas en paralelo para maximizar la velocidad de ejecución.
- **Mocks y Espías**: Proporciona herramientas integradas para crear mocks y espías de funciones.
- **Snapshots**: Permite crear instantáneas del estado de la interfaz en un momento específico para comparar en pruebas futuras.
- **Cobertura de código**: Genera informes de cobertura de código detallados.
- **Watch Mode**: Reejecuta pruebas automáticamente cuando los archivos relacionados cambian.

##### Ejemplo básico de Jest:

```jsx
import sum from './sum';

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

#### Testing Library

##### ¿Qué es Testing Library?

Testing Library es un conjunto de utilidades para probar componentes de UI de manera accesible y amigable para el usuario. `@testing-library/react` es su implementación específica para React.

##### Filosofía de Testing Library:

- **Centrado en el usuario**: Testing Library fomenta las pruebas que se asemejan a cómo los usuarios interactúan con tu aplicación.
- **Accesibilidad**: Promueve prácticas que mejoran la accesibilidad, como seleccionar elementos por roles, etiquetas y texto visible.
- **Simplicidad**: Proporciona una API simple y ligera que facilita escribir y mantener pruebas.

##### Características principales de Testing Library:

- **Selección de elementos**: Métodos como `getByText`, `getByRole`, `getByLabelText` para seleccionar elementos de manera accesible.
- **Pruebas asincrónicas**: Utilidades como `waitFor` y `findBy` para manejar componentes que actualizan su estado de manera asincrónica.
- **Utilidades de eventos**: `fireEvent` para simular eventos del navegador.

##### Ejemplo básico de Testing Library con Jest:

```jsx
import React from 'react';
import { render, screen, fireEvent } from '@testing-library/react';
import '@testing-library/jest-dom/extend-expect';
import MyComponent from './MyComponent';

test('renders learn react link', () => {
  render(<MyComponent />);
  const linkElement = screen.getByText(/learn react/i);
  expect(linkElement).toBeInTheDocument();
});

test('button click updates text', () => {
  render(<MyComponent />);
  const button = screen.getByRole('button', { name: /click me/i });
  fireEvent.click(button);
  const updatedText = screen.getByText(/you clicked the button/i);
  expect(updatedText).toBeInTheDocument();
});
```

#### Configurar Jest

Para empezar a usar Jest primero debemos configurarlo, ya que en Vite no vienen configurados por defecto.

Esta configuración solo se hace una vez en cada proyecto. 

```bash
yarn add --dev jest
```

Añadimos el script de ejecución dentro del archivo `package.json`.

```json
"scripts": {
    "dev": "vite",
    "build": "vite build",
    "lint": "eslint . --ext js,jsx --report-unused-disable-directives --max-warnings 0",
    "preview": "vite preview",
    "test": "jest" 👈👀
  },
```

Dentro de la carpeta de nuestro proyecto creamos una carpeta llamada `tests`. Este será como un espejo del `src`.

Ahora podemos hacer una demostración de como funcionan los test.

`tests > demo.test.js`

```js
test("Esta prueba no debe de fallar", () => {
  if (0 === 1) {
    throw new Error("No puede dividir entre cero");
  }
});
```

Para correr las pruebas ejecutamos: 

```bash
yarn test
```

Si no queremos ingresar `yarn test` cada vez que queramos ejecutar las pruebas, solo debemos agregar lo siguiente en el archivo `package.json`.

```json
"scripts": {
    "dev": "vite",
    "build": "vite build",
    "lint": "eslint . --ext js,jsx --report-unused-disable-directives --max-warnings 0",
    "preview": "vite preview",
    "test": "jest --watchAll" 👈👀
  },
```

Ahora, al ejecutar `yarn test` se quedará escuchando cuando hagamos un cambio.

Mi estructura quedó algo así (cree un proyecto desde cero):

```bash
.
├── index.html
├── node_modules
├── package.json
├── public
│   └── vite.svg
├── README.md
├── src
│   ├── App.css
│   ├── App.jsx
│   ├── bases 👈👀
│   │   ├── 01-const-let.js
│   │   ├── 02-backticks.js
│   │   ├── 03-obj-literal.js
│   │   ├── 04-array.js
│   │   ├── 05-functions.js
│   │   ├── 06-desest-obj.js
│   │   ├── 07-desest-arr.js
│   │   ├── 08-imp-exp.mjs
│   │   ├── 09-promises.js
│   │   ├── 10-fetch.js
│   │   ├── 11-async-await.js
│   │   └── 12-conditional-ternary.js
│   ├── index.css
│   └── main.jsx
├── tests 👈👀👇
│   └── demo.test.js
├── vite.config.js
└── yarn.lock
```

[jestjs](https://jestjs.io/)

[Jestjs getting-started](https://jestjs.io/docs/getting-started)

### 5.6 Jest - Expect - toBe

#### `describe`

`describe` es una función en Jest que permite agrupar pruebas relacionadas bajo un mismo bloque. Esto facilita la organización y lectura de las pruebas, especialmente cuando tienes múltiples casos de prueba para una misma unidad funcional o componente.

```jsx
describe('Math functions', () => {
  // Tests relacionados con funciones matemáticas irán aquí
});
```

##### Ejemplo:

```jsx
describe('Math functions', () => {
  test('adds 1 + 2 to equal 3', () => {
    expect(1 + 2).toBe(3);
  });

  test('subtracts 2 - 1 to equal 1', () => {
    expect(2 - 1).toBe(1);
  });
});
```

#### `test`

`test` es una función en Jest que define un caso de prueba individual. También puedes usar `it` como un alias para `test`. Cada caso de prueba contiene una descripción y una función que ejecuta las expectativas para esa prueba.

```jsx
test('description of the test', () => {
  // código de la prueba
});
```

##### Ejemplo:

```jsx
test('adds 1 + 2 to equal 3', () => {
  expect(1 + 2).toBe(3);
});
```

#### `expect`

`expect` es una función en Jest que se utiliza para hacer afirmaciones en tus pruebas. Recibe un valor y devuelve un conjunto de métodos (matchers) que permiten comprobar diferentes condiciones sobre ese valor.

```jsx
expect(value).matcherMethod();
```

##### Ejemplo:

```jsx
expect(1 + 2).toBe(3);
```

##### Matchers comunes de `expect`

- **`.toBe(value)`**: Comprueba que el valor sea exactamente igual al valor esperado (usando `===`).
    
    ```jsx
    expect(2 + 2).toBe(4);
    ```
    
- **`.toEqual(value)`**: Comprueba que el valor sea igual al valor esperado, para objetos y arrays (usando comparación profunda).
    
    ```jsx
    const obj = { a: 1 };
    expect(obj).toEqual({ a: 1 });
    ```
    
- **`.toBeTruthy()`**: Comprueba que el valor sea verdadero en un contexto booleano.
    
    ```jsx
    expect(true).toBeTruthy();
    ```
    
- **`.toContain(item)`**: Comprueba que un array o string contenga un elemento específico.
    
    ```jsx
    const shoppingList = ['milk', 'bread', 'eggs'];
    expect(shoppingList).toContain('milk');
    ```

#### Ejemplo completo utilizando `describe`, `test` y `expect`

```jsx
describe('Array operations', () => {
  test('array contains milk', () => {
    const shoppingList = ['milk', 'bread', 'eggs'];
    expect(shoppingList).toContain('milk');
  });

  test('sum of numbers is correct', () => {
    expect(1 + 2).toBe(3);
  });

  test('object assignment', () => {
    const data = { one: 1 };
    data['two'] = 2;
    expect(data).toEqual({ one: 1, two: 2 });
  });

  test('null value is falsy', () => {
    const n = null;
    expect(n).toBeFalsy();
  });
});
```

En nuestro proyecto, añadimos ayudas o intelligent a Visual Studio Code.

```bash
yarn add -D @types/jest
```

`tests > demo.test.js`

```jsx
describe("Tests on the <DemoComponent/>", () => {
  test("This test must not fail", () => {
    // 1. Initialization
    const message1 = "Hi world";

    // 2. Stimulus
    const message2 = message1.trim();

    // 3. Observe expected behavior
    expect(message1).toBe(message2); 👈👀
  });
});
```

[Jest Expect](https://jestjs.io/docs/expect#reference)

### 5.7 Nota de Actualización - Extensión de archivos

En la siguiente clase se hace la configuración para las pruebas de nuestros distintos archivos, en caso de ver el error:

```bash
You appear to be using a native ECMAScript module configuration file, which is only supported when running Babel asynchronously.
```
  
Cambiar extensión de los archivos `jest.config.js` y `babel.config.js` a `.cjs`
  
Para ver más detalles al respecto pueden ir a [https://nodejs.org/docs/latest/api/modules.html#enabling](https://nodejs.org/docs/latest/api/modules.html#enabling "https://nodejs.org/docs/latest/api/modules.html#enabling").

### 5.8 Pruebas en el archivo `02-template-string.js`

Configuración de Babel: Esto instala las dependencias necesarias para integrar Babel con Jest y permitir que Jest transforme el código ES6+ durante las pruebas.

```bash
yarn add --dev babel-jest @babel/core @babel/preset-env
```

Al usar Babel con Jest, puedes escribir tu código de pruebas utilizando las últimas características de JavaScript, y Babel se encargará de transformar ese código a una versión que Jest pueda ejecutar. Esto es especialmente útil si estás utilizando sintaxis moderna de JavaScript que no es compatible de manera nativa con la versión de Node.js que estás usando para ejecutar tus pruebas.

Creamos el archivo `babel.config.cjs`

```js
module.exports = {
  presets: [
    ["@babel/preset-env", { targets: { node: "current" } }],
  ],
};
```

- **`module.exports`**: Esto exporta la configuración para que Babel pueda usarla.
    
- **`presets`**: Los presets son conjuntos de plugins de Babel que permiten transformar el código JavaScript de manera específica.
    
- **`["@babel/preset-env", { targets: { node: "current" } }]`**: Aquí se está utilizando el preset `@babel/preset-env` con una configuración específica. El objeto `{ targets: { node: "current" } }` le dice a Babel que transforme el código para que sea compatible con la versión actual de Node.js que se está utilizando para ejecutar las pruebas.

[Using Babel](https://jestjs.io/docs/getting-started#using-babel)

`src > bases > 02-backticks.js`

```jsx
function getGreeting(name) {
  return "Hi " + name;
}

export { getGreeting };
```

Creamos una carpeta para las pruebas:

```bash
├── tests 
│   └── bases 👈👀
│   │   ├── 01-const-let.js
│   │   ├── 02-backticks.js
│   │   ├── 03-obj-literal.js
│   │   ├── 04-array.js
│   │   ├── 05-functions.js
│   │   ├── 06-desest-obj.js
│   │   ├── 07-desest-arr.js
│   │   ├── 08-imp-exp.mjs
│   │   ├── 09-promises.js
│   │   ├── 10-fetch.js
│   │   ├── 11-async-await.js
│   │   └── 12-conditional-ternary.js
```

`test > base-pruebas > 02-template-string.test.js`

```jsx
import { getGreeting } from "../../src/bases/02-backticks";

describe("Test on 02-template-string", () => {
  test("getGreeting should return a greeting. ", () => {
    const name = "Ale Roses";
    const message = getGreeting(name);

    expect(message).toBe(`Hi ${name}`);
  });
});
```

En la terminal podremos usar `w` para mostrar más opciones y `p` para buscar el nombre del archivo a probar.

```bash
Watch Usage: Press w to show more.
```

```bash
Watch Usage
 › Press a to run all tests.
 › Press f to run only failed tests.
 › Press o to only run tests related to changed files.
 › Press p to filter by a filename regex pattern.
 › Press t to filter by a test name regex pattern.
 › Press q to quit watch mode.
 › Press Enter to trigger a test run.
```

### 5.9 toEqual

`toEqual` es un matcher en Jest que se utiliza para verificar que dos valores son equivalentes en contenido. A diferencia de `toBe`, que usa el operador de igualdad estricta (`===`) y verifica que los dos valores comparados son exactamente el mismo objeto o valor primitivo, `toEqual` realiza una comparación profunda. Esto significa que verifica que los valores dentro de **objetos** y **arrays** sean los mismos, no que los objetos o arrays sean exactamente el mismo objeto en memoria.

También sirve el `toStrictEqual`.

#### Comparación con `toBe`

- **`toBe`**: Usa el operador `===` y verifica que los valores sean exactamente los mismos en términos de identidad.
    
    ```jsx
    test('toBe with primitive values', () => {
      expect(1 + 2).toBe(3);
    });
    
    test('toBe with objects fails', () => {
      const obj = { a: 1 };
      expect(obj).toBe({ a: 1 }); // Falla porque no son el mismo objeto en memoria
    });
    ```
    
- **`toEqual`**: Realiza una comparación profunda para verificar la equivalencia de contenido.
    
    ```jsx
    test('toEqual with objects', () => {
      const obj = { a: 1 };
      expect(obj).toEqual({ a: 1 }); // Pasa porque los contenidos son iguales
    });
    ```

📌 `toEqual` es muy útil para verificar que estructuras complejas de datos, como objetos y arrays, tienen el mismo contenido, sin preocuparse por si son exactamente la misma referencia en memoria.

Ahora veamos nuestro proyecto...

`src > bases > 05-functions.js`

```js
const getUser = () => ({
  uid: "ABC123",
  username: "The-crazy-man",
});

const getActiveUser = (name) => ({
  uid: "ABC567",
  username: name,
});

export { getUser, getActiveUser };
```

`test > bases > 05-functions.test.js`

```js
import {
  getActiveUser,
  getUser,
} from "../../src/bases/05-functions";

describe("Test on 05-functions", () => {
  test("getUser should return a object", () => {
    const testUser = {
      uid: "ABC123",
      username: "The-crazy-man",
    };

    const user = getUser();

    expect(user).toEqual(testUser); 👈👀
  });

  test("getActiveUser should return an object", () => {
    const data = "Ale Roses";
    const activeUser = (name) => ({
      uid: "ABC567",
      username: name,
    });
    const testUser = getActiveUser(data);

    expect(activeUser(data)).toEqual(testUser); 👈👀
  });
});
```

### 5.10 Pruebas en el archivo `07-deses-arr.js`

`src > bases > 07-desest-arr.js`

```jsx
const showArray = () => {
  return ["ABC", 123];
};

export { showArray };
```

`test > bases > 07-desest-arr.test.js`

```jsx
import { showArray } from "../../src/bases/07-desest-arr";

describe("Test on 07-desest-arr", () => {
  test("showArray should return a string and a number", () => {
    const [letters, numbers] = showArray();

    expect(letters).toBe("ABC");
    expect(numbers).toBe(123);

    expect(typeof letters).toBe("string");
    expect(typeof numbers).toBe("number");

    expect(letters).toEqual(expect.any(String)); 👈👀
  });
});
```

**`expect.any(String)`**: Verifica que el valor es cualquier cadena de texto.

📌 La línea `expect(letters).toEqual(expect.any(String));` no está anidando los `expect`. En lugar de eso, se está utilizando el matcher `expect.any` como un argumento para `toEqual`.

Vamos a desglosarlo y luego hablaré sobre el matcher `any`.

- **`expect(letters)`**: Esto crea una expectativa sobre la variable `letters`.
- **`.toEqual(...)`**: Este matcher verifica que el valor de `letters` sea igual al valor esperado que se pasa como argumento.
- **`expect.any(String)`**: Este matcher especial se utiliza para verificar que el valor sea de cualquier tipo de `String`.

El matcher `expect.any` se pasa como argumento a `toEqual`, lo que significa que Jest verificará que `letters` sea cualquier cadena de texto, no una cadena específica. No hay anidamiento de `expect` aquí; simplemente se está usando `expect.any` dentro de `toEqual`.

#### ¿Qué es `expect.any`?

`expect.any(constructor)` es un matcher en Jest que se utiliza para verificar que un valor es de un tipo específico, sin preocuparse por el valor exacto. El `constructor` puede ser cualquier función constructora como `String`, `Number`, `Object`, `Array`, etc.

```jsx
expect.any(constructor)
```

Donde `constructor` es una función constructora para el tipo de valor que estás verificando.

#### Ejemplos de uso

##### Verificar que el valor es una cadena

```jsx
test('value is a string', () => {
  const value = 'Hello, world!';
  expect(value).toEqual(expect.any(String));
});
```

##### Verificar que el valor es un número

```jsx
test('value is a number', () => {
  const value = 123;
  expect(value).toEqual(expect.any(Number));
});
```

##### Verificar que el valor es un objeto

```jsx
test('value is an object', () => {
  const value = { key: 'value' };
  expect(value).toEqual(expect.any(Object));
});
```

##### Verificar que el valor es un array

```jsx
test('value is an array', () => {
  const value = [1, 2, 3];
  expect(value).toEqual(expect.any(Array));
});
```

#### Uso combinado con otros matchers

`expect.any` puede ser utilizado con otros matchers para crear expectativas más flexibles. Aquí hay algunos ejemplos:

##### Verificar propiedades de un objeto

```jsx
test('object has properties with specific types', () => {
  const user = {
    name: 'John Doe',
    age: 30,
  };

  expect(user).toEqual({
    name: expect.any(String),
    age: expect.any(Number),
  });
});
```

##### Verificar elementos de un array

```jsx
test('array contains elements of specific types', () => {
  const items = ['apple', 'banana', 'cherry'];

  expect(items).toEqual([
    expect.any(String),
    expect.any(String),
    expect.any(String),
  ]);
});
```

### 5.11 Pruebas en `08-imp-exp.js - Arreglos`

#### `toBeFalsy()`

`toBeFalsy()` es un matcher en Jest que se utiliza para verificar que un valor sea "falsy" en JavaScript. En JavaScript, los valores "falsy" son aquellos que se consideran falsos cuando se evalúan en un contexto booleano. Estos valores son:

- `false`
- `0`
- `""` (cadena vacía)
- `null`
- `undefined`
- `NaN`

Cualquier valor que no esté en esta lista es considerado "truthy" (es decir, se considera verdadero en un contexto booleano).

```javascript
expect(valor).toBeFalsy();
```

Esto verifica que el `valor` proporcionado sea uno de los valores "falsy" mencionados anteriormente.

##### Ejemplo con `false`

```javascript
test('false is falsy', () => {
  const value = false;
  expect(value).toBeFalsy();
});
```

##### Ejemplo con `0`

```javascript
test('0 is falsy', () => {
  const value = 0;
  expect(value).toBeFalsy();
});
```

##### Ejemplo con una cadena vacía

```javascript
test('empty string is falsy', () => {
  const value = '';
  expect(value).toBeFalsy();
});
```

##### Ejemplo con `null`

```javascript
test('null is falsy', () => {
  const value = null;
  expect(value).toBeFalsy();
});
```

##### Ejemplo con `undefined`

```javascript
test('undefined is falsy', () => {
  const value = undefined;
  expect(value).toBeFalsy();
});
```

##### Ejemplo con `NaN`

```javascript
test('NaN is falsy', () => {
  const value = NaN;
  expect(value).toBeFalsy();
});
```

##### Comparación con `toBeTruthy()`

- **`toBeFalsy()`**: Verifica que el valor sea "falsy" (uno de los valores mencionados arriba).
- **`toBeTruthy()`**: Verifica que el valor sea "truthy" (cualquier valor que no sea falsy, como objetos, arrays, números distintos de 0, cadenas no vacías, etc.).

Ejemplo con `toBeTruthy()`:

```javascript
test('truthy value', () => {
  const value = 'hello';
  expect(value).toBeTruthy(); // Pasa porque 'hello' es un valor truthy
});
```

#### `toStrictEqual()`

`toStrictEqual()` es un matcher en Jest que verifica que dos valores sean **profundamente iguales**, no solo en el contenido, sino también en su tipo y estructura exacta. A diferencia de `toEqual()`, que realiza una comparación profunda de los valores pero permite cierto tipo de flexibilidad (como permitir que dos objetos con el mismo contenido pero diferentes instancias sean considerados iguales), `toStrictEqual()` es más estricto en la comparación.

- Compara los valores de manera profunda.
- Verifica que las propiedades y los tipos de los objetos sean exactamente iguales.
- Asegura que las propiedades del objeto sean del mismo tipo (por ejemplo, `undefined` no será igual a `null`).

##### Comparación de objetos

```javascript
test('toStrictEqual compares objects', () => {
  const obj1 = { name: 'John', age: 30 };
  const obj2 = { name: 'John', age: 30 };
  expect(obj1).toStrictEqual(obj2);  // Pasa, los objetos son idénticos en contenido y tipo
});
```

##### Diferencia en tipo

```javascript
test('toStrictEqual checks type differences', () => {
  const obj1 = { value: null };
  const obj2 = { value: undefined };
  expect(obj1).not.toStrictEqual(obj2);  // Falla, porque `null` no es igual a `undefined`
});
```

##### Comparación de arrays

```javascript
test('toStrictEqual compares arrays', () => {
  const arr1 = [1, 2, 3];
  const arr2 = [1, 2, 3];
  expect(arr1).toStrictEqual(arr2);  // Pasa, los arrays son iguales
});
```

#### Comparación con `toEqual()`

- **`toEqual()`**: Realiza una comparación profunda, pero permite más flexibilidad en cuanto a la estructura interna de los objetos.
- **`toStrictEqual()`**: Más estricto, asegura que la estructura interna, los tipos y las propiedades sean exactamente iguales.

En nuestro proyecto...

`src > bases > 08-imp-exp.js`

```jsx
import { heroes } from "../data/heroes.js";

const getHeroById = (id) => {
  return heroes.find((value) => value.id === id);
};

const getHeroesByOwner = (owner) => {
  return heroes.filter((hero) => hero.owner === owner);
};

export { getHeroById, getHeroesByOwner };
```

`test > bases > 08-imp-exp.test.js`

```jsx
import {
  getHeroById,
  getHeroesByOwner,
} from "../../src/bases/08-imp-exp.js";
import { heroes } from "../../src/data/heroes.js";

describe("Test on 08-imp-exp", () => {
  test("getHeroById should return a hero by Id", () => {
    const id = 1;
    const hero = getHeroById(id);

    expect(hero).toEqual({
      id: 1,
      name: "Batman",
      owner: "DC",
    });
  });

  test("getHeroById should return undefinded if the id doesn't exist", () => {
    const id = 11;
    const hero = getHeroById(id);

    expect(hero).toBe(undefined);
    expect(hero).toBeFalsy();

    // false is considered a false value
    expect(false).toBeFalsy(); 👈👀
  });

  // Task
  test("getHeroesByOwner should return an array of DC heroes", () => {
    const owner = "DC";
    const newHeroes = getHeroesByOwner(owner);
    const dcHeroes = [
      {
        id: 1,
        name: "Batman",
        owner: "DC",
      },
      {
        id: 3,
        name: "Superman",
        owner: "DC",
      },
      {
        id: 4,
        name: "Flash",
        owner: "DC",
      },
    ];

    expect(newHeroes.length).toBe(3);
    expect(newHeroes).toStrictEqual(dcHeroes); 👈👀

    // Actual method
    expect(newHeroes).toEqual(
      heroes.filter((hero) => hero.owner === owner)
    );
  });
});
```

Creamos una carpeta data y añadimos el archivo `heroes.js`.

> En caso trabajaste con la extensión `.mjs` tener cuidado porque para las pruebas debe estar en `.js` de lo contrario fallará.

[**heroes.js - Gist**](https://gist.github.com/Klerith/4aeb99d31aedbc29ff4d54bbb77d2d7f)

### 5.12 Pruebas con tareas asíncronas

Por defecto Jest trabaja con pruebas síncronas o sea ejecuta el código en secuencia y cuando encuentra una promesa este la ejecuta, pero luego sigue ejecutando el código siguiente y al llegar al final recién arroja el error.

`src > bases > 09-promises.js`

```jsx
import { getHeroById } from "./08-imp-exp.js";

const getHeroByIdAsync = (id) => {
  const promise = new Promise((resolve, reject) => {
    setTimeout(() => {
      const data = getHeroById(id);

      data ? resolve(data) : reject("Id not found " + id);
    }, 1000);
  });

  return promise;
};

export { getHeroByIdAsync };
```

`src > bases > 09-promises.test.js`

```jsx
import { getHeroByIdAsync } from "../../src/bases/09-promises";

describe("Test on 09-promises", () => {
  test("09-promises should return a hero", (done) => {
    const id = 1;

    getHeroByIdAsync(id).then((hero) => {
      // expect(true).toBe(false);

      expect(hero).toEqual({
        id: 1,
        name: "Batman",
        owner: "DC",
      });

      done();
    });
  });

  test("09-promises should return an error if Hero doesn't exist", (done) => {
    const id = 12;

    getHeroByIdAsync(id)
      .then((hero) => {
        // expect(true).toBe(false);

        expect(hero).toBeFalsy();

        done();
      })
      .catch((error) => {
        expect(error).toBe(`Id not found ${id}`);

        done();
      });
  });
});
```

---
El uso de `done` en el contexto del ejemplo de prueba anterior se relaciona con la forma en que Jest maneja pruebas asíncronas. Vamos a desglosarlo en detalle.

#### `done` en Pruebas Asíncronas

La función de prueba visto en el ejemplo está probando un comportamiento asíncrono: una promesa que se resuelve o se rechaza. Cuando trabajas con código asíncrono en pruebas, Jest necesita saber cuándo la prueba ha terminado de ejecutarse. Por defecto, Jest no sabe cuándo debe considerar una prueba asíncrona como completada, por lo que proporciona el mecanismo `done` para manejar esto.

#### Detalle del Uso de `done`

1. **Declaración de la Prueba**: La función de prueba recibe `done` como un argumento. Esto indica a Jest que la prueba es asíncrona y que no debe finalizar la prueba hasta que se llame a `done`.
    
2. **Promesa Asíncrona**:
    
    - La función `getHeroByIdAsync(id)` devuelve una promesa.
    - **Caso de Éxito (`then`)**:
        - Si la promesa se resuelve, se llama al bloque `then` con el `hero` resultante.
        - `expect(hero).toBeFalsy()` verifica que `hero` es falsy.
        - Finalmente, `done()` se llama para indicar que la prueba ha terminado correctamente.
    - **Caso de Error (`catch`)**:
        - Si la promesa se rechaza, se llama al bloque `catch` con el `error` resultante.
        - `expect(error).toBe(\`Id not found ${id}`)` verifica que el error es el esperado.
        - Finalmente, `done()` se llama para indicar que la prueba ha terminado correctamente.
3. **Importancia de `done`**:
    
    - **Sin `done`**: Jest no sabría cuándo la prueba ha terminado. Puede que Jest termine la prueba antes de que la promesa se resuelva o se rechace, lo que llevaría a falsos negativos o pruebas incompletas.
    - **Con `done`**: Garantiza que Jest espera hasta que se llame a `done` antes de considerar la prueba como completada. Esto es crucial para asegurar que todas las verificaciones dentro de la promesa se ejecuten antes de finalizar la prueba.

#### Alternativa con `async`/`await`

En lugar de usar `done`, podrías escribir la prueba utilizando `async`/`await` para hacerla más limpia y evitar el manejo explícito de `done`. Aquí hay un ejemplo de cómo hacerlo:

```javascript
test("09-promises should return an error if Hero doesn't exist", async () => {
  const id = 12;

  try {
    const hero = await getHeroByIdAsync(id);
    expect(hero).toBeFalsy();
  } catch (error) {
    expect(error).toBe(`Id not found ${id}`);
  }
});
```

### 5.13 Pruebas con async-await

#### `whatwg-fetch`

`whatwg-fetch` es un paquete (polyfill) que implementa el estándar **Fetch API** en navegadores que no tienen soporte nativo para ello. La API `fetch` proporciona una forma más moderna y poderosa de realizar solicitudes de red, reemplazando a `XMLHttpRequest`.

Si tu proyecto necesita trabajar en navegadores antiguos que no soportan `fetch` (por ejemplo, Internet Explorer), entonces usar un polyfill como `whatwg-fetch` asegura que tu código funcione de manera consistente.

Instalamos:

```bash
yarn add -D whatwg-fetch
```

📌 **`-D`**: Es un atajo de `--dev`, que indica que la dependencia que estás agregando es para el entorno de desarrollo. Las dependencias de desarrollo son aquellas que solo se utilizan durante el proceso de desarrollo y no son necesarias en el entorno de producción. Se agregan al archivo `devDependencies` en el `package.json`.

Creamos el archivo `jest.config.cjs` y el archivo `jest.setup.js` todo en la raíz del proyecto.

`jest.config.cjs` 

```jsx
module.exports = {
  // TODO: jsdom,
  setupFiles: ["./jest.setup.js"],
};
```

📌 Para esta configuración podemos ir a [Jestjs.io](https://jestjs.io/blog/2020/05/05/jest-26) y buscar `jest.config`.

`jest.setup.js`

```js
## En caso de usar node en version menor a la 18
import "whatwg-fetch";
```

Para este ejemplo usaremos al APIKEY de GIPHY que generamos en clases pasadas.

`src > bases > 11-async-await.js`

```jsx
const getImage = async () => {
  try {
    const apiKey = "fEOnnEkSzI8fEOmMc09dfEOFt9fEO";
    const response = await fetch(
      `https://api.giphy.com/v1/gifs/random?api_key=${apiKey}`
    );
    const { data } = await response.json();
    const { url } = data.images.original;

    return url;
  } catch (error) {
    console.error(error);
    return "Image not found";
  }
};

// getImage();

export { getImage };
```

`src > bases > 11-async-await.test.js`

```jsx
import { getImage } from "../../src/bases/11-async-await";

describe("Test on 11-async-await", () => {
  test("getImage should return an image Url", async () => {
    const url = await getImage();

    expect(typeof url).toBe("string");
  });
});
```

### 5.14 Evaluar el Catch en el async-await

En nuestro ejemplo, estamos esperando que la respuesta sea una `url` que es un `string`. Para evaluar el `catch` solo podemos añadir el mensaje esperado dentro de nuestras pruebas.

`src > bases > 11-async-await.js`

```jsx
```

`src > bases > 11-async-await.test.js`

```jsx
import { getImagen } from "../../src/basic-tests/11-async-await";

describe("Test on 11-async-await", () => {
  test("getImagen should return an url", async () => {
    const url = await getImagen();
    // console.log(url);

    expect(typeof url).toBe("string");
    expect(url).toBe("Image not found"); 👈👀
  });
});
```

### 5.15 Pruebas sobre componentes de React

Usaremos **Testing Library / React Testing Library** para hacer pruebas sobre componentes propios de React, ya que es muy bueno para manejar el DOM virtual.

**Testing Library** está más enfocado en lo que sucede en la pantalla después de hacer alguna interacción, en cambio, **Jest** está más enfocado u orientado a hacer las **aserciones** de funciones que se necesitan evaluar.

📌 **Aserción:** Acción y efecto de afirmar o dar por cierto algo.

```bash
## Comando actual para React TL + DOM TL
yarn add --dev @testing-library/react @testing-library/dom

## También se encontra por separado
yarn add --dev @testing-library/dom

## Este comando es antiguo
yarn add --dev @testing-library/react
```

Para el siguiente ejemplo usaremos el componente `FirstApp.jsx`.

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { FirstTest } from "./FirstTest.jsx";

import "./index.css";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <FirstTest />
  </React.StrictMode>
);
```

- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro)
- [Testing React Apps: DOM Testing](https://jestjs.io/docs/tutorial-react#dom-testing)

### 5.16 Pruebas en FirstApp - Componentes de React

Para continuar con las pruebas debemos instalar lo siguiente, **cerrar todo y volver a iniciar los Test.**

```bash
yarn add -D jest-environment-jsdom
yarn add -D @babel/preset-react
```

1. **`yarn add -D jest-environment-jsdom`**

Este comando instala el paquete `jest-environment-jsdom` como una dependencia de desarrollo (`-D` o `--dev`). Veamos qué hace:

- **`jest-environment-jsdom`**: Este paquete proporciona un entorno de ejecución simulado para pruebas en Jest basado en **jsdom**. **jsdom** es una implementación de un navegador web en JavaScript, lo que permite simular el DOM (Document Object Model) de un navegador en un entorno de Node.js.
    
    Jest, por defecto, usa **jsdom** para simular el entorno de un navegador cuando ejecutas pruebas que interactúan con el DOM. Instalar `jest-environment-jsdom` garantiza que Jest pueda ejecutar pruebas de forma adecuada en un entorno simulado, incluso si no es la configuración predeterminada.
    

Si tu proyecto usa **Jest** para pruebas y necesitas un entorno de navegador (como si estuvieras probando componentes React o manipulando el DOM), **jsdom** es útil porque simula el DOM de un navegador, permitiendo hacer pruebas de manera eficiente sin tener un navegador real.
    
Esto es especialmente útil cuando trabajas con bibliotecas o aplicaciones que interactúan con el DOM, como React.

#### Ejemplo de uso:

```javascript
// En tu archivo de configuración de Jest (por ejemplo, jest.config.js)
module.exports = {
  testEnvironment: 'jsdom',
};
```

De forma predeterminada, Jest ya usa jsdom, pero si lo necesitas explícitamente o tienes una configuración personalizada, este paquete asegura que Jest se ejecute con el entorno adecuado.

2. **`yarn add -D @babel/preset-react`**

Este comando instala el paquete **`@babel/preset-react`** como dependencia de desarrollo. Vamos a explicarlo:

- **`@babel/preset-react`**: Este es un preset de Babel que permite que Babel transpile (o convierta) el código JSX y características específicas de React a código JavaScript que los navegadores puedan entender. JSX es una sintaxis que permite escribir código que se parece a HTML dentro de JavaScript, pero los navegadores no lo entienden directamente. Por eso, Babel necesita transpilar ese código para que sea compatible con los navegadores.

¿Por qué es necesario?

Si estás utilizando React en tu proyecto, los archivos que contienen JSX necesitan ser transformados en JavaScript puro que los navegadores puedan ejecutar. Este preset de Babel se asegura de que tu código JSX se transforme correctamente durante el proceso de compilación.

En tu archivo de configuración de Babel (por ejemplo, `babel.config.cjs`), agrega el preset:
    
```javascript
// Esto es un ejemplo, mas abajo encontraras la configuración que se usó en el curso
module.exports = {
  presets: [
    "@babel/preset-env", // Para convertir ES6+ a código compatible con navegadores antiguos
    "@babel/preset-react", // Para convertir JSX y características de React
  ],
};
```

Esto configurará Babel para que pueda entender y convertir JSX a código JavaScript estándar que los navegadores puedan ejecutar.

📌 Al hacer las instalaciones aparece un **Warning** relacionado con los `defaultProps` usados en clases anteriores. Lo que hice fue comentar esa parte del código y listo.

En nuestro proyecto...

`jest.config.cjs`

```jsx
module.exports = {
  testEnvironment: "jest-environment-jsdom",
  setupFiles: ["./jest.setup.js"],
};
```

`babel.config.cjs`

```jsx
module.exports = {
  presets: [
    ["@babel/preset-env", { targets: { esmodules: true } }],
    ["@babel/preset-react", { runtime: "automatic" }],
  ],
};
```

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { FirstTest } from "./FirstTest";  👈👀

import "./styles.css";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <FirstTest title="Ale Roses" subtitle={246} />  👈👀
  </React.StrictMode>
);
```

`src > FirstTest.jsx`

```jsx
import PropTypes from "prop-types";

const FirstTest = ({
  title = "No title",
  subTitle,
  name,
}) => {
  return (
    <>
      <h1 data-testid="test-title">{title}</h1>
      <p>{subTitle}</p>
      <p>{name}</p>
      {/* <code>{JSON.stringify(newMessage)}</code> */}
    </>
  );
};

// Comment on this part, it is obsolete.
FirstTest.propTypes = {  👈👀
  title: PropTypes.string.isRequired,
  subTitle: PropTypes.string,
};

// defaultProps throws an error
FirstTest.defaultProps = { 👈👀
  // title: "No title",
  subTitle: "New Text",
  name: "Ale Roses",
};

export { FirstTest };
```

`test > FirstTest.test.jsx`

```jsx
import { render } from "@testing-library/react";
import { FirstTest } from "../src/FirstTest.jsx";

describe("FirstApp tests", () => {
  test("It should match the snapshot", () => {
    // snapshot: instantánea captura

    render(<FirstTest title="Ale Roses" subtitle={246} />);
  });
});
```

En la actualidad aparece el siguiente **Warning** al tratar de usar `defaultProps`:

```bash
Warning: FirstTest: Support for defaultProps will be removed from function components in a future major release. Use JavaScript default parameters instead.
        at title (/home/ghost/Desktop/FH/x-test/src/FirstTest.jsx:4:3)
```

Para evitar esto solo agrega los `defaultProps` de la siguiente manera:

```jsx
import PropTypes from "prop-types";

const FirstTest = ({ 👈👀👇
  title = "No title",
  subTitle = "New Text",
  name = "Ale Roses",
}) => {
  return (
    <>
      <h1 data-testid="test-title">{title}</h1>
      <p>{subTitle}</p>
      <p>{name}</p>
    </>
  );
};

FirstTest.propTypes = {
  title: PropTypes.string.isRequired,
  subTitle: PropTypes.string,
};

export { FirstTest };
```

- [DOM Manipulation JEST](https://jestjs.io/docs/next/tutorial-jquery)
- [Babel Preset React](https://babeljs.io/docs/babel-preset-react)

### 5.17 Probar FirstApp: `toMatchSnapshot`

Veamos cómo funcionan `render`, `container` y `getByText` con `@testing-library/react`, así como los métodos de aserción `toBeTruthy()`, `toBe()` y `toContain()` de Jest.

#### @testing-library/react

##### `render`
La función `render` de `@testing-library/react` se utiliza para renderizar componentes React en el DOM para que puedan ser probados. Al usar `render`, obtienes un conjunto de utilidades para interactuar con el componente renderizado.

##### `container`
El objeto `container` es una propiedad devuelta por `render`. Representa el contenedor del DOM donde el componente fue renderizado. Puedes usarlo para acceder directamente al árbol del DOM y realizar manipulaciones o inspecciones.

##### `getByText`
`getByText` es una función proporcionada por `@testing-library/react` que permite seleccionar elementos en el DOM en función de su contenido de texto. Es útil para verificar que el contenido renderizado coincide con lo esperado.

##### Ejemplo de uso

```jsx
import React from 'react';
import { render } from '@testing-library/react';
import '@testing-library/jest-dom/extend-expect'; // Para tener los matchers extendidos como toBeInTheDocument
import MyComponent from './MyComponent';

test('renders learn react link', () => {
  const { container, getByText } = render(<MyComponent />);
  
  // Usando container
  const element = container.querySelector('.some-class');
  expect(element).not.toBe(null);

  // Usando getByText
  const linkElement = getByText(/learn react/i);
  expect(linkElement).toBeInTheDocument();
});
```

En este ejemplo, `render` se usa para renderizar `MyComponent`. Luego, se utilizan `container` y `getByText` para seleccionar elementos en el DOM y hacer aserciones sobre ellos.

#### Métodos de aserción

##### `toBeTruthy()`
`toBeTruthy()` verifica que el valor que se está probando es "verdadero" en el contexto booleano. Es decir, cualquier valor que no sea `null`, `undefined`, `false`, `0`, `NaN`, o una cadena vacía se considera "truthy".

```jsx
test('value is truthy', () => {
  const value = 'hello';
  expect(value).toBeTruthy(); // Pasa porque 'hello' es truthy
});
```

##### `toBe()`
`toBe()` verifica que el valor que se está probando es exactamente igual (usando `Object.is`) al valor esperado. Es útil para comparar valores primitivos y objetos inmutables.

```jsx
test('value is exactly equal to 4', () => {
  const value = 4;
  expect(value).toBe(4); // Pasa porque 4 es igual a 4
});
```

##### `toContain()`
`toContain()` verifica que una matriz o cadena contiene un elemento específico.

Para matrices:

```jsx
test('array contains the value', () => {
  const array = [1, 2, 3];
  expect(array).toContain(2); // Pasa porque 2 está en la matriz
});
```

Para cadenas:

```jsx
test('string contains the substring', () => {
  const string = 'hello world';
  expect(string).toContain('world'); // Pasa porque 'world' está en la cadena
});
```

#### Entonces…

- **`render`**: Renderiza un componente React y devuelve utilidades para interactuar con él.
- **`container`**: Es el contenedor del DOM donde el componente fue renderizado.
- **`getByText`**: Selecciona elementos del DOM en función de su contenido de texto.
- **`toBeTruthy()`**: Verifica que el valor es "verdadero" en contexto booleano.
- **`toBe()`**: Verifica que el valor es exactamente igual al esperado.
- **`toContain()`**: Verifica que una matriz o cadena contiene un elemento específico.

#### `toMatchSnapshot()`

`toMatchSnapshot()` es una función de Jest que se utiliza para realizar pruebas de instantáneas (snapshots). Las pruebas de instantáneas son una forma de guardar el estado de una salida específica (por ejemplo, el resultado renderizado de un componente React) en un archivo de instantánea y luego compararlo con futuras ejecuciones de pruebas para detectar cambios inesperados.

1. **Captura Inicial**: La primera vez que ejecutas una prueba con `toMatchSnapshot()`, Jest guarda la salida de la prueba en un archivo de instantánea. Este archivo se guarda en una carpeta `__snapshots__` dentro de tu estructura de pruebas.
    
2. **Comparación**: En ejecuciones posteriores de la prueba, Jest compara la salida actual con la instantánea guardada. Si hay diferencias, la prueba falla, indicando que algo ha cambiado.
    
3. **Actualización**: Si el cambio en la salida es intencional (por ejemplo, después de actualizar un componente), puedes actualizar la instantánea para reflejar el nuevo estado esperado.

##### Ejemplo de uso

Supongamos que tienes un componente React que deseas probar.

```jsx
import React from 'react';
import renderer from 'react-test-renderer';
import MyComponent from './MyComponent';

test('MyComponent matches snapshot', () => {
  const tree = renderer.create(<MyComponent />).toJSON();
  expect(tree).toMatchSnapshot();
});
```

En este ejemplo:

1. **Renderizado**: El componente `MyComponent` se renderiza utilizando `react-test-renderer`.
2. **Conversión a JSON**: La salida renderizada se convierte a una estructura de datos JSON.
3. **Verificación de la instantánea**: `expect(tree).toMatchSnapshot()` compara la estructura renderizada con la instantánea guardada.

##### Ventajas de las pruebas de instantáneas

- **Detección de cambios no intencionados**: Las pruebas de instantáneas son útiles para detectar cambios accidentales en la salida de tus componentes. Si un cambio en el código provoca una diferencia en la salida, la prueba fallará.
    
- **Documentación visual**: Las instantáneas actúan como una forma de documentación visual, mostrando cómo se espera que luzca la salida en un momento dado.
    
- **Fácil de actualizar**: Si haces cambios intencionales en tu componente y la instantánea necesita ser actualizada, puedes actualizar fácilmente las instantáneas usando el comando de Jest `--updateSnapshot` o `-u`.

##### Cómo actualizar instantáneas

Si has cambiado intencionalmente la salida de un componente y necesitas actualizar la instantánea, puedes ejecutar:

```bash
jest --updateSnapshot
```

Esto actualizará las instantáneas para que reflejen el nuevo estado esperado.

📌 Al usar `toMatchSnapshot` se crea una carpeta llamada `__snapshots__` con las instantáneas o capturas del componente asociado.

Esto permite verificar que el código está tal cual como lo creamos y que no se eliminaron líneas. Si eliminas algunas, verás que esto se refleja en la consola.

En caso el cambio hecho en el código sea intencional, puedes presionar `u` en la consola para actualizar los cambios en el `__snapshots__`.

La estructura es la siguiente:

```bash
├── src
│   ├── App.jsx
│   ├── basic-tests
│   │   ├── 02-template-string.js
│   │   ├── 05-funciones.js
│   │   ├── 06-deses-obj.js
│   │   ├── 07-deses-arr.js
│   │   ├── 08-imp-exp.js
│   │   ├── 09-promesas.js
│   │   └── 11-async-await.js
│   ├── CounterApp.jsx
│   ├── data
│   │   └── heroes.js
│   ├── FirstApp.jsx 🔥
│   ├── main.jsx
│   └── styles.css
├── tests
│   ├── basic-tests
│   │   ├── 02-template-string.test.js
│   │   ├── 05-functions.test.js
│   │   ├── 07-deses-arr.test.js
│   │   ├── 08-imp-exp.test.js
│   │   ├── 09-promises.test.js
│   │   └── 11-async-await.test.js
│   ├── demo.test.js
│   ├── FirstApp.test.jsx 🔥
│   └── __snapshots__ 👈👀👇
│       └── FirstApp.test.jsx.snap 🔥
├── vite.config.js
└── yarn.lock
```

`test > FirstTest.test.jsx`

```jsx
import { render } from "@testing-library/react";
import { FirstTest } from "../src/FirstTest.jsx";

describe("FirstApp tests", () => {
  test("It should match the snapshot", () => {
    // snapshot: instantánea, captura

    const message = "Hi i'm Ale Roses";
    const { container } = render(
      <FirstTest title={message} />
    );

    expect(container).toMatchSnapshot(); 👈👀
  });

  test("It should display the title in an h1.", () => {
    const message = "Hi i'm Ale Roses";
    const { container, getByText } = render(
      <FirstTest title={message} />
    );

    expect(getByText(message)).toBeTruthy();

    const h1 = container.querySelector("h1");

    expect(h1.innerHTML).toBe(message);
    
    // Work with spaces at the beginning and at the end.
    expect(h1.innerHTML).toContain(message); 👈👀
  });
});
```

### 5.18 getByTestId y otras props

#### `data-testid`

`data-testid` es un atributo HTML que se utiliza para identificar elementos del DOM en las pruebas. Es una convención comúnmente utilizada para marcar elementos de manera que sean fáciles de seleccionar durante las pruebas sin afectar el comportamiento o el estilo del componente.

Supongamos que tienes un componente React:

```jsx
const MyComponent = () => (
  <div>
    <button data-testid="submit-button">Submit</button>
  </div>
);

export default MyComponent;
```

En este ejemplo, el botón tiene un atributo `data-testid` con el valor `"submit-button"`, lo que lo hace fácilmente seleccionable en las pruebas.

#### `getByTestId`

`getByTestId` es una función proporcionada por Testing Library que permite seleccionar un elemento del DOM utilizando su atributo `data-testid`. Es útil cuando quieres seleccionar un elemento específico que has marcado con `data-testid`.

```javascript
import { render, screen } from '@testing-library/react';
import MyComponent from './MyComponent';

test('renders submit button', () => {
  render(<MyComponent />);
  const button = screen.getByTestId('submit-button');
  expect(button).toBeInTheDocument();
});
```

En este ejemplo, `screen.getByTestId('submit-button')` selecciona el botón que hemos marcado con `data-testid="submit-button"` y luego verificamos que el botón está presente en el documento con `expect(button).toBeInTheDocument()`.

#### `getByText` y `getAllByText`

- **`getByText`**: Selecciona el primer elemento que contiene el texto especificado.
- **`getAllByText`**: Selecciona todos los elementos que contienen el texto especificado y devuelve un array de nodos.

Estas funciones son útiles para seleccionar elementos basados en el texto visible en la pantalla, lo cual es una forma natural de interactuar con los elementos del DOM durante las pruebas.

##### Ejemplo de uso de `getByText`

```javascript
import { render, screen } from '@testing-library/react';
import MyComponent from './MyComponent';

test('renders submit button', () => {
  render(<MyComponent />);
  const button = screen.getByText('Submit');
  expect(button).toBeInTheDocument();
});
```

En este ejemplo, `screen.getByText('Submit')` selecciona el botón que contiene el texto "Submit".

##### Ejemplo de uso de `getAllByText`

Supongamos que tienes varios elementos con el mismo texto:

```jsx
const MyComponent = () => (
  <div>
    <p>Item 1</p>
    <p>Item 1</p>
    <p>Item 2</p>
  </div>
);

export default MyComponent;
```

En este caso, puedes seleccionar todos los elementos con el texto "Item 1":

```javascript
import { render, screen } from '@testing-library/react';
import MyComponent from './MyComponent';

test('renders multiple items with the same text', () => {
  render(<MyComponent />);
  const items = screen.getAllByText('Item 1');
  expect(items.length).toBe(2);
});
```

En este ejemplo, `screen.getAllByText('Item 1')` selecciona todos los elementos `<p>` que contienen el texto "Item 1" y luego verificamos que hay dos elementos con ese texto.

En nuestro proyecto...

📌 Si están en desarrollo se recomienda no hacer pruebas de `snapshot`.

`src > FirstTest.jsx`

```jsx
import PropTypes from "prop-types";

const FirstTest = ({
  title = "No title",
  subTitle = "New Text",
  name = "Ale Roses",
}) => {
  return (
    <>
      <h1 🔥data-testid="test-title" 👈👀 >{title}</h1>
      <p>{subTitle}</p> 👈👀
      <p>{subTitle}</p> 👈👀
      <p>{name}</p>
    </>
  );
};

FirstTest.propTypes = {
  title: PropTypes.string.isRequired,
  subTitle: PropTypes.string,
};

export { FirstTest };
```

`test > FirstTest.test.jsx`

```jsx
import { render } from "@testing-library/react";
import { FirstTest } from "../src/FirstTest.jsx";

describe("FirstTest tests", () => {
  test("It should display the title in an h1.", () => {
    const message = "Hi i'm Ale Roses";

    const { container, getByText, getByTestId 👈👀 } = render(
      <FirstTest title={message} />
    );

    expect(getByText(message)).toBeTruthy();

    // toBeTruthy: Verifica que exista
    expect(getByTestId("test-title")).toBeTruthy();
    expect(getByTestId("test-title").innerHTML).toBe(
      message
    );

    expect(getByTestId("test-title").innerHTML).toContain(
      message
    );
  });

  test("should show the subtitle send by props", () => {
    const message = "Hi i'm Ale Roses";
    const subTitle = "I'm a subtitle";

    const { getByText, getAllByText 👈👀 } = render(
      <FirstTest title={message} subTitle={subTitle} />
    );

    // expect(getByText(subTitle)).toBeTruthy();

    // En caso de haber mas de un elemento a evaluar usar getAllByText() que devuelve un array
    expect(getAllByText(subTitle)).toBeTruthy();
    expect(getAllByText(subTitle).length).toBe(2);
  });
});
```

### 5.19 Screen - Testing Library

La función `screen` es una parte esencial de `@testing-library/react` y facilita la selección de elementos del DOM cuando se realizan pruebas. Veamos cómo funciona y cómo se utiliza en los tests.

`screen` es una utilidad global que permite acceder a los métodos de consulta de manera más sencilla y sin necesidad de desestructurar la respuesta de la función `render`.

En lugar de desestructurar por ejemplo `getByText` desde el resultado de `render`, puedes usar `screen` directamente para acceder a este método.

#### Sin `screen`:

```jsx
import { render } from "@testing-library/react";
import MyComponent from "./MyComponent";

test("renders learn react link", () => {
  const { getByText } = render(<MyComponent />);
  const linkElement = getByText(/learn react/i);
  
  expect(linkElement).toBeInTheDocument();
});
```

#### Con `screen`:

```jsx
import { render, screen } from "@testing-library/react";
import MyComponent from "./MyComponent";

test("renders learn react link", () => {
  render(<MyComponent />);
  const linkElement = screen.getByText(/learn react/i);
  expect(linkElement).toBeInTheDocument();
});
```

#### Métodos comunes de `screen`

`screen` proporciona varios métodos de consulta que puedes usar para seleccionar elementos en el DOM renderizado. Algunos de los más comunes son:

- **`screen.getByText(text)`**: Busca un elemento por su contenido de texto.
- **`screen.getByRole(role)`**: Busca un elemento por su rol (como `button`, `heading`, etc.).
- **`screen.getByLabelText(label)`**: Busca un elemento asociado a una etiqueta específica.
- **`screen.getByPlaceholderText(placeholder)`**: Busca un elemento por su texto de marcador de posición.
- **`screen.getByAltText(alt)`**: Busca un elemento por su texto alternativo.
- **`screen.debug()`**: Imprime el contenido del DOM en el momento en que se llama. Esto es útil para entender mejor la estructura del componente que estás probando.

#### Ejemplo avanzado

Supongamos que tienes un componente de formulario y quieres probar varios aspectos del mismo.

```jsx
import React from "react";
import { render, screen } from "@testing-library/react";
import "@testing-library/jest-dom/extend-expect"; // para los matchers extendidos
import FormComponent from "./FormComponent";

test("renders form elements correctly", () => {
  render(<FormComponent />);

  // Verifica que el título del formulario esté presente
  const heading = screen.getByRole("heading", {
    name: /form title/i,
  });
  expect(heading).toBeInTheDocument();

  // Verifica que el input con el placeholder 'Username' esté presente
  const usernameInput =
    screen.getByPlaceholderText("Username");
  expect(usernameInput).toBeInTheDocument();

  // Verifica que el botón 'Submit' esté presente
  const submitButton = screen.getByRole("button", {
    name: /submit/i,
  });
  expect(submitButton).toBeInTheDocument();

  // Verifica que el label del input 'Password' esté presente
  const passwordLabel = screen.getByLabelText("Password");
  expect(passwordLabel).toBeInTheDocument();
});
```

Ahora en nuestro proyecto.

`test > FirstTest2.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { FirstTest } from "../src/FirstTest.jsx";

describe("FirstApp tests", () => {
  const message = "Hi i'm Ale Roses";
  const subTitle = "I'm a subtitle";

  test("It should match the snapshot", () => {
    // snapshot: instantánea, captura

    const { container } = render(
      <FirstTest title={message} />
    );

    expect(container).toMatchSnapshot();
  });

  test("It should display the message 'Hi, i'm Ale Roses'", () => {
    // Imprime el estado inicial del DOM
    // screen.debug()
    render(<FirstTest title={message} />);

    // Que no exista: not
    // expect(screen.getByText(title)).not.toBeTruthy();
    expect(screen.getByText(message)).toBeTruthy();
    // Imprime el estado del DOM después de la acción
    // screen.debug();
  });

  test("It should display the title in an h1", () => {
    render(<FirstTest title={message} />);
    expect(
      screen.getByRole("heading", { level: 1 }).innerHTML
    ).toContain(message);
  });

  test("It should display the subtitle sent by a prop", () => {
    render(
      <FirstTest title={message} subTitle={subTitle} />
    );

    // En caso de haber mas de un elemento a evaluar usar getAllByText() que devuelve un array
    expect(screen.getAllByText(subTitle).length).toBe(2);
  });
});
```

### 5.20 Pruebas básicas del CounterApp

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { CounterApp } from "./CounterApp.jsx";

import "./styles.css";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <CounterApp value={0} />
  </React.StrictMode>
);
```

`src > CounterApp.jsx`

```jsx
import React, { useState } from "react";
import PropTypes from "prop-types";

const CounterApp = ({ value }) => {
  const [counter, setCounter] = useState(value);

  const handleAdd = () => {
    // setCounter(counter + 1);
    setCounter((c) => c + 1);
  };

  const handleRest = () => {
    setCounter((c) => c - 1);
  };

  const handleReset = () => {
    setCounter(value);
  };

  return (
    <>
      <h1>Counter App</h1>

      <button onClick={handleAdd}>+1</button>
      <button onClick={handleRest}>-1</button>
      <button aria-label="btn-reset" onClick={handleReset}>
        Reset
      </button>
      <h2>{counter}</h2>
    </>
  );
};

CounterApp.propTypes = {
  value: PropTypes.number.isRequired,
};

export { CounterApp };
```

`tests > CounterApp.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { CounterApp } from "../src/CounterApp";

describe("CounterApp Testing", () => {
  const value = 0;

  test("It should match the snapshot", () => {
    const { container } = render(
      <CounterApp value={value} />
    );
    expect(CounterApp).toMatchSnapshot();
  });

  test("It should display an initial value of 0", () => {
    render(<CounterApp value={value} />);

    expect(screen.getByText(value)).toBeTruthy();
    expect(
      screen.getByRole("heading", { level: 2 }).innerHTML
    ).toContain("0");
  });
});
```

### 5.21 Simular eventos - Click

`fireEvent` se usa para disparar eventos del DOM, como clics, cambios de entrada, envíos de formularios, entre otros. Simula la interacción del usuario con el componente, permitiéndote probar cómo responde tu aplicación a estas interacciones.

Para utilizar `fireEvent`, seleccionas un elemento del DOM usando `screen` o cualquier método de consulta proporcionado por `@testing-library/react`, y luego disparas un evento sobre ese elemento.

#### Ejemplo básico

Supongamos que tienes un botón que, al ser clicado, cambia el estado de un mensaje:

```jsx
import React, { useState } from 'react';

function ToggleButton() {
  const [visible, setVisible] = useState(false);

  return (
    <div>
      <button onClick={() => setVisible(!visible)}>Toggle</button>
      {visible && <p>The message is now visible</p>}
    </div>
  );
}

export default ToggleButton;
```

Puedes escribir una prueba para este componente utilizando `fireEvent` de la siguiente manera:

```jsx
import { render, screen, fireEvent } from '@testing-library/react';
import ToggleButton from './ToggleButton';

test('toggles message visibility on button click', () => {
  render(<ToggleButton />);
  
  const button = screen.getByRole('button', { name: /toggle/i });
  fireEvent.click(button);
  
  expect(screen.getByText(/the message is now visible/i)).toBeInTheDocument();
  
  fireEvent.click(button);
  
  expect(screen.queryByText(/the message is now visible/i)).not.toBeInTheDocument();
});
```

#### Tipos de eventos comunes

##### `fireEvent.click(element)`

Simula un clic en el elemento especificado.

```jsx
fireEvent.click(button);
```

##### `fireEvent.change(element, { target: { value: 'new value' } })`

Simula un cambio de valor en un elemento de entrada.

```jsx
const input = screen.getByLabelText(/username/i);
fireEvent.change(input, { target: { value: 'new username' } });
expect(input.value).toBe('new username');
```

##### `fireEvent.submit(form)`

Simula el envío de un formulario.

```jsx
const form = screen.getByRole('form');
fireEvent.submit(form);
```

#### Otros eventos disponibles

- `fireEvent.focus(element)`
- `fireEvent.blur(element)`
- `fireEvent.mouseOver(element)`
- `fireEvent.keyDown(element, { key: 'Enter', code: 'Enter' })`

#### Ejemplo avanzado con varios eventos

Supongamos que tienes un formulario con un campo de texto y un botón de envío. Quieres probar que al escribir en el campo y hacer clic en el botón, se muestra un mensaje de éxito:

```jsx
import React, { useState } from 'react';

function Form() {
  const [value, setValue] = useState('');
  const [submitted, setSubmitted] = useState(false);

  const handleSubmit = (event) => {
    event.preventDefault();
    setSubmitted(true);
  };

  return (
    <div>
      <form onSubmit={handleSubmit}>
        <label htmlFor="input">Enter text:</label>
        <input
          id="input"
          type="text"
          value={value}
          onChange={(e) => setValue(e.target.value)}
        />
        <button type="submit">Submit</button>
      </form>
      {submitted && <p>Form submitted successfully</p>}
    </div>
  );
}

export default Form;
```

La prueba para este formulario podría verse así:

```jsx
import { render, screen, fireEvent } from '@testing-library/react';
import Form from './Form';

test('submits form and shows success message', () => {
  render(<Form />);
  
  const input = screen.getByLabelText(/enter text/i);
  const button = screen.getByRole('button', { name: /submit/i });
  
  fireEvent.change(input, { target: { value: 'Hello World' } });
  expect(input.value).toBe('Hello World');
  
  fireEvent.click(button);
  
  expect(screen.getByText(/form submitted successfully/i)).toBeInTheDocument();
});
```

Ahora veamos como se usa en nuestro proyecto:

`tests > CounterApp.test.jsx`

```jsx
import {
  fireEvent, 👈👀
  render,
  screen,
} from "@testing-library/react";
import { CounterApp } from "../src/CounterApp";

describe("Test in the CounterApp", () => {
  const value = 0;

  test("Should match the snapshott", () => {
    const { container } = render(
      <CounterApp value={value} />
    );
    expect(CounterApp).toMatchSnapshot();
  });

  test("should show the inicial value of 0", () => {
    render(<CounterApp value={value} />);

    expect(screen.getByText(value)).toBeTruthy();
    expect(
      screen.getByRole("heading", { level: 2 }).innerHTML
    ).toContain("0");
  });

  test("Should increase with the +1 button", () => {
    render(<CounterApp value={value} />);
    fireEvent.click(screen.getByText("+1")); 👈👀

    expect(screen.getByText("1")).toBeTruthy();
  });

  // test("Should decrease with the -1 button", () => {
  //   render(<CounterApp value={value} />);
  //   fireEvent.click(screen.getByText("-1"));

  //   // screen.debug();
  //   expect(screen.getByText("-1")).toBeTruthy();
  // });

  test("The reset button should work", () => {
    render(<CounterApp value={value} />);
    fireEvent.click(screen.getByText("+1"));
    fireEvent.click(screen.getByText("+1"));
    fireEvent.click(screen.getByText("+1"));

    // Returns the value to 0
    // fireEvent.click(screen.getByText("Reset"));
    fireEvent.click(
      screen.getByRole("button", { name: "btn-reset" })
    );

    // screen.debug();
    expect(screen.getByText(value)).toBeTruthy();
  });
});
```

### 5.22 Código fuente de la sección

Aquí les dejo el código fuente de la sección por si lo llegan a necesitar y comparar contra el suyo:

- [**Github - Fin sección 5**](https://github.com/Klerith/react-vite-counter-app/tree/fin-seccion-5)
- [Apuntes](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/devTalles/react-hooks-mern.md)

## 🟣 6. GifExpertApp - Aplicación

### 6.1 Introducción a la sección

### 6.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Custom Hooks
- Fetch hacia un API
- Comunicación entre componentes
- Clases de CSS
- Animaciones
- Enviar métodos como argumentos
- Crear listados
- keys
- Giphy

Esta es una aplicación pequeña pero muy ilustrativa que explica cómo utilizar React + customHooks para poder resolver necesidades en específico que podremos re-utilizar después.

### 6.3 Resultado al final de la sección

![Project 01](https://i.postimg.cc/zD2R0NnK/1-project.png)

### 6.4 Inicio de proyecto - GifExpertApp

```bash
yarn create vite
	04-gif-expert-app
	react
	JavaScript
cd 04-gif-expert-app

# Instalar Módulos de Node:
yarn install
# También puedes usar:
yarn

code-insiders .

# Corremos la app
yarn dev
```

Limpiamos el contenido de la carpeta `src`, solo dejamos el archivo `main.jsx`.

En esta clase dejamos la siguiente estructura:

```bash
.
├── index.html
├── node_modules
├── package.json
├── public
│   └── vite.svg
├── README.md
├── src 👈👀👇
│   ├── GifExpertApp.jsx
│   └── main.jsx
├── vite.config.js
└── yarn.lock

3 directories, 5 files
```

También debemos tener ya creada una API KEY en [GiphY Devs](https://developers.giphy.com/)

📌 Al iniciar el proyecto, el archivo `main.jsx` ya no importa el `ReactDOM from "react-dom/client"`, directamente importa el `createRoot`

### 6.5 GifExpertApp - Component

`src > main.jsx`

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import { GifExpertApp } from "./GifExpertApp";

import "./styles.css"; 👈👀

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <GifExpertApp />
  </React.StrictMode>
);
```

`src > GifExpertApp.jsx`

```jsx
export const GifExpertApp = () => {
  return (
    <>
      <h1>GifExpertApp</h1>
    </>
  );
};
```

Los estilos puedes agregarlos según tu criterio o también puedes usar los que se usaron para crear esta aplicación. Solo asegúrate de crearlos dentro de la carpeta `src`.

#### Estructura de Archivos

##### Agrupación por funcionalidades o rutas

Una forma común de estructurar proyectos es ubicar CSS, JS y tests juntos dentro de carpetas agrupadas por funcionalidad o ruta.

```bash
.
├── common
│   ├── Avatar.js
│   ├── Avatar.css
│   ├── APIUtils.js
│   └── APIUtils.test.js
├── feed
│   ├── index.js
│   ├── Feed.js
│   ├── Feed.css
│   ├── FeedStory.js
│   ├── FeedStory.test.js
│   └── FeedAPI.js
└── profile
    ├── index.js
    ├── Profile.js
    ├── ProfileHeader.js
    ├── ProfileHeader.css
    └── ProfileAPI.js
```

La definición de una “funcionalidad” no es universal, y depende de ti elegir la granularidad. Si no puedes pensar en una lista de carpetas de nivel superior, puede preguntarle a los usuarios de tu producto cuáles son las partes principales y usar su modelo mental como estructura.

##### Agrupando por tipo de archivo

Otra forma popular de estructurar proyectos es agrupar archivos similares, por ejemplo:

```bash
.
├── api
│   ├── APIUtils.js
│   ├── APIUtils.test.js
│   ├── ProfileAPI.js
│   └── UserAPI.js
├── components
│   ├── Avatar.js
│   ├── Avatar.css
│   ├── Feed.js
│   ├── Feed.css
│   ├── FeedStory.js
│   ├── FeedStory.test.js
│   ├── Profile.js
│   ├── ProfileHeader.js
│   └── ProfileHeader.css
```

Algunas personas también prefieren ir más lejos y separar los componentes en diferentes carpetas dependiendo de su función en la aplicación. Por ejemplo, [Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/) es una metodología de diseño basada en este principio. Recuerda que a menudo es más productivo tratar estas metodologías como ejemplos útiles en lugar de reglas estrictas a seguir.

##### Evita el exceso de anidación

Hay muchos puntos débiles asociados con el anidamiento profundo de directorios en proyectos JavaScript. Se vuelve más difícil escribir importaciones relativas entre ellas o actualizar esas importaciones cuando se mueven los archivos. A menos que tengas una razón muy convincente para usar una estructura de carpetas profunda, considera limitarte a **un máximo de tres o cuatro carpetas anidadas** dentro de un solo proyecto. Por supuesto, esto es solo una recomendación y puede que no sea relevante para tu proyecto.

##### No lo pienses demasiado

Si estás comenzando un proyecto, [no gastes más de cinco minutos](https://es.wikipedia.org/wiki/Par%C3%A1lisis_del_an%C3%A1lisis) en elegir una estructura de archivos. ¡Elige cualquiera de los enfoques anteriores (o crea uno propio) y comienza a escribir código! Probablemente querrás volver a pensarlo de todos modos después de haber escrito código real.

Si te sientes completamente atascado, comienza por mantener todos los archivos en una sola carpeta. Eventualmente crecerá lo suficiente como para que quieras separar algunos archivos del resto. Para ese momento, tendrás suficiente conocimientos para saber qué archivos editas juntos con mayor frecuencia. En general, es una buena idea mantener los archivos que a menudo cambian juntos cerca unos de otros. Este principio se llama “colocación”.

A medida que los proyectos crecen, frecuentemente utilizan una combinación de los dos enfoques anteriores en la práctica. Así que elegir el “correcto” al principio no es muy importante.

#### 🔥 Estructurando proyectos y nombrando componentes en React

React es una biblioteca que no impone reglas sobre cómo organizar y estructurar tus proyectos, lo que permite libertad para probar diferentes enfoques y adaptarlos según convenga. Sin embargo, esto puede causar confusión para desarrolladores que empiezan con React.

##### Estructura de Carpetas

Cuando se utiliza `create-react-app`, se genera una estructura básica con archivos y carpetas en la raíz como `.gitignore`, `package.json`, `README.md`, y `yarn.lock`. También se crean las carpetas `public` y `src`, donde `src` contiene el código fuente.

```bash
.
├── public
├── src
│   ├── App.css
│   ├── App.js
│   ├── App.test.js
│   ├── index.css
│   ├── index.js
│   ├── logo.svg
│   └── registerServiceWorker.js
├── .gitignore
├── package.json
├── README.md
└── yarn.lock
```

##### Contenedores y Componentes

A menudo se separan los componentes en `containers` y `components` dentro de `src`, pero este enfoque tiene problemas:

```
src
├─ components  
└─ containers
```

- Reglas subjetivas: No siempre está claro qué es un "Container" y qué es un "Presentational Component".
- No considera el dinamismo: Los componentes pueden cambiar de tipo a lo largo del proyecto, causando movimientos constantes entre carpetas.
- Duplicidad de nombres: Puede haber componentes con el mismo nombre en diferentes carpetas.
- Pérdida de productividad: Navegación constante entre carpetas distantes.

Para resolver esto, se recomienda no separar componentes por "presentational" vs "container" sino agruparlos por módulos o características dentro de la carpeta `components`.

[Presentational and Container Components](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0).

##### Separación y Agrupación del Código

Dentro de `components`, se agrupan los archivos por módulo o característica. Por ejemplo, un módulo `User` tendría una estructura como:

```
src
└─ components
   └─ User
      ├─ Form.jsx
      └─ List.jsx
```

Si un componente tiene múltiples archivos, se agrupan en una carpeta con el mismo nombre del componente. 

```
src
└─ components
   └─ User
     ├─ Form
     │  ├─ Form.jsx
     │  └─ Form.css
     └─ List.jsx
```

Los archivos de prueba se colocan junto al archivo que están probando y se nombran como `Form.spec.jsx`.

##### Componentes de UI

Los componentes genéricos se colocan en una carpeta `UI` dentro de `components`. Estos son componentes reutilizables sin lógica de negocio específica, como botones, inputs, etc.

##### Nombrando Componentes

Los nombres de los componentes deben ser claros y únicos en la aplicación. Se sigue un patrón de nomenclatura basado en la ruta relativa del componente. Por ejemplo, un componente en `components/User/List.jsx` se llamaría `UserList`.

> El nombre de un componente es muy útil cuando necesitamos depurar usando herramientas como React Dev Tools, y cuando ocurren errores de ejecución en la aplicación. El error siempre viene con el nombre del componente donde ocurrió.

Cuando el archivo está dentro de una carpeta con el mismo nombre, no necesitamos repetir el nombre. Dicho esto, `components/User/Form/Form.jsx`, se nombraría como `UserForm` y no como `UserFormForm`.

##### Pantallas

Las pantallas son las vistas de la aplicación y se mantienen en una carpeta separada en la raíz de `src`, agrupadas según la definición de rutas. Por ejemplo:

```
src
├── components
└── screens
    └── User
        ├── Form.jsx
        └── List.jsx
```

El archivo `Root.jsx` en `screens` define todas las rutas de la aplicación y se ve algo así:

```jsx
import React, { Component } from "react";
import { Router } from "react-router";
import { Redirect, Route, Switch } from "react-router-dom";
import ScreensUserForm from "./User/Form";
import ScreensUserList from "./User/List";

const ScreensRoot = () => (
  <Router>
    <Switch>
      <Route
        path="/user/list"
        component={ScreensUserList}
      />
      <Route
        path="/user/create"
        component={ScreensUserForm}
      />
    </Switch>
  </Router>
);

export default ScreensRoot;
```

Observa que ponemos todas las pantallas dentro de una carpeta con el mismo nombre de la ruta, usuario/ -> Usuario/. Intenta mantener una carpeta para cada ruta padre, y agrupa las sub-rutas en ella. En este caso, creamos la carpeta Usuario y guardamos en ella las pantallas Lista y Pantalla Formulario. Este patrón te ayudará a encontrar fácilmente qué pantalla está renderizando cada ruta, simplemente echando un vistazo a la url.

Una misma pantalla puede ser utilizada para renderizar dos rutas diferentes, como hicimos anteriormente con las rutas para crear y editar un usuario.

Puede notar que todos los componentes contienen Screen como prefijo en su nombre. Cuando el componente se encuentra fuera de la carpeta `components`, debemos nombrarlo de acuerdo a su ruta relativa a la carpeta `src`. Un componente ubicado en `src/screens/User/List.jsx` debería llamarse `ScreensUserList`.

Con el `Root.jsx` creado, nuestra estructura sería la siguiente:

```
src
├── components
└── screens
    ├── User
    │   ├── Form.jsx
    │   └── List.jsx
    └── Root.jsx 
```

No olvides importar `Root.jsx` dentro de `index.js` para que sea el componente raíz de la aplicación.

Finalmente, nuestra aplicación se estructuraría así:

```
src
├── components
│   ├── UI
│   └── User
│        ├── Form
│        │   ├── Form.css
│        │   └── Form.jsx
|        └── List.jsx
└── screens
    ├── User
    │   ├── Form.jsx
    │   └── List.jsx
    └── Root.jsx
```

##### Conclusiones

- Los componentes de presentación y contenedores se mantienen en `src/components`.
- Los componentes se agrupan por módulo/característica.
- Los componentes genéricos se colocan en `src/components/UI`.
- Las pantallas se mantienen simples, con mínima estructura y código.
- Las pantallas se agrupan según la definición de rutas.
- Los componentes se nombran según su ruta relativa a `components` o `src`.

Estas recomendaciones buscan mejorar la organización y estructura del proyecto en React, facilitando la búsqueda de archivos y evitando confusiones.

- [**Reactjs.org - Estructura de directorios**](https://es.reactjs.org/docs/faq-structure.html)
- [Structuring projects and naming components in React](https://hackernoon.com/structuring-projects-and-naming-components-in-react-1261b6e18d76)
- [**Estructura, nombres de folders y componentes en React - Hackernoon.com**](https://hackernoon.com/structuring-projects-and-naming-components-in-react-1261b6e18d76)
- [**Estilos GifExpertApp**](https://gist.github.com/Klerith/e4fca6ac127ccb9abd1e8ad77fcd52f1)

### 6.6 Creando una lista de categorías

`src > GifExpertApp.jsx`

```jsx
import { useState } from "react";

export const GifExpertApp = () => {
  const [categories, setCategories] = useState([
    "One Punch",
    "Dragon Ball",
  ]);

  return (
    <>
      <h1>GifExpertApp</h1>

      <ol>
        {categories.map((item, id) => {
          return <li key={id}>{item}</li>;
        })}
      </ol>
    </>
  );
};
```

Puedo tener todos los `useState` que necesite.

### 6.7 Agregar una nueva categoría

`src > GifExpertApp.jsx`

```jsx
import { useState } from "react";

export const GifExpertApp = () => {
  const [categories, setCategories] = useState([
    "One Punch",
    "Dragon Ball",
  ]);

  const onAddCategory = () => {
    // setCategories((item) => [...item, "New Item!!!"]);
    setCategories([...categories, "New Item!!!"]);
  };

  return (
    <>
      <h1>GifExpertApp</h1>

      <button onClick={onAddCategory}>Add</button>
      <ol>
        {categories.map((item, id) => {
          return <li key={id}>{item}</li>;
        })}
      </ol>
    </>
  );
};
```

### 6.8 Componente AddCategory

Para esta clase usaremos el `event onChange`. Este `event` se puede desestructurar como `{target}` para obtener `target.value` de manera más corta.

`src > AddCategory.jsx`

```jsx
import { useState } from "react";

const AddCategory = () => {
  const [inputValue, setInputValue] = useState("One Punch");

  const onInputChange = (event 👈👀) => {
    setInputValue(event.target.value);
  };

  const onSubmit = (event) => {
    event.preventDefault(); 👈👀

    console.log(inputValue);
  };

  return (
    <form action="" onSubmit={onSubmit}>
      <input
        type="text"
        placeholder="Search gifts"
        value={inputValue}
        onChange={onInputChange}
      />
    </form>
  );
};

export { AddCategory };
```

📌 Tip de **VSC**: Al escribir `useState` e importarlo, me subraya las partes que necesito editar para escribir el nombre deseado. Aquí escribo el nombre y presiono tabulador para que ponga en mayúscula la parte del `setI...👈👀`

```bash
// Si presiono tabulador 👇 new se vuelve New...
const [newName|👈👀, setnewName|👈👀] = useState(second)
```

### 6.9 Comunicación entre componentes

`src > GifExpertApp.jsx`

```jsx
import { useState } from "react";
import { AddCategory } from "./components/AddCategory";

export const GifExpertApp = () => {
  const [categories, setCategories] = useState([
    "One Punch",
    "Dragon Ball",
  ]);

  // const onAddCategory = () => {
  //   // setCategories((item) => [...item, "New Item!!!"]);
  //   setCategories([...categories, "New Item!!!"]);
  // };

  return (
    <>
      <h1>GifExpertApp</h1>

      <AddCategory setCategories={setCategories} /> 👈👀

      <ol>
        {categories.map((item, id) => {
          return <li key={id}>{item}</li>;
        })}
      </ol>
    </>
  );
};
```

`src > AddCategory.jsx`

```jsx
import { useState } from "react";

const AddCategory = ({ setCategories }) => {
  const [inputValue, setInputValue] = useState("One Punch");

  const onInputChange = (event) => {
    setInputValue(event.target.value);
  };

  const onSubmit = (event) => {
    event.preventDefault();

    if (inputValue.trim().length <= 1) return;

    setCategories((categories) => [
      inputValue,
      ...categories,
    ]);
    setInputValue("");
  };

  return (
    <form action="" onSubmit={onSubmit}>
      <input
        type="text"
        placeholder="Search gifts"
        value={inputValue}
        onChange={onInputChange}
      />
    </form>
  );
};

export { AddCategory };
```

### 6.10 Emitir un evento al padre

`src > GifExpertApp.jsx`

```jsx
import { useState } from "react";
import { AddCategory } from "./components/AddCategory";

const GifExpertApp = () => {
  const [categories, setCategories] = useState([
    "One Punch",
    "Dragon Ball",
  ]);

  const onAddCategory = (newCategory) => { 👈👀
    setCategories([newCategory, ...categories]);
  };

  return (
    <>
      <h1>GifExpertApp</h1>

      <AddCategory 👈👀👇
        onNewCategory={onAddCategory}
      />

      <ol>
        {categories.map((item, id) => {
          return <li key={id}>{item}</li>;
        })}
      </ol>
    </>
  );
};

export { GifExpertApp };
```

`src > components > AddCategory.jsx`

```jsx
import React, { useState } from "react";

const AddCategory = ({ onNewCategory }) => { 👈👀
  const [inputValue, setInputValue] = useState("Something");

  const onInputChange = ({ target }) => {
    setInputValue(target.value);
  };

  const onSubmit = (event) => {
    event.preventDefault();

    if (inputValue.trim().length <= 1) return;

    onNewCategory(inputValue.trim()); 👈👀

    setInputValue("");
  };

  return (
    <form onSubmit={onSubmit}>
      <input
        type="text"
        placeholder="Search gifts"
        value={inputValue}
        onChange={onInputChange}
      />
    </form>
  );
};

export { AddCategory };
```

### 6.11 Validar que los nombres sean únicos

¿Por qué es mala idea usar el `index` que brinda `map` para darle una `key` a una lista que se está renderizando?

En React, cuando se renderiza una lista de elementos, es importante asignar una clave única a cada elemento mediante la prop `key`. Esto ayuda a React a mantener el estado de la lista y a optimizar las actualizaciones.

Sin embargo, usar el índice proporcionado por el método `map` como clave no es recomendable por varias razones:

#### 1. Problemas con la reordenación

Cuando se reordena la lista, los índices cambian. Si se utiliza el índice como clave, React tendrá que volver a renderizar toda la lista, lo que puede provocar un rendimiento deficiente.

#### 2. Problemas con la eliminación de elementos

Si se elimina un elemento de la lista, los índices de los elementos restantes cambian. Al utilizar el índice como clave, React puede perder el estado de los elementos restantes.

#### 3. Problemas con la adición de elementos

Si se agrega un nuevo elemento a la lista, el índice de los elementos existentes cambia. Al utilizar el índice como clave, React puede volver a renderizar los elementos existentes.

#### Solución

En lugar de utilizar el índice proporcionado por `map`, es recomendable utilizar una clave única y estable para cada elemento. Algunas opciones son:

- Un ID único generado en el servidor o en el cliente.
- Un campo único en el objeto de datos, como un nombre o una descripción.
- Una combinación de campos que garantice la unicidad.

Por ejemplo:

```jsx
const lista = [
  { id: 1, nombre: 'Elemento 1' },
  { id: 2, nombre: 'Elemento 2' },
  { id: 3, nombre: 'Elemento 3' },
];

return (
  <ul>
    {lista.map((elemento) => (
      <li key={elemento.id}>{elemento.nombre}</li>
    ))}
  </ul>
);
```

En este ejemplo, se utiliza el campo `id` como clave única para cada elemento de la lista. Esto garantiza que cada elemento tenga una clave estable y única, lo que ayuda a React a mantener el estado de la lista y a optimizar las actualizaciones.

Por el momento para nuestro proyecto usaremos el `index`, pero validaremos si existe el nuevo dato en nuestra lista existente:

`src > GifExpertApp.jsx`

```jsx
import { useState } from "react";
import { AddCategory } from "./components/AddCategory";

const GifExpertApp = () => {
  const [categories, setCategories] = useState([
    "One Punch",
    "Dragon Ball",
  ]);

  const onAddCategory = (newCategory) => {
    if (categories.includes(newCategory)) return; 👈👀

    setCategories([newCategory, ...categories]);
  };

  return (
    <>
      <h1>GifExpertApp</h1>

      <AddCategory onNewCategory={onAddCategory} />

      <ol>
        {categories.map((item, id) => {
          return <li key={id}>{item}</li>;
        })}
      </ol>
    </>
  );
};

export { GifExpertApp };
```

Revisamos si en nuestra lista existe el nuevo elemento enviado usando `.include()`, de existir detenemos su anexión con `return`.

### 6.12 GifGrid - Nuevo componente

Recuerda que siempre se asigna la `key` al objeto padre.

`src > GifExpertApp.jsx`

```jsx
import { useState } from "react";
import { AddCategory } from "./components/AddCategory";
import { GifGrid } from "./components/GifGrid";

const GifExpertApp = () => {
  const [categories, setCategories] = useState([
    "One Punch",
    "Dragon Ball",
  ]);

  const onAddCategory = (newCategory) => {
    if (categories.includes(newCategory)) return;

    setCategories([newCategory, ...categories]);
  };

  return (
    <>
      <h1>GifExpertApp</h1>

      <AddCategory onNewCategory={onAddCategory} />

      {categories.map((item) => ( 👈👀👇
        <GifGrid key={item} category={item} />
      ))}
    </>
  );
};

export { GifExpertApp };
```

`src > components > GifGrid.jsx`

```jsx
const GifGrid = ({ category }) => {
  const gifs = [0, 1, 2, 3, 4];

  return (
    <>
      <h3>{category}</h3>
      {gifs.map((gif) => (
        <p>{gif}</p>
      ))}
    </>
  );
};

export { GifGrid };
```

### 6.13 Fetch API - Obtener las imágenes deseadas

```bash
# Instalar en Linux
snap install postman
```

Si estás en Linux y Postman no corre adecuadamente, puedes usar la versión de [Postman en la web](https://web.postman.co/home). Te creas una cuenta y entras en `My Workspace`, estando en `Collections` le das al icono `+` y listo, añades la URL con la que vas a trabajar.

![Postman web](https://i.postimg.cc/3xv7MNn2/6-postman-web.png)

`src > components > GifGrid.jsx`

```jsx
import { getGifs } from "../helpers/getGifs";

const GifGrid = ({ category }) => {
  getGifs(category); // 👈👀 Mala práctica

  return (
    <>
      <h3>{category}</h3>
    </>
  );
};

export { GifGrid };
```

`src > helpers > getGifs.js`

```js
const getGifs = async (category) => {
  const url = `https://api.giphy.com/v1/gifs/search?api_key=NhCnnfEOEkSzI8EgLmMc09dBClFt99Ou&q=${category}&limit=20`;
  const response = await fetch(url);
  const { data } = await response.json();

  const gifs = data.map((img) => {
    return {
      id: img.id,
      title: img.title,
      url: img.images.downsized_medium.url,
    };
  });

  console.log(gifs);
  return gifs;
};

export { getGifs };
```

- [**Giphy Developers - Search Endpoint**](https://developers.giphy.com/branch/master/docs/api/endpoint/#search)
- [Intalar Postman](https://learning.postman.com/docs/getting-started/installation/installation-and-updates/)
- [Postman en la web](https://web.postman.co/home)

### 6.14 useEffect

`src > components > GifGrid.jsx`

```jsx
import { useEffect, useState } from "react";
import { getGifs } from "../helpers/getGifs";

const GifGrid = ({ category }) => {
  const [counter, setCounter] = useState(10);

  useEffect(() => { 👈👀
  // Lógica para cargar los datos desde una API
    getGifs(category);
  }, []); // [counter] si cambia dispara nuevamente la func.

  return (
    <>
      <h3>{category}</h3>
      <h5>{counter}</h5>
      <button onClick={() => setCounter(counter + 1)}>
        +1
      </button>
    </>
  );
};

export { GifGrid };
```

[Hook useEffect()](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/Platzi/reactjs.md#18-qu%C3%A9-son-los-efectos-en-react-useeffect)

### 6.15 Demostración de producción rápido

```bash
yarn build
```

`yarn build` crea una carpeta llamada `dist` que contendrá nuestra aplicación de producción optimizada.

```bash
.
├── dist 👈👀
│   ├── assets
│   └── index.html
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
├── vite.config.js
└── yarn.lock
```

Luego de hacer `build` podemos usar también en script `preview` para servir localmente nuestra aplicación en un entorno de producción.  Este comando utiliza los archivos generados durante el proceso de producción para ejecutar la aplicación.

```bash
yarn preview
```

`src > components > GifGrid.jsx`

```jsx
import { useEffect } from "react";
import { getGifs } from "../helpers/getGifs";

const GifGrid = ({ category }) => {
  useEffect(() => {
    getGifs(category);
  }, []);

  return (
    <>
      <h3>{category}</h3>
    </>
  );
};

export { GifGrid };
```

`src > helpers > getGifs.js`

```jsx
const getGifs = async (category) => {
  const url = `https://api.giphy.com/v1/gifs/search?api_key=NhCnnfEOEkSzI8EgLmMc09dBClFt99Ou&q=${category}&limit=10`;
  const response = await fetch(url);
  const { data } = await response.json();

  const gifs = data.map((img) => {
    return {
      id: img.id,
      title: img.title,
      url: img.images.downsized_medium.url,
    };
  });

  return gifs;
};

export { getGifs };
```

#### http-server

http-server es un software que permite crear un servidor web básico para servir archivos estáticos a través del protocolo HTTP. Es una herramienta de línea de comandos que facilita la creación rápida de un servidor web local para el desarrollo y la visualización de sitios web estáticos.

Al utilizar http-server, puedes especificar una carpeta en tu sistema de archivos y el software creará un servidor web en tu máquina local que servirá los archivos estáticos contenidos en esa carpeta. Esto es útil cuando estás trabajando en el desarrollo de un sitio web y deseas ver cómo se ve y se comporta en un entorno de servidor web.

```bash
# Esto es opcional
npm install --global http-server
cd dist
http-server -o
```

[http-server](https://www.npmjs.com/package/http-server)

### 6.16 Mostrar los títulos de las imágenes

`src > components > GifGrid.jsx`

```jsx
import { useEffect, useState } from "react";
import { getGifs } from "../helpers/getGifs";

const GifGrid = ({ category }) => {
  const [images, setImages] = useState([]);

  const getImages = async () => { 👈👀
    const newImages = await getGifs(category);

    setImages(newImages);
  };

  useEffect(() => {
    // getGifs(category).then((newImages) =>
    //   setImages(newImages)
    // );
    getImages(); 👈👀
  }, []);

  return (
    <>
      <h3>{category}</h3>
      <ol>
        {images.map(({ id, title, url 👈👀}) => (
          <li key={id}>{title}</li>
        ))}
      </ol>
    </>
  );
};

export { GifGrid };
```

### 6.17 className - Clases de css

Ya conocemos la forma tradicional de pasar `props`, pero en esta clase veremos como pasar `props` usando el Operador de Propagación o Spread Operator `...imgs`

#### Spread Operator

El spread operator se usa para expandir elementos de un iterable (como un array o un objeto) en lugares donde se esperan múltiples elementos.

##### Ejemplos:

1. **En Arrays:**
    
    ```javascript
    const array1 = [1, 2, 3];
    const array2 = [...array1, 4, 5, 6];
    console.log(array2); // Output: [1, 2, 3, 4, 5, 6]
    ```
    
2. **En Objetos:**
    
    ```javascript
    const obj1 = { a: 1, b: 2 };
    const obj2 = { ...obj1, c: 3 };
    console.log(obj2); // Output: { a: 1, b: 2, c: 3 }
    ```
    
3. **En Funciones:**
    
    ```javascript
    function sum(x, y, z) {
      return x + y + z;
    }
    const numbers = [1, 2, 3];
    console.log(sum(...numbers)); // Output: 6
    ```

#### Rest Operator

El rest operator se usa para agrupar el resto de los elementos en un array o un objeto. Se utiliza principalmente en la desestructuración.

##### Ejemplos:

1. **En Arrays:**
    
    ```javascript
    const [first, ...rest] = [1, 2, 3, 4, 5];
    console.log(first); // Output: 1
    console.log(rest);  // Output: [2, 3, 4, 5]
    ```
    
2. **En Objetos:**
    
    ```javascript
    const { a, b, ...rest } = { a: 1, b: 2, c: 3, d: 4 };
    console.log(a);    // Output: 1
    console.log(b);    // Output: 2
    console.log(rest); // Output: { c: 3, d: 4 }
    ```
    
3. **En Parámetros de Funciones:**
    
    ```javascript
    function sum(...args) {
      return args.reduce((acc, val) => acc + val, 0);
    }
    console.log(sum(1, 2, 3, 4)); // Output: 10
    ```

En resumen, el operador `...` en JavaScript se conoce como spread operator cuando expande elementos, y rest operator cuando agrupa el resto de los elementos.

Ahora en nuestro proyecto:

`src > components > GifGrid.jsx`

```jsx
import { useEffect, useState } from "react";
import { getGifs } from "../helpers/getGifs";
import { GifItem } from "./GifItem";

const GifGrid = ({ category }) => {
  const [images, setImages] = useState([]);

  const getImages = async () => {
    const newImages = await getGifs(category);

    setImages(newImages);
  };

  useEffect(() => {
    getImages();
  }, []);

  return (
    <>
      <h3>{category}</h3>
      <div className="card-grid"> 👈👀
        {images.map((img) => (
          <GifItem key={img.id} {...img} 👈👀 />
        ))}
      </div>
    </>
  );
};

export { GifGrid };
```

`src > components > GifItem.jsx`

```jsx
const GifItem = ({ title, url, id 👈👀 }) => {
  return (
    <div className="card">
      <img src={url} alt={title} />
      <p>{title}</p>
    </div>
  );
};

export { GifItem };
```

Envía `{ ...img }` y recibe `{ title, url, id }`

### 6.18 Custom Hook - useFetchGifs

`src > components > GifGrid.jsx`

```jsx
import { GifItem } from "./GifItem";
import { useFetchGifs } from "../hooks/useFetchGifs";

const GifGrid = ({ category }) => {👈👀👇
  const { images, isLoading } = useFetchGifs(category);

  return (
    <>
      <h3>{category}</h3>
      <div className="card-grid">
        {images.map((img) => (
          <GifItem key={img.id} {...img} />
        ))}
      </div>
    </>
  );
};

export { GifGrid };
```

`src > hooks > useFetchGifs.js`

```js
import { useEffect, useState } from "react";
import { getGifs } from "../helpers/getGifs";

const useFetchGifs = (category) => {
  const [images, setImages] = useState([]);
  const [isLoading, setIsLoading] = useState(true);

  const getImages = async () => {
    const newImages = await getGifs(category);

    setImages(newImages);
  };

  useEffect(() => {
    getImages();
    setIsLoading(false);
  }, []);

  return {
    images,
    isLoading,
  };
};

export { useFetchGifs };
```

- [Apuntes Custom Hooks](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/Platzi/reactjs.md#14-custom-hooks)
- [[reactjs#14. Custom Hooks]]
- [Pesticide for Chrome](https://chromewebstore.google.com/detail/pesticide-for-chrome-mv3/jeebpgmphhagpecfiophljpkhncoajcg?hl=es-419)
- [CSS Debugger](https://chromewebstore.google.com/detail/css-debugger/bjpidjfkmlbmlfeogdpemieacmdicdno)

### 6.19 Mostrar mensaje de carga

`src > components > GifGrid.jsx`

```jsx
import { GifItem } from "./GifItem";
import { useFetchGifs } from "../hooks/useFetchGifs";

const GifGrid = ({ category }) => {
  const { images, isLoading } = useFetchGifs(category);

  console.log({ images, isLoading });

  return (
    <>
      <h3>{category}</h3>👈👀👇
      {isLoading && <h2>Loading...</h2>}

      <div className="card-grid">
        {images.map((img) => (
          <GifItem key={img.id} {...img} />
        ))}
      </div>
    </>
  );
};

export { GifGrid };
```

### 6.20 Archivos de barril

En el contexto de JavaScript y React, los "Archivos de barril" (también conocidos como "Archivos de índice" o "Archivos de barril de exportación") son archivos utilizados para exportar múltiples módulos desde una carpeta o directorio en un solo punto de acceso. En lugar de tener que importar cada módulo individualmente desde su ubicación específica, puedes importarlos todos a través del archivo de barril.

La idea detrás de los archivos de barril es simplificar y centralizar la importación de módulos dentro de una carpeta o directorio. Imagina una situación en la que tienes una carpeta llamada "componentes" que contiene varios componentes de React. En lugar de importar cada componente individualmente al utilizarlos en otros archivos, puedes crear un archivo de barril en la carpeta "componentes" que exporte todos los componentes desde un solo lugar.

Aquí hay un ejemplo de cómo se podría estructurar un archivo de barril en una carpeta de componentes:

```javascript
// components/index.js

export { default as Componente1 } from './Componente1';
export { default as Componente2 } from './Componente2';
export { default as Componente3 } from './Componente3';
// ... y así sucesivamente
```

En este caso, el archivo de barril `index.js` exporta los componentes `Componente1`, `Componente2` y `Componente3` desde sus respectivos archivos. Luego, en otros archivos de tu proyecto, puedes importar todos los componentes utilizando una sola línea de código:

```javascript
import { Componente1, Componente2, Componente3 } from './components';
```

Esto simplifica la estructura de importación y hace que tu código sea más legible y mantenible, especialmente cuando tienes una gran cantidad de módulos en una carpeta.

Los archivos de barril no son exclusivos de React, sino que se pueden utilizar en cualquier proyecto de JavaScript para exportar varios módulos desde una ubicación centralizada. Ayudan a organizar y simplificar la importación de código en proyectos más grandes, evitando la necesidad de especificar rutas de archivo largas y repetitivas en cada importación.

En nuestro proyecto:

`src > components > index.js`

```jsx
export * from "./AddCategory";
export * from "./GifGrid";
export * from "./GifItem";
```

`src > hooks > GifExpertApp.jsx`

```jsx
import { useState } from "react"; 👈👀👇
import { AddCategory, GifGrid } from "./components";

const GifExpertApp = () => {
  const [categories, setCategories] = useState([
    "One Punch",
  ]);

  const onAddCategory = (newCategory) => {
    if (categories.includes(newCategory)) return;

    setCategories([newCategory, ...categories]);
  };

  return (
    <>
      <h1>GifExpertApp</h1>

      <AddCategory onNewCategory={onAddCategory} />

      {categories.map((item) => (
        <GifGrid key={item} category={item} />
      ))}
    </>
  );
};

export { GifExpertApp };
```

La estructura del proyecto queda así:

```bash
.
├── dist
├── index.html
├── node_modules
├── package.json
├── README.md
├── src 👈👀👇
│   ├── components
│   │   ├── AddCategory.jsx
│   │   ├── GifGrid.jsx
│   │   ├── GifItem.jsx
│   │   └── index.js 👈👀
│   ├── GifExpertApp.jsx 👈👀
│   ├── helpers
│   │   └── getGifs.js
│   ├── hooks
│   │   └── useFetchGifs.js
│   ├── main.jsx
│   └── styles.css
├── vite.config.js
└── yarn.lock
```

[Limas de barril y por qué deberías DEJAR de usarlas ahora](https://dev.to/tassiofront/barrel-files-and-why-you-should-stop-using-them-now-bc4)

### 6.21 Código fuente de la sección

Aquí les dejo el código fuente de la sección, tal cual lo dejé en el último video para que puedan compararlo contra el suyo si fuera necesario.

[**GitHub - Fin Sección 6**](https://github.com/Klerith/react-vite-gif-expert/tree/fin-seccion-6) 

## 🟣 7. Generando el build de producción y despliegues

### 7.1 Introducción a la sección

El despliegue se hará en GitHub.

### 7.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Aprender cómo realizar backups a repositorios de Git
- Subir nuestro repositorio a GitHub
- Uso de GitHub Pages
- Desplegar nuestra aplicación de React
- Generar build de producción de nuestra aplicación

Aunque es una sección pequeña, les puede servir para desplegar infinidad de proyectos de React de forma gratuita, sin contar que tendrán respaldos de sus proyectos por si llegan a perder su trabajo que tenían localmente en su computadora.

### 7.3 Desplegar en Netlify

`src > components > GifGrid.jsx`

```bash
# Instalar dependencias: package.json
yarn

# Ejecutar el proyecto
yarn dev

# Abrir el proyecto en VSC
code-insiders .

# Crear carpeta dist
yarn build
```

[Crear cuenta en Netlify](https://app.netlify.com/teams/alevroses/overview)

Una vez dentro de Netlify nos vamos a **Sites** donde aparece un mensaje dentro de un recuadro igual al siguiente:

```bash
Want to deploy a new site without connecting to Git?
Drag and drop your site output folder here

Or, browse to upload.
```

Arrastra la carpeta **dist** dentro de ese recuadro y espera a que termine de cargar.

Si el nombre del proyecto no te gusta puedes cambiarlo yendo a **Site Configuration** y busca **Change site name**.

De `luxury-buttercream-ed1988` lo cambié a `search-tests`.

[Web desplegada](https://search-tests-two.netlify.app/)

#### Actualizar proyecto

Para volver a desplegar o actualizar nuestro proyecto nos vamos a la página principal y buscamos `Sites`, damos clic a nuestro proyecto y luego en `Deploys`, tendremos que ver algo así:

> Need to update your site?
> Drag and drop your site output folder here.
> Or, browse to upload.

Arrastras nuevamente la carpeta `dist` y listo.

### 7.4 Preparación del proyecto - GitHub Pages

Asegúrate de tener un `.gitignore` con todos los archivos y carpetas a ignorar en el repositorio de GitHub.

```bash
git init
git add .
git commit -am "First commit"
```

En caso de borrar archivos importantes del proyecto puedes reconstruirlos con: 

```bash
git checkout -- .
```

- [[gh-pages]] 👈👀
- [Apuntes GitHub Pages](https://github.com/aleroses/Platzi/blob/master/DW/1-basico/005-git-github/gh-pages.md)

### 7.5 Subir a GitHub

Crea un repositorio en GitHub y enlazalo con tu repositorio local.

Actualmente he visto que siempre pide una `key` cuando es la primera vez que usamos Git y GitHub o cuando es una Sistema Operativo o Computador nuevo.

Dejo los apuntes donde se toca ese tema:

[⚠☢ Posible error ☣](https://github.com/aleroses/Platzi/blob/master/DW/1-basico/005-git-github/git-github.md#-posible-error-)

### 7.6 Desplegando aplicación en Github Pages

Puedes renombrar `dist` por `docs`.

```bash
git add . && git commit -am "Update" && git push origin master
```

En el repositorio en GitHub te vas a Settings/Pages y en el apartado de Branch selecciona la rama, luego `/docs` y dale a `Save`.

Personalmente el método que uso para subir y desplegar mis pequeños proyectos es el que se detalla en los enlaces abajo.

[[gh-pages]] 👈👀

[Apuntes GitHub Pages](https://github.com/aleroses/Platzi/blob/master/DW/1-basico/005-git-github/gh-pages.md)

### 7.7 Actualizar GitHub pages

En caso de un error como el mostrado en clase debes ir a `docs/index.html` y dejar los links de la siguiente manera:

```html
href="./assets/index.df2abcea.css"
```

En caso de persistir el error también modifica el link en la raíz principal en el `index.html` en la parte del `main`.

El link del **favicon** no hace falta cambiarlo.

Ahora envía los cambios a GitHub, espera y listo.

[Vite React App Deploy on GitHub](https://www.youtube.com/watch?v=XhoWXhyuW_I)

## 🟡 8. Testing - Probando la aplicación de GifExpert

### 8.1 Introducción a la sección

### 8.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Seguir el camino de las pruebas
- Pruebas en componentes específicos
- Pruebas en componentes de forma individual
- Pruebas con customHooks 
- Esperar cambios en un customHook
- Simular eventos en inputs y formularios
- Simular llamadas a funciones
- Evaluar si existen elementos en el componente

En esta sección seguiremos expandiendo todo lo que habíamos visto anteriormente en otras secciones de pruebas, pero ahora veremos más a detalle los temas y adicionalmente introduciremos nuevos conceptos y nuevos tipos de pruebas.

### 8.3 Configurar el ambiente de pruebas

Instalación y configuración de Jest + React Testing Library

#### En proyectos de React + Vite

1. Instalaciones:
```bash
# Explicación de cada comando en la parte de abajo.
yarn add --dev 
  jest 
  babel-jest 
  @babel/preset-env 
  @babel/preset-react 

yarn add --dev 
  @testing-library/react 
  @types/jest 
  jest-environment-jsdom
```

Puedes ejecutar el comando de arriba o instalar todo por separado e ir viendo que cosas estás instalando, ver lista inferior.

- Instalar Jest: `yarn add --dev jest`
- Integrar Babel con Jest:
	- `yarn add --dev babel-jest @babel/core @babel/preset-env`
	- `yarn add -D @babel/preset-react` transpilar.
- Instalar React Testing Library: Actual 👈👀👇
	- `yarn add --dev @testing-library/react @testing-library/dom`
- Añadir ayudas o intelligent a Visual Studio Code:
	- `yarn add -D @types/jest`
- Implementa navegador web en JavaScript, lo que permite simular el DOM.
	- `yarn add -D jest-environment-jsdom`

2. Opcional: Si usamos Fetch API en el proyecto:
```bash
yarn add --dev whatwg-fetch
```

3. Actualizar los scripts del `package.json`
```js
"scripts: {
  ...
  "test": "jest --watchAll"
```

4. Crear la configuración de babel `babel.config.cjs`
```js
module.exports = {
  presets: [
    ["@babel/preset-env", { targets: { esmodules: true } }],
    ["@babel/preset-react", { runtime: "automatic" }],
  ],
};
```

5. Opcional, pero eventualmente necesario, crear Jest config y setup:

`jest.config.cjs`
```jsx
module.exports = {
  testEnvironment: "jest-environment-jsdom",
  setupFiles: ["./jest.setup.js"],
  transformIgnorePatterns: [],
};
```

`jest.setup.js`
```js
// En caso de necesitar la implementación del FetchAPI
import 'whatwg-fetch'; // <-- yarn add whatwg-fetch
```

Ahora podemos hacer una demostración de como funcionan los test.

`tests > demo.test.js`

```js
test("Esta prueba no debe de fallar", () => {
  if (0 === 1) {
    throw new Error("No puede dividir entre cero");
  }
});
```

[vite-testing-config](https://gist.github.com/Klerith/ca7e57fae3c9ab92ad08baadc6c26177)

### 8.4 Implementando PropTypes

Trazar la ruta critica:

En Vite los `PropTypes` no vienen instalados por defecto y para React 19 esto quedó obsoleto:

```bash
yarn add prop-types 

# Para NPM
npm install prop-types
```

`src > components > GifGrid.jsx`

```jsx
import PropTypes from "prop-types";

export const GifItem = ({ title, url, id }) => {
  return (
    <div className="card">
      <h3>{title}</h3>
      <img src={url} alt={title} />
    </div>
  );
};

GifItem.propTypes = { 👈👀
  title: PropTypes.string.isRequired,
  url: PropTypes.string.isRequired,
};
```

`test > components > GifItem.test.jsx`

```jsx
import { render } from "@testing-library/react";
import { GifItem } from "../../src/components/GifItem";

describe("GifItem test", () => {
  const data = {
    title: "Testing",
    url: "https://redflag",
    id: "2",
  };

  test("Should match the snapshot", () => {
    const { container } = render(
      <GifItem title={data.title} url={data.url} />
    );
    expect(container).toMatchSnapshot();
  });
});
```

### 8.5 Resolución de la tarea

Lo mismo que el punto anterior.

### 8.6 Pruebas del componente - GifGridItem

`test > components > GifItem.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { GifItem } from "../../src/components/GifItem";

describe("GifItm test", () => {
  const data = {
    title: "Testing",
    url: "https://red.png/",
    id: "2",
  };

  test("Should match the snapshot", () => {
    const { container } = render(
      <GifItem title={data.title} url={data.url} />
    );
    expect(container).toMatchSnapshot();
  });

  test("should display the image with the url", () => {
    render(<GifItem title={data.title} url={data.url} />);

    // screen.debug();
    // console.log(screen.getByRole("img").src);

    // One way
    expect(screen.getByRole("img").src).toBe(data.url);
    expect(screen.getByRole("img").alt).toBe(data.title);

    // Another way
    const { src, alt } = screen.getByRole("img");
    expect(src).toBe(data.url);
    expect(alt).toBe(data.title);
    // screen.debug();
  });

  test("should display the title in the component", () => {
    render(<GifItem title={data.title} url={data.url} />);
    expect(screen.getByText(data.title)).toBeTruthy();
  });
});
```

### 8.7 Pruebas en el helper getGifs

#### toBeGreaterThan()

`toBeGreaterThan()` es un matcher que se utiliza para verificar que un valor numérico es mayor que otro. Jest proporciona una serie de matchers para realizar diferentes tipos de aserciones (assertions) en tus pruebas, y `toBeGreaterThan()` es uno de ellos.

Aquí tienes un ejemplo sencillo de cómo usar `toBeGreaterThan()` en una prueba con Jest:

```javascript
test('el valor es mayor que 10', () => {
  const valor = 15;
  expect(valor).toBeGreaterThan(10);
});
```

En este ejemplo, la prueba verificará que la variable `valor` (que es 15) es mayor que 10. Si `valor` fuera menor o igual a 10, la prueba fallaría.

##### Uso en el contexto de React Testing Library

Supongamos que tienes un componente de React que muestra el número de elementos en una lista y quieres asegurarte de que siempre hay más de 5 elementos:

```javascript
import React from 'react';
import { render, screen } from '@testing-library/react';
import '@testing-library/jest-dom/extend-expect';
import MiComponente from './MiComponente';

test('la lista tiene más de 5 elementos', () => {
  render(<MiComponente />);
  const elementos = screen.getAllByRole('listitem');
  expect(elementos.length).toBeGreaterThan(5);
});
```

En este ejemplo, `screen.getAllByRole('listitem')` obtiene todos los elementos de la lista del componente `MiComponente`, y `expect(elementos.length).toBeGreaterThan(5)` verifica que la cantidad de elementos en la lista es mayor que 5.

Ahora en nuestro proyecto:

`test > helpers > getGif.test.js`

```jsx
import { getGif } from "../../src/helpers/getGif";

describe("getGif testing", () => {
  test("should display an gifs array", async () => {
    // It worked without passing the “flag” parameter.
    const gifs = await getGif("flag");

    // console.log(gifs);

    // Array.isArray(gifs) returns true
    expect(Array.isArray(gifs)).toBeTruthy();
    expect(gifs.length).toBeGreaterThan(0);

    // Check an object
    expect(gifs[0]).toEqual({
      id: expect.any(String),
      title: expect.any(String),
      url: expect.any(String),
    });

    // Check all objects
    gifs.forEach((obj) => {
      expect(obj).toEqual({
        id: expect.any(String),
        title: expect.any(String),
        url: expect.any(String),
      });
    });
  });
});
```

### 8.8 Pruebas del componente - AddCategory

`test > components > AddCategories.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { AddCategories } from "../../src/components/AddCategories";

describe("Testing in AddCategories", () => {
  test("should change the value of the text box", () => {
    render(<AddCategories onValueUpdate={() => {}} />);

    const input👈👀 = screen.getByRole("textbox");

    // console.log(input);

    // screen.debug();

    fireEvent.input(input, {👈👀👇
      target: { value: "Gogueta" },
    });

    expect(input.value).toBe("Gogueta");

    screen.debug();
  });
});
```

### 8.9 Simular un submit del formulario

En React (o en JSX en general), el atributo `aria-label` es utilizado para mejorar la accesibilidad de los elementos en una aplicación web. El propósito de `aria-label` es proporcionar una etiqueta de texto que describe el elemento para los lectores de pantalla y otras tecnologías de asistencia. Esto es particularmente útil para elementos que no tienen un texto visible o cuyo propósito no es obvio para los usuarios con discapacidades visuales.

Considera el siguiente botón que contiene un ícono, pero no tiene texto visible:

```jsx
<button>
  <i className="fas fa-play"></i>
</button>
```

Para los usuarios que dependen de los lectores de pantalla, este botón podría ser confuso porque el ícono por sí solo no proporciona suficiente contexto. Al agregar un `aria-label`, podemos describir la función del botón:

```jsx
import React from 'react';

const PlayButton = () => {
  return (
    <button aria-label="Play">
      <i className="fas fa-play"></i>
    </button>
  );
};

export default PlayButton;
```

En este caso, el lector de pantalla leerá "Play" cuando enfoque este botón, proporcionando una mejor experiencia de usuario para aquellos con discapacidades visuales.

#### ¿Cuándo Usar `aria-label`?

1. **Elementos con Íconos o Imágenes:** Si el elemento contiene solo un ícono o una imagen sin texto visible.
2. **Elementos Interactivos sin Texto:** Para elementos interactivos (como botones, enlaces, etc.) que no tienen texto visible pero necesitan ser descriptivos.
3. **Mejorar la Descripción:** Si el texto visible no describe adecuadamente el propósito del elemento.

#### Consideraciones

- **Consistencia:** Asegúrate de que las descripciones sean consistentes y claras en toda la aplicación.
- **Brevedad:** Mantén las etiquetas breves pero descriptivas.
- **No Redundancia:** No uses `aria-label` si ya hay un texto visible que describe adecuadamente el elemento.

Al usar `aria-label` adecuadamente, puedes asegurarte de que tu aplicación sea más accesible y usable para todos los usuarios.

En nuestro proyecto:

`src > components > AddCategories.jsx`

```jsx
import PropTypes from "prop-types";
import { useState } from "react";

export const AddCategories = ({ onValueUpdate }) => {
  const [inputValue, setInputValue] = useState("");

  const handleInput = (event) => {
    const newValue = event.target.value;

    setInputValue(newValue);
  };

  const handleSubmit = (event) => {
    console.log("Hi world from the hanleSubmit"); 👈👀

    event.preventDefault();

    if (inputValue.trim().length <= 1) return;

    onValueUpdate(inputValue.trim());

    setInputValue("");
  };

  return (
    // Does not work with id or className
    <form aria-label="form"👈👀 onSubmit={handleSubmit}>
      <input
        type="text"
        placeholder="Search something"
        value={inputValue}
        onChange={handleInput}
      />
    </form>
  );
};

AddCategories.propTypes = {
  onValueUpdate: PropTypes.func.isRequired,
};
```

`test > components > AddCategories.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { AddCategories } from "../../src/components/AddCategories";

describe("AddCategories testing", () => {
  test("should change the value of the text box", () => {
    render(<AddCategories onValueUpdate={() => {}} />);

    const input = screen.getByRole("textbox");

    // console.log(input);

    // screen.debug();

    fireEvent.input(input, {
      target: { value: "Gogueta" },
    });

    expect(input.value).toBe("Gogueta");

    // screen.debug();
  });

  test("should call onValueUpdate if the input has a value", () => {
    const inputValue = "Gogueta";

    // TODO: ???

    render(<AddCategories onValueUpdate={() => {}} />);

    const input = screen.getByRole("textbox");
    const form = screen.getByRole("form");👈👀

    fireEvent.input(input, {👈👀👇
      targer: { value: inputValue },
    });

    // Triggering the submit: aria-label="form"
    fireEvent.submit(form);👈👀

    // screen.debug();

    expect(input.value).toBe("");
  });
});
```

En esta prueba primero renderizamos el componente, simulamos un `input` y luego un `submit`, con esto se espera que el `value` quede vacío. Para que el `submit(form)` funcione primero debes añadir un `arial-label` en la etiqueta JSX `form` del componente.

[Attributes aria-label](https://developer.mozilla.org/es/docs/Web/Accessibility/ARIA/Attributes/aria-label)

### 8.10 Jest Functions

En Jest, un "mock" es una técnica utilizada para reemplazar partes de tu código o dependencias durante las pruebas con objetos simulados que imitan el comportamiento de los objetos reales. Esto es útil para aislar el código que estás probando y eliminar dependencias externas que podrían afectar los resultados de las pruebas.

#### Tipos de Mocks en Jest

1. **Mock Functions (Funciones Mock):** Estas son funciones que te permiten espiar las llamadas a la función, sus argumentos, y controlar su comportamiento. Son útiles para probar la lógica que depende de las funciones que pasan como argumentos.
    
    ```javascript
    const myMock = jest.fn();
    
    // Llamar a la función mock
    myMock('arg1', 'arg2');
    
    // Verificar que la función fue llamada
    expect(myMock).toHaveBeenCalled();
    expect(myMock).toHaveBeenCalledWith('arg1', 'arg2');
    ```
    
2. **Manual Mocks:** Puedes crear manualmente archivos mock para módulos específicos en tu proyecto. Estos archivos suelen colocarse en un directorio llamado `__mocks__`.
    
    Estructura de directorios:
    
    ```
    /my-module.js
    /__mocks__/my-module.js
    ```
    
    ```javascript
    // __mocks__/my-module.js
    module.exports = {
      myFunction: jest.fn().mockReturnValue('mocked value'),
    };
    ```
    
3. **Auto Mocks:** Jest puede generar mocks automáticamente para módulos completos usando la función `jest.mock`.
    
    ```javascript
    jest.mock('./my-module');
    
    const myModule = require('./my-module');
    
    // La función dentro del módulo está ahora mockeada
    myModule.myFunction.mockReturnValue('mocked value');
    ```
    
4. **Mocking Timers:** Jest también puede mockear funciones de temporizadores, como `setTimeout`, `setInterval`, y `Date`.
    
    ```javascript
    jest.useFakeTimers();
    
    setTimeout(() => {
      console.log('Hello');
    }, 1000);
    
    jest.runAllTimers();
    
    // El mensaje 'Hello' se registra inmediatamente
    ```
    

#### ¿Por qué usar Mocks?

- **Aislar el Código:** Permite probar una unidad de código sin depender de otros módulos o servicios externos.
- **Simular Comportamientos:** Puedes simular comportamientos de funciones y módulos que son difíciles de reproducir en un entorno de prueba (como respuestas de API).
- **Mejorar la Velocidad de las Pruebas:** Eliminar dependencias externas puede hacer que las pruebas sean más rápidas y menos propensas a fallar debido a problemas externos.

#### Ejemplo Completo

Supongamos que tienes una función que depende de una API externa:

```javascript
// api.js
export const fetchData = () => {
  return fetch('https://api.example.com/data')
    .then(response => response.json());
};

// user.js
import { fetchData } from './api';

export const getUserData = () => {
  return fetchData().then(data => data.user);
};
```

Puedes mockear la función `fetchData` en tu prueba para controlar su comportamiento:

```javascript
// __tests__/user.test.js
import { getUserData } from '../user';
import { fetchData } from '../api';

jest.mock('../api');

test('getUserData returns user data', async () => {
  fetchData.mockResolvedValue({ user: 'John Doe' });

  const user = await getUserData();

  expect(user).toBe('John Doe');
  expect(fetchData).toHaveBeenCalled();
});
```

En este ejemplo, `fetchData` está mockeado para devolver un valor específico, permitiendo que la prueba de `getUserData` sea predecible y controlada.

Los mocks son una herramienta poderosa en Jest que te permiten crear pruebas más robustas y confiables al simular el comportamiento de las dependencias de tu código.

Ahora en nuestro proyecto:

`src > components > AddCategories.jsx`

```jsx
import PropTypes from "prop-types";
import { useState } from "react";

export const AddCategories = ({ onValueUpdate }) => {
  const [inputValue, setInputValue] = useState("");

  const handleInput = (event) => {
    const newValue = event.target.value;

    setInputValue(newValue);
  };

  const handleSubmit = (event) => {
    // console.log("Hi world from the hanleSubmit");

    event.preventDefault();

    if (inputValue.trim().length <= 1) return;

    // Calling two or more times
    onValueUpdate(inputValue.trim());

    setInputValue("");
  };

  return (
    <form aria-label="form" onSubmit={handleSubmit}>
      <input
        type="text"
        placeholder="Search something"
        value={inputValue}
        onChange={handleInput}
      />
    </form>
  );
};

AddCategories.propTypes = {
  onValueUpdate: PropTypes.func.isRequired,
};
```

`test > components > AddCategories.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { AddCategories } from "../../src/components/AddCategories";

describe("AddCategories testing", () => {
  test("should change the value of the text box", () => {
    render(<AddCategories onValueUpdate={() => {}} />);

    const input = screen.getByRole("textbox");

    // console.log(input);

    // screen.debug();

    fireEvent.input(input, {
      target: { value: "Gogueta" },
    });

    expect(input.value).toBe("Gogueta");

    // screen.debug();
  });

  test("should call onValueUpdate if the input has a value", () => {
    const inputValue = "Gogueta";
    // Mock simulación
    const onValueUpdate = jest.fn();

    // TODO: ???

    render(<AddCategories onValueUpdate={onValueUpdate} />);

    const input = screen.getByRole("textbox");
    const form = screen.getByRole("form");

    fireEvent.input(input, {
      target: { value: inputValue },
    });

    // Triggering the submit
    fireEvent.submit(form);

    // screen.debug();

    expect(input.value).toBe("");
    expect(onValueUpdate).toHaveBeenCalled();
    expect(onValueUpdate).toHaveBeenCalledTimes(1);
    expect(onValueUpdate).toHaveBeenCalledWith(inputValue);

    // console.log(onValueUpdate);
  });

  test("shouldn't call the onValueUpdate if the input is empty.", () => {
    const onValueUpdate = jest.fn();
    render(<AddCategories onValueUpdate={onValueUpdate} />);

    const form = screen.getByRole("form");
    fireEvent.submit(form);

    expect(onValueUpdate).toHaveBeenCalledTimes(0);
    expect(onValueUpdate).not.toHaveBeenCalled();
  });
});
```

### 8.11 Pruebas del componente GifGrid - Mock customHook

Recuerda que los `PropTypes` quedaron obsoletos en **abril de 2017 (v15.5.0)**.

En React 19, se eliminaron las `propType` comprobaciones del paquete React y su uso se ignorará de forma silenciosa. Si estás usando `propTypes`, se recomienda migrar a TypeScript u otra solución de verificación de tipos.

También estamos eliminando `defaultProps` los componentes de función que reemplazan los parámetros predeterminados de ES6.

[Documentación](https://es.react.dev/blog/2024/04/25/react-19-upgrade-guide#removed-proptypes-and-defaultprops)

`test > components > GifGrid.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { GifGrid } from "../../src/components/GifGrid";

describe("GifGrid testing", () => {
  const category = "One Punch";

  test("should show the initial load", () => {
    render(<GifGrid data={category} />);

    // screen.debug();
    expect(screen.getByText("Loading..."));
    expect(screen.getByText(category));
  });

  test("should display items when loading images from useFetchGif", () => {
    //second;
  });
});
```

### 8.12 Hacer un mock completo de un Custom Hook

#### ¿Qué es una función simulada?

Una función simulada (mock function) en Jest es una función que reemplaza una implementación original o real con implementaciones controladas que retornan valores predecibles. Esto es útil para aislar la lógica de la unidad de código que estás probando. Facilitando la creación de pruebas consistentes y repetibles.

#### `.mockReturnValue()`

El método `.mockReturnValue(value)` de Jest se usa para especificar el valor que una función simulada debe retornar cada vez que es llamada. Esto significa que, independientemente de los argumentos con los que se llame a la función simulada, siempre retornará el valor que se ha especificado con `.mockReturnValue(value)`.

#### Ejemplo de uso

Vamos a ver un ejemplo paso a paso de cómo usar `.mockReturnValue()` en una prueba con Jest y Testing Library.

##### Paso 1: Crear una función y un componente

Supongamos que tenemos una función `getData` que queremos simular en nuestras pruebas, y un componente `DataComponent` que usa esta función.

```javascript
// getData.js
export const getData = () => {
  return [
    { id: 1, name: 'Item 1' },
    { id: 2, name: 'Item 2' },
  ];
};

// DataComponent.jsx
import React, { useEffect, useState } from 'react';
import { getData } from './getData';

const DataComponent = () => {
  const [data, setData] = useState([]);

  useEffect(() => {
    const fetchData = async () => {
      const result = await getData();
      setData(result);
    };
    fetchData();
  }, []);

  return (
    <ul>
      {data.map((item) => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
};

export default DataComponent;
```

##### Paso 2: Crear la prueba

Ahora, vamos a escribir una prueba para `DataComponent` usando Jest y Testing Library, y simularemos la función `getData` usando `.mockReturnValue()`.

```javascript
// DataComponent.test.jsx
import React from 'react';
import { render, screen } from '@testing-library/react';
import DataComponent from './DataComponent';
import { getData } from './getData';

jest.mock('./getData'); // Simula el módulo getData

test('should render a list of items', async () => {
  // Usar .mockReturnValue() para especificar el valor de retorno de la función simulada
  const mockData = [
    { id: 1, name: 'Mock Item 1' },
    { id: 2, name: 'Mock Item 2' },
  ];
  getData.mockReturnValue(mockData);

  render(<DataComponent />);

  // Verificar que los elementos simulados están en el documento
  expect(await screen.findByText('Mock Item 1')).toBeInTheDocument();
  expect(await screen.findByText('Mock Item 2')).toBeInTheDocument();
});
```

##### Explicación del Ejemplo

1. **Simulación del Módulo**: Usamos `jest.mock('./getData')` para simular el módulo `getData`. Esto reemplaza la implementación real de `getData` con una simulada.
2. **Configuración del Valor de Retorno**: Usamos `getData.mockReturnValue(mockData)` para especificar que cada vez que `getData` sea llamada en el contexto de esta prueba, retornará `mockData`.
3. **Renderizar el Componente**: Renderizamos el componente `DataComponent` usando Testing Library.
4. **Verificación de la Salida**: Usamos `screen.findByText` para verificar que los elementos del array `mockData` están presentes en el documento. `findByText` es una función asíncrona que espera a que el elemento aparezca en el DOM.

Al usar `.mockReturnValue()`, podemos controlar exactamente lo que retorna `getData` durante la prueba, permitiéndonos verificar que `DataComponent` maneja correctamente estos datos simulados sin depender de la implementación real de `getData`.

Ahora en nuestro proyecto:

Simular que el `useFetchGifs` va a regresar el valor que quiera:

`test > components > GifGrid.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { GifGrid } from "../../src/components/GifGrid";
import { useFetchGifs } from "../../src/hooks/useFetchGifs";

jest.mock("../../src/hooks/useFetchGifs");

describe("GifGrid testing", () => {
  const category = "One Punch";

  test("should show the initial load", () => {
    useFetchGifs.mockReturnValue({
      images: [],
      isLoading: true,
    });

    render(<GifGrid data={category} />);

    // screen.debug();
    expect(screen.getByText("Loading..."));
    expect(screen.getByText(category));
  });

  test("should display items when loading images from useFetchGif", () => {
    const gifs = [
      {
        id: "ABC",
        title: "Gogeta",
        url: "https://localhost/gogeta.jpg/",
      },
      {
        id: "123",
        title: "Vegetto",
        url: "https://localhost/gogeta.jpg/",
      },
    ];

    useFetchGifs.mockReturnValue({
      images: gifs,
      isLoading: true,
    });

    render(<GifGrid data={category} />);

    // screen.debug();
    expect(screen.getAllByRole("img").length).toBe(2);
  });
});
```

### 8.13 Pruebas sobre customHooks

#### `renderHook`

- **Definición**: Es una función proporcionada por `@testing-library/react-hooks` para probar hooks de React de manera aislada.
- **Uso**: Permite renderizar un hook y obtener su estado actual para realizar aserciones sobre su comportamiento.
- **Ejemplo**:
    
    ```javascript
    import { renderHook } from '@testing-library/react-hooks';
    import useCustomHook from './useCustomHook';
    
    const { result } = renderHook(() => useCustomHook());
    ```
    

#### `result.current`

- **Definición**: Es una propiedad del objeto retornado por `renderHook` que contiene el valor actual retornado por el hook.
- **Uso**: Se usa para acceder al estado y funciones del hook en el momento actual.
- **Ejemplo**:
    
    ```javascript
    const { result } = renderHook(() => useCustomHook());
    expect(result.current.someValue).toBe(expectedValue);
    ```
    

#### `waitFor`

- **Definición**: Es una función de `@testing-library/react` que espera hasta que una condición especificada sea verdadera.
- **Uso**: Se usa para manejar operaciones asíncronas y asegurar que el código bajo prueba ha alcanzado el estado deseado antes de realizar aserciones.
- **Ejemplo**:
    
    ```javascript
    import { renderHook, act } from '@testing-library/react-hooks';
    import { waitFor } from '@testing-library/react';
    import useAsyncHook from './useAsyncHook';
    
    const { result } = renderHook(() => useAsyncHook());
    
    act(() => {
      result.current.someAsyncFunction();
    });
    
    await waitFor(() => {
      expect(result.current.someValue).toBe(expectedValue);
    });
    ```

#### Resumen

- **`renderHook`**: Renderiza un hook para pruebas.
- **`result.current`**: Accede al valor actual del hook.
- **`waitFor`**: Espera hasta que una condición se cumpla en pruebas asíncronas.

En nuestro proyecto:

`test > components > useFetchGifs.test.jsx`

```jsx
import {
  renderHook,
  waitFor,
} from "@testing-library/react";
import { useFetchGifs } from "../../src/hooks/useFetchGifs";

describe("Testing useFetchGifs", () => {
  test("should return the initial state", () => {
    const { result } = renderHook(() =>
      useFetchGifs("One Punch")
    );

    // console.log(result);
    const { images, isLoading } = result.current;

    expect(images.length).toBe(0);
    expect(isLoading).toBeTruthy();
  });

  test("should return an array of images and isLoading should be set to false.", async () => {
    const { result } = renderHook(() =>
      useFetchGifs("One punch")
    );

    await waitFor(
      () =>
        expect(
          result.current.images.length
        ).toBeGreaterThan(0)
      //, {
      //   timeout: 2000,
      // }
    );

    const { images, isLoading } = result.current;
    expect(images.length).toBeGreaterThan(0);
    expect(isLoading).toBeFalsy();
  });
});
```

### 8.14 Pruebas de tarea

Hacer algunas pruebas sobre `GifExpertApp.jsx`

`src > components > GifExpertApp.test.jsx`

```jsx
import {
  fireEvent,
  render,
  renderHook,
  screen,
} from "@testing-library/react";
import { GifExpertApp } from "../src/GifExpertApp";
import { AddCategories } from "../src/components";
import { useState } from "react";

// jest.mock("../src/GifExpertApp");

describe("GifExpertApp testing", () => {
  test("Should display a title", () => {
    render(<GifExpertApp />);

    // screen.debug();

    const heading = screen.getByRole("heading", {
      level: 1,
    });
    const form = screen.getByRole("form");

    // console.log(heading.innerHTML);

    expect(heading.innerHTML).toBe("GifExpertApp");
    expect(form).toContain();

    // screen.debug();
  });

  test("Should add a new category", () => {
    render(<GifExpertApp />);

    const input = screen.getByRole("textbox");
    const form = screen.getByRole("form");

    fireEvent.input(input, { target: { value: "gogeta" } });

    fireEvent.submit(form);

    const value = screen.getByText("gogeta");

    // screen.debug()
    expect(value).toBeTruthy();
  });

  test("Should not add a new category if it already exists", () => {
    const testValue = "Gogeta";

    render(<GifExpertApp />);

    const input = screen.getByRole("textbox");
    const form = screen.getByRole("form");

    fireEvent.input(input, {
      target: { value: testValue },
    });
    fireEvent.submit(form);

    fireEvent.input(input, {
      target: { value: testValue },
    });
    fireEvent.submit(form);

    expect(screen.getAllByText("Gogeta").length).toBe(1);
  });
});
```

### 8.15 Código fuente de la sección

Aquí les dejo el código fuente de la secció por si la llegan a necesitar o comparar contra la mía

[**Github - Fin sección 8**](https://github.com/Klerith/react-gif-expert/tree/fin-seccion-8)


## 🟣 9. Profundizando Hooks - Generales

### 9.1 Introducción a la sección

### 9.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Profundizar en el tema de los Hooks
- Crear otros customHooks
- useState
- useCounter - Personalizado
- useEffect y sus precauciones
- useRef
- useFetch - Personalizado + optimizaciones
- useLayoutEffect
- Memo
- useMemo
- useCallback

Estos son los Hooks relativamente simples, aún hay mas que explicaremos más adelante, pero en esta sección nos enfocaremos en estos trabajos y para qué nos pueden servir.

Adicionalmente estaremos dejando las bases para lo que será una sección de pruebas sumamente interesante después.

### 9.3 Inicio de proyecto - HooksApp

```bash
❯ yarn create vite
  ✔ Project name: … 05-hook-app
  ✔ Select a framework: › React 👈👀👇
  ✔ Select a variant: › React Router v7 ↗
    git   Initialize a new git repository? (recommended)
         ○ Yes  ● No 
    deps   Install dependencies with yarn? (recommended)
         ● Yes  ○ No 🔥🤔
    done   That's it!

❯ cd 05-hook-app
❯ yarn 👈👀 Parece que ya no es necesario
❯ code-insiders .
```

La estructura de archivos con los pasos anteriores cambia un poco, así que en lugar de elegir `React Router v7 ↗` como variante, elegiré `JavaScript + SWC` y veré si las configuraciones son similares o iguales a como se ha venido trabajando el curso. 

```bash
? Select a variant: › - Use arrow-keys. Return to submit.
    TypeScript
    TypeScript + SWC
    JavaScript
❯   JavaScript + SWC
    React Router v7 ↗

❯ cd 05-hook-app
❯ yarn
```

Borramos todo menos el `main`, dejamos la siguiente estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── HooksApp.jsx
│   ├── index.css
│   └── main.jsx
├── vite.config.js
└── yarn.lock
```

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import "./index.css";
import { HooksApp } from "./HooksApp";

createRoot(document.getElementById("root")).render(
  <StrictMode>{<HooksApp />}</StrictMode>
);
```

`src > HooksApp.jsx`

```jsx
export const HooksApp = () => {
  return <h1>HooksApp</h1>;
};
```

`src > index.css`

```css
body {
  padding: 20px;
}

button {
  margin-right: 10px;
}
```

`src > HooksApp.jsx`

```jsx
export const HooksApp = () => {
  return <h1>HooksApp</h1>;
};
```

`src > index.html`

```jsx
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />

    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />
    <!-- CSS 👈👀👇 -->
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
      crossorigin="anonymous"
    />
    <title>HookApp</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

[CSS Getbootstrap](https://getbootstrap.com/)

### 9.4 useState

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import { HooksApp } from "./HooksApp";
import { CounterApp } from "./01-useState/CounterApp";

import "./index.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <HooksApp />
    <CounterApp
      data={{
        value1: 10,
        value2: 20,
        value3: 30,
      }}
    />
  </StrictMode>
);
```

`src > 01-useState > CounterApp.jsx`

```jsx
import React from "react";
import { useState } from "react";

export const CounterApp = ({ data }) => {
  const [counter, setCounter] = useState(data);
  const { value1, value2, value3 } = counter;

  const handleValue1 = () => {
    // Remember that "n" is the complete object
    setCounter((n) => {
      return {
        ...n,
        // To update a value it must go at the end.
        value1: n.value1 + 1,
      };
    });

    // When destructuring, new values (value0: 0,) are added to the object, but existing values that are being updated (value1: ...) are replaced...
    console.log({
      ...counter, 👀👇 // Updated value
      value1: counter.value1 + 1, 
      value0: 0, 👈👀 // New value
    });
  };

  return (
    <>
      <h1>CounterApp: {value1}</h1>
      <h1>CounterApp: {value2}</h1>
      <h1>CounterApp: {value3}</h1>

      <hr />

      <button onClick={handleValue1}>+1</button>
    </>
  );
};
```

### 9.5 useCounter - CustomHook

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import { CounterCustomHook } from "./01-useState/CounterCustomHook";

import "./index.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <CounterCustomHook />
  </StrictMode>
);
```

`src > hooks > useCounter.js`

```jsx
import { useState } from "react";

export const useCounter = (initialValue = 10) => {
  const [counter, setCounter] = useState(initialValue);

  return {
    counter,
  };
};
```

`src > 01-useState > CounterCustomHook.jsx`

```jsx
import { useCounter } from "../hooks/useCounter";

export const CounterCustomHook = () => {
  const { counter } = useCounter();

  return (
    <>
      <h1>Counter with Hook: {counter}</h1>
      <hr />

      <button>+1</button>
      <button>Reset</button>
      <button>-1</button>
    </>
  );
};
```

### 9.6 Exponer métodos del Hook

Dato importante sobre objetos:

```js
// Representation of an object in string
const obj = {};
// undefined
obj.toString();
// '[object Object]'
```

`src > 01-useState > CounterCustomHook.jsx`

```jsx
import { useCounter } from "../hooks/useCounter";

export const CounterCustomHook = () => {
  const { counter, increase, decrease, reset } =
    useCounter();

  return (
    <>
      <h1>Counter with Hook: {counter}</h1>
      <hr />

      {/* We use () => {} not to pass the "event" to it */}
      <button onClick={() => increase(5)}>+1</button>
      <button onClick={reset}>Reset</button>
      <button onClick={() => decrease(5)}>-1</button>
    </>
  );
};
```

`src > hooks > useCounter.js`

```js
import { useState } from "react";

export const useCounter = (initialValue = 10) => {
  const [counter, setCounter] = useState(initialValue);

  const increase = (value = 1) => {
    // To use value with the data we need we must call this function using () => {}. The () must be empty.
    setCounter((v) => v + value);
  };

  const decrease = (value = 1) => {
    if (counter === 0) return;

    setCounter((v) => v - value);
  };

  const reset = () => {
    setCounter(10);
  };
  return {
    counter,
    increase,
    decrease,
    reset,
  };
};
```

### 9.7 useEffect - SimpleForm

En JavaScript, la sintaxis `[name]: value` es una forma de asignar propiedades dinámicas a un objeto. Este enfoque te permite usar una expresión, como una variable, para definir el nombre de una propiedad en lugar de escribir un nombre de propiedad literal.

1. Clave dinámica en un objeto:

En los objetos de JavaScript, normalmente asignamos propiedades con un nombre fijo:

```js
const obj = {
  fixedName: "valor fijo"
};
```

Pero con la sintaxis de corchetes `[name]`, puedes usar el valor de una expresión o variable como nombre de propiedad:

```js
const dynamicKey = "claveDinamica";
const obj = {
  [dynamicKey]: "valor dinámico"
};

console.log(obj); 
// { claveDinamica: 'valor dinámico' }
```

2. Cómo se usa:

Con variables: Puedes asignar propiedades cuyo nombre provenga de una variable.

```js
const key1 = "nombre";
const key2 = "edad";
const persona = {
  [key1]: "Juan",
  [key2]: 25
};

console.log(persona); // { nombre: 'Juan', edad: 25 }
```

En funciones o cálculos: Incluso puedes calcular dinámicamente el nombre de la propiedad.

```js
const prefix = "usuario";
const obj = {
  [${prefix}_ID]: 1234
};

console.log(obj); // { usuario_ID: 1234 }
```

3. Casos de uso comunes:

Renombrar propiedades de manera dinámica: Por ejemplo, al trabajar con datos donde los nombres de las claves cambian:

```js
const data = { oldKey: "valor" };
const newKey = "newKey";
const transformed = {
  [newKey]: data.oldKey
};

console.log(transformed); // { newKey: 'valor' }
```

Crear propiedades basadas en iteraciones:

```js
const keys = ["clave1", "clave2", "clave3"];
const obj = {};
keys.forEach((key, index) => {
  obj[`propiedad_${index}`] = key;
});

console.log(obj);
// { propiedad_0: 'clave1', propiedad_1: 'clave2', propiedad_2: 'clave3' }
```

Usar claves únicas (por ejemplo, valores de UUID o identificadores).

#### Relación con otras funcionalidades

- **Symbol como clave:** Puedes usar un `Symbol` como clave dinámica con esta sintaxis.

```js
const uniqueKey = Symbol("claveUnica");
const obj = {
  [uniqueKey]: "valor único"
};

console.log(obj); // { [Symbol(claveUnica)]: 'valor único' }
```

- **Métodos en clases:** En una clase, también puedes definir métodos dinámicos.

```js
class MyClass {
  [methodName]() {
    console.log("Método dinámico");
  }
}

const obj = new MyClass();
const methodName = "miMetodo";
obj[methodName](); // Método dinámico
```

Esta flexibilidad hace que los objetos en JavaScript sean muy versátiles y útiles en casos donde los nombres de propiedades no son conocidos de antemano o dependen de cálculos o entradas del usuario.

Ahora en nuestro proyecto:

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import { SimpleForm } from "./02-useEffect/SimpleForm";
import "./index.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <SimpleForm />
  </StrictMode>
);
```

`src > 02-useEffect > SimpleForm.jsx`

```jsx
import { useEffect, useState } from "react";

export const SimpleForm = () => {
  const [formState, setFormState] = useState({
    username: "Ghost",
    email: "ghost@gmail.com",
  });

  const { username, email } = formState;

  const handleInputChange = ({ target }) => {
    const { value, name } = target;
    console.log(value, name);

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  useEffect(() => {
    console.log("useEffect called");
  });

  return (
    <>
      <h1>SimpleForm</h1>
      <hr />
      <input
        type="text"
        placeholder="Search something"
        value={username}
        name="username"
        onChange={handleInputChange}
      />

      <input
        type="email"
        placeholder="test@gmail.com"
        value={email}
        name="email"
        onChange={handleInputChange}
      />
    </>
  );
};
```

### 9.8 Dependencias del useEffect

`src > 02-useEffect > SimpleForm.jsx`

```jsx
import { useEffect, useState } from "react";

export const SimpleForm = () => {
  const [formState, setFormState] = useState({
    username: "Ghost",
    email: "ghost@gmail.com",
  });

  const { username, email } = formState;

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  useEffect(() => {
    console.log("useEffect called");
    // The [] is called only once
  }, []); 👈👀

  useEffect(() => {
    console.log("formState called");
    // Runs every time the formState changes
  }, [formState]); 👈👀

  useEffect(() => {
    console.log("email modified");
  }, [email]); 👈👀

  return (
    <>
      <h1>SimpleForm</h1>
      <hr />
      <input
        type="text"
        placeholder="Search something"
        value={username}
        name="username"
        onChange={handleInputChange}
      />

      <input
        type="email"
        placeholder="test@gmail.com"
        value={email}
        name="email"
        onChange={handleInputChange}
      />
    </>
  );
};
```

### 9.9 useEffect unmount - Cleanup

En React, el hook `useEffect` permite realizar efectos secundarios en componentes funcionales. Estos efectos secundarios pueden incluir la manipulación del DOM, la realización de peticiones HTTP, la configuración de suscripciones, entre otras acciones. Entender cómo montar y desmontar un `useEffect` es crucial para gestionar estos efectos secundarios de manera eficiente.

#### Montaje de `useEffect`

El `useEffect` se ejecuta después de que el componente se monta y después de cada actualización. La estructura básica de `useEffect` es la siguiente:

```jsx
import React, { useEffect } from 'react';

const MiComponente = () => {
  useEffect(() => {
    // Código que se ejecuta al montar el componente

    return () => {
      // Código que se ejecuta al desmontar el componente (opcional)
    };
  }, []); // La lista de dependencias vacía asegura que esto solo se ejecute al montar y desmontar
}
```

- **Montaje**: La función que se pasa a `useEffect` se ejecuta después de que el componente se monta. Esto es útil para inicializar datos, configurar suscripciones, iniciar temporizadores, etc.

#### Desmontaje de `useEffect`

Para limpiar efectos secundarios y evitar posibles fugas de memoria, `useEffect` puede devolver una función de limpieza. Esta función se ejecutará cuando el componente se desmonte o cuando cambien las dependencias del efecto (si las hay).

```jsx
import React, { useEffect } from 'react';

const MiComponente = () => {
  useEffect(() => {
    // Código que se ejecuta al montar el componente
    console.log('Componente montado');

    return () => {
      // Código que se ejecuta al desmontar el componente
      console.log('Componente desmontado');
    };
  }, []); // La lista de dependencias vacía asegura que esto solo se ejecute al montar y desmontar
}
```

En este ejemplo, la función de limpieza dentro del `return` se ejecuta cuando el componente se desmonta.

#### Dependencias en `useEffect`

Puedes especificar dependencias para el `useEffect` en el segundo argumento, que es un array. El efecto se volverá a ejecutar solo cuando alguna de estas dependencias cambie.

```jsx
import React, { useEffect, useState } from 'react';

const MiComponente = () => {
  const [contador, setContador] = useState(0);

  useEffect(() => {
    console.log('El contador ha cambiado:', contador);

    return () => {
      console.log('Limpiando efecto del contador:', contador);
    };
  }, [contador]); // El efecto se ejecutará cuando 'contador' cambie
}
```

#### Ejemplo Completo

```jsx
import React, { useEffect, useState } from 'react';

const Temporizador = () => {
  const [segundos, setSegundos] = useState(0);

  useEffect(() => {
    const intervalo = setInterval(() => {
      setSegundos(prevSegundos => prevSegundos + 1);
    }, 1000);

    return () => {
      clearInterval(intervalo);
    };
  }, []);

  return (
    <div>
      Segundos: {segundos}
    </div>
  );
}

export default Temporizador;
```

En este ejemplo:

1. El `useEffect` configura un intervalo que incrementa el estado `segundos` cada segundo.
2. La función de limpieza devuelve `clearInterval` para detener el intervalo cuando el componente se desmonte.

Este patrón asegura que los efectos secundarios se gestionen correctamente, evitando problemas como fugas de memoria.

Espero que esto te ayude a entender cómo montar y desmontar un `useEffect` en React. Si tienes alguna pregunta adicional o necesitas más detalles, no dudes en preguntar.

Ahora en nuestro proyecto:

`src > 02-useEffect > SimpleForm.jsx`

```jsx
import { useEffect, useState } from "react";
import { Message } from "./Message";

export const SimpleForm = () => {
  const [formState, setFormState] = useState({
    username: "Ghost",
    email: "ghost@gmail.com",
  });

  const { username, email } = formState;

  const handleInputChange = ({ target }) => {
    const { value, name } = target;
    // console.log(value, name);

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  useEffect(() => {
    // console.log("useEffect called");
    // The [] is called only once
  }, []);

  useEffect(() => {
    // console.log("formState called");
    // Runs every time the formState changes
  }, [formState]);

  useEffect(() => {
    // console.log("email modified");
  }, [email]);

  return (
    <>
      <h1>SimpleForm</h1>
      <hr />
      <input
        type="text"
        placeholder="Search something"
        value={username}
        name="username"
        onChange={handleInputChange}
      />

      <input
        type="email"
        placeholder="test@gmail.com"
        value={email}
        name="email"
        onChange={handleInputChange}
      />

      {/* When it matches, the
      component is mounted, but when it no longer it
      disappears (disassembles) */}
      {username === "Ghost" && <Message /> 👈👀}
    </>
  );
};
```

`src > 02-useEffect > Message.jsx`

```jsx
import { useEffect } from "react";

export const Message = () => {
  useEffect(() => {
    console.log("Message Mounted");

    return () => {
      console.log("Message Unmounted");
    };
  }, []);

  return (
    <>
      <h3>The user already exists</h3>
    </>
  );
};
```

Si estás usando el `<StrictMode>`, notarás que el componente se monta y desmonta de primeras, es su comportamiento normal. Luego cuando ingresas el `username` que coincide se monta el componente `Message` y cuando no coincide se desmonta.

[StrictMode](https://react.dev/reference/react/StrictMode)

### 9.10 useEffect - Precauciones

En el ejemplo que veremos, el `useEffect` se utiliza para registrar un evento de movimiento del ratón (`mousemove`) y actualizar las coordenadas (`coords`) en el estado del componente. 

A continuación, se mencionan algunas precauciones importantes que debes tener en cuenta:

#### 1. Limpieza del Efecto

Es crucial que el `useEffect` limpie el evento registrado cuando el componente se desmonte para evitar fugas de memoria.

```jsx
return () => {
  window.removeEventListener("mousemove", onMouseMove);
};
```

#### 2. Dependencias del `useEffect`

En este caso, el array de dependencias es vacío (`[]`), lo que significa que el efecto solo se ejecutará una vez cuando el componente se monte y la limpieza se ejecutará cuando el componente se desmonte. Esto es apropiado para este escenario, ya que no necesitas volver a ejecutar el efecto en respuesta a cambios de estado o props.

#### 3. Funcionamiento Correcto del Manejador de Eventos

Asegúrate de que el manejador de eventos `onMouseMove` esté correctamente definido y funcione como se espera. En este ejemplo de código, se está utilizando la desestructuración de objetos para obtener las coordenadas `x` y `y` del evento del ratón:

```jsx
const onMouseMove = ({ x, y }) => {
  setCoords({ x, y });
};
```

Asegura que las coordenadas se actualicen adecuadamente.

#### 4. Renderizado y Optimización

Cada vez que el estado `coords` se actualiza, el componente `Message` se volverá a renderizar. Esto es deseable en este caso, ya que se desea mostrar las coordenadas actualizadas en tiempo real. Sin embargo, es importante ser consciente de que actualizaciones frecuentes del estado pueden afectar el rendimiento en componentes más complejos.

#### 5. Uso del Estado

En tu componente, `coords` se utiliza para almacenar y mostrar las coordenadas del ratón en tiempo real:

```jsx
return (
  <>
    <h3>The user already exists</h3>
    {JSON.stringify(coords)}
  </>
);
```

Permite ver las coordenadas del ratón en el renderizado del componente.

#### 6. Manejo de Posibles Errores

Considera manejar posibles errores o situaciones inesperadas, como la ausencia de `x` e `y` en el evento del ratón. Aunque es raro, puede ser útil tener una verificación adicional:

```jsx
const onMouseMove = (event) => {
  const { x, y } = event;
  if (typeof x === 'number' && typeof y === 'number') {
    setCoords({ x, y });
  }
};
```

Ahora en nuestro código:

`src > 02-useEffect > Message.jsx`

```jsx
import { useEffect, useState } from "react";

export const Message = () => {
  const [coords, setCoords] = useState({ x: 0, y: 0 });

  useEffect(() => {
    const onMouseMove = ({ x, y } 👈👀/*event*/) => {
      // const coords = { x, y };
      setCoords({ x, y });
    };

    window.addEventListener("mousemove", onMouseMove);
    // console.log("Message Mounted");

    return () => { 👈👀👇
      window.removeEventListener("mousemove", onMouseMove);
      // console.log("Message Unmounted");
    };
  }, []);

  return (
    <>
      <h3>The user already exists</h3>
      {JSON.stringify(coords)} 👈👀
    </>
  );
};
```

### 9.11 Formulario con custom Hook

`src > 02-useEffect > FormCustomHook.jsx`

```jsx
import { useForm } from "../hooks/useForm";

export const FormCustomHook = () => {
  const { username, email, password, handleInputChange } =
    useForm({
      username: "",
      email: "",
      password: "",
    });

  return (
    <>
      <h1>Form with Custom Hooks</h1>
      <hr />
      <input
        type="text"
        placeholder="Search something"
        value={username}
        name="username"
        onChange={handleInputChange}
      />
      <input
        type="email"
        placeholder="test@gmail.com"
        value={email}
        name="email"
        onChange={handleInputChange}
      />

      <input
        type="password"
        placeholder="Password"
        value={password}
        name="password"
        onChange={handleInputChange}
      />
    </>
  );
};
```

`src > hooks > useForm.jsx`

```jsx
import { useState } from "react";

export const useForm = (initialForm = {}) => {
  const [formState, setFormState] = useState(initialForm);

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  return {
    ...formState,
    formState,
    handleInputChange,
  };
};
```

### 9.12 Tarea - Implementar funcionalidad de Reset

`src > 02-useEffect > FormCustomHook.jsx`

```jsx
import { useForm } from "../hooks/useForm";

export const FormCustomHook = () => {
  const {
    username,
    email,
    password,
    handleInputChange,
    handleResetForm,
  } = useForm({
    username: "",
    email: "",
    password: "",
  });

  return (
    <>
      <h1>Form with Custom Hooks</h1>
      <hr />
      <input
        type="text"
        placeholder="Search something"
        value={username}
        name="username"
        onChange={handleInputChange}
      />
      <input
        type="email"
        placeholder="test@gmail.com"
        value={email}
        name="email"
        onChange={handleInputChange}
      />

      <input
        type="password"
        placeholder="Password"
        value={password}
        name="password"
        onChange={handleInputChange}
      />

      <button onClick={handleResetForm}👈👀>Delete</button>
    </>
  );
};
```

`src > hooks > useForm.jsx`

```jsx
import { useState } from "react";

export const useForm = (initialForm = {}) => {
  const [formState, setFormState] = useState(initialForm);

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  const handleResetForm = () => {
    setFormState(initialForm); 👈👀
  };

  return {
    ...formState,
    formState,
    handleInputChange,
    handleResetForm, 👈👀
  };
};
```

[React hook form](https://react-hook-form.com/)

### 9.13 useFetch - CustomHook


`src > 03-examples > MultipleCustomHook.jsx`

```jsx
import React from "react";
import { useFetch } from "../hooks";👈👀 // Barril

export const MultipleCustomHook = () => {
  useFetch();

  return <div>MultipleCustomHook</div>;
};
```

`src > hooks > useFetch.js`

```js
import { useEffect, useState } from "react";

export const useFetch = () => {
  const [state, setState] = useState({
    data: null,
    isLoading: true,
    hasError: false,
    error: null,
  });

  useEffect(() => {
    getFetch();
  }, []);

  const getFetch = async () => {
    const response = await fetch(
      "https://pokeapi.co/api/v2/pokemon/1" 👈👀
    );
    const data = await response.json();

    console.log(data);
  };

  return {
    data: state.data,
    isLoading: state.isLoading,
    hasError: state.hasError,
  };
};
```

Archivo Barril:
`src/hooks/index.js`

```js
export * from "./useFetch";
```

[Poke API](https://pokeapi.co/)

### 9.14 Parametrizar y consumir nuestro custom Hook

`src > 03-examples > MultipleCustomHook.jsx`

```jsx
import React from "react";
import { useFetch } from "../hooks";

export const MultipleCustomHook = () => {
  const { data, hasError, isLoading } = useFetch(
    "https://pokeapi.co/api/v2/pokemon/1"
  );

  return (
    <>
      <h1>Pokemon information</h1>
      <hr />

      {isLoading && <p>Loading...</p>}

      {/* <pre>{JSON.stringify(data, null, 2)}</pre> */}

      {/* If we have data "?"" shows the name */}
      <h2>{data?.name}</h2> 👈👀
    </>
  );
};
```

`src > hooks > useFetch.js`

```js
import { useEffect, useState } from "react";

export const useFetch = (url) => {
  const [state, setState] = useState({
    data: null,
    isLoading: true,
    hasError: false,
    error: null,
  });

  useEffect(() => {
    getFetch();
  }, [url]);

  const setLoadingState = () => {
    setState({ 👈👀👇
      data: null,
      isLoading: true,
      hasError: false,
      error: null,
    });
  };

  const getFetch = async () => {
    // Every time you change the url the state must be without data
    setLoadingState();

    const response = await fetch(url);
    // Sleep
    await new Promise((resolve) =>
      setTimeout(resolve, 1500)
    );

    if (!response.ok) {
      setState({
        data: null,
        isLoading: false,
        hasError: true,
        error: {
          code: response.status,
          message: response.statusText,
        },
      });

      return;
    }

    const data = await response.json();

    setState({
      data: data,
      isLoading: false,
      hasError: false,
      hasError: false,
      error: null,
    });

    // Cache management

  };

  return {
    data: state.data,
    isLoading: state.isLoading,
    hasError: state.hasError,
  };
};
```

### 9.15 useFetch + useCounter

`src > 03-examples > MultipleCustomHook.jsx`

```jsx
import React from "react";
import { useFetch } from "../hooks";
import { useCounter } from "../hooks/useCounter";
import { LoadingMessage } from "./LoadingMessage";
import { PokemonCard } from "./PokemonCard";

export const MultipleCustomHook = () => {
  const { counter, increase, decrease, reset } =
    useCounter(1);
  const { data, hasError, isLoading } = useFetch(
    `https://pokeapi.co/api/v2/pokemon/${counter}`
  );

  return (
    <>
      <h1>Pokemon information</h1>
      <hr />

      {isLoading ? (
        <LoadingMessage />
      ) : (
        <PokemonCard
          id={data.id}
          name={data.name}
          sprites={[data.sprites]}
        />
      )}

      <button
        onClick={() => (counter > 1 ? decrease() : null)}
      >
        Previous
      </button>
      <button onClick={() => increase()}>Next</button>
    </>
  );
};
```

`src > 03-examples > LoadingMessage.jsx`

```jsx
export const LoadingMessage = () => {
  return (
    <section>
      <h1>Loading component...</h1>
    </section>
  );
};
```

`src > 03-examples > PokemonCard.jsx`

```jsx
export const PokemonCard = ({ id, name, sprites = [] }) => {
  return (
    <section>
      <h2>
        #{id} - {name}
      </h2>

      {sprites.map((img) => {
        return (
          <div key={id}>
            <img src={img.front_shiny} alt={name} />
            <img src={img.front_default} alt={name} />
            <img src={img.back_shiny} alt={name} />
            <img src={img.back_default} alt={name} />
          </div>
        );
      })}
    </section>
  );
};
```

### 9.16 Incorporar caché

`localStorage` es una característica de JavaScript que permite almacenar datos de forma persistente en el navegador del usuario. Los datos almacenados en `localStorage` no tienen fecha de caducidad y permanecen disponibles incluso después de cerrar el navegador. Aquí te explico cómo usarlo con ejemplos breves:

#### Guardar Datos

Para guardar datos en `localStorage`, usas el método `setItem`:

```javascript
localStorage.setItem('clave', 'valor');
```

**Ejemplo:**

```javascript
localStorage.setItem('name', 'ghost');
```

#### Obtener Datos

Para obtener datos de `localStorage`, usas el método `getItem`:

```javascript
var valor = localStorage.getItem('clave');
```

**Ejemplo:**

```javascript
var nombre = localStorage.getItem('name'); // 'ghost'
console.log(name);
```

#### Eliminar Datos

Para eliminar un ítem específico de `localStorage`, usas el método `removeItem`:

```javascript
localStorage.removeItem('clave');
```

**Ejemplo:**

```javascript
localStorage.removeItem('name');
```

#### Limpiar Todo

Para limpiar todos los datos almacenados en `localStorage`, usas el método `clear`:

```javascript
localStorage.clear();
```

**Ejemplo:**

```javascript
localStorage.clear();
```

#### Almacenar y Recuperar Objetos

`localStorage` solo almacena cadenas de texto. Para almacenar objetos, debes convertirlos a JSON con `JSON.stringify` y luego convertirlos de nuevo con `JSON.parse` al recuperarlos.

**Guardar un objeto:**

```javascript
var usuario = { nombre: 'Ale', edad: 20 };
localStorage.setItem('usuario', JSON.stringify(usuario));
```

**Obtener un objeto:**

```javascript
var usuario = JSON.parse(localStorage.getItem('usuario'));
console.log(usuario.nombre); // 'Ale'
console.log(usuario.edad);  // 20
```

Estos son los conceptos básicos para usar `localStorage` en JavaScript.

Ahora en nuestro proyecto:

📌 En el navegador nos dirigimos a los `DevTools` y entramos en `Network` y nos fijamos que en `Filter` no haya nada, limpiamos dando clic en el icono 🚫, ahora presionamos el icono 🔘 de la izquierda y por último seleccionamos `All`. Ahora puedes dar clic en `Next` para visualizar el nuevo Pokémon.

`src > hooks > useFetch.js`

```js
import { useEffect, useState } from "react";

const localCache = {}; 👈👀

export const useFetch = (url) => {
  const [state, setState] = useState({
    data: null,
    isLoading: true,
    hasError: false,
    error: null,
  });

  useEffect(() => {
    getFetch();
  }, [url]);

  const setLoadingState = () => {
    setState({
      data: null,
      isLoading: true,
      hasError: false,
      error: null,
    });
  };

  const getFetch = async () => {
    if (localCache[url]) { 👈👀
      console.log("Using cache");

      setState({
        data: localCache[url],
        isLoading: false,
        hasError: false,
        error: null,
      });

      return;
    }

    // Every time you change the url the state must be without data
    setLoadingState();

    const response = await fetch(url);
    // Sleep
    await new Promise((resolve) =>
      setTimeout(resolve, 1500)
    );

    if (!response.ok) {
      setState({
        data: null,
        isLoading: false,
        hasError: true,
        error: {
          code: response.status,
          message: response.statusText,
        },
      });

      return;
    }

    const data = await response.json();

    setState({
      data: data,
      isLoading: false,
      hasError: false,
      hasError: false,
      error: null,
    });

    // Cache management 👈👀
    localCache[url] = data;
  };

  return {
    data: state.data,
    isLoading: state.isLoading,
    hasError: state.hasError,
  };
};
```

 En este ejemplo básicamente la variable `localCache` es un objeto que se utiliza para almacenar los datos de las respuestas de las solicitudes.
 
 Cuando se hace una solicitud a una URL, primero se verifica si los datos de esa URL ya están en el `localCache` y si están, se utilizan esos datos y no se hace la solicitud `fetch`, si no están, entonces simplemente se hace la solicitud, se guardan los datos en `localCache` y luego se utilizan.

📌 Cuando usas corchetes con un objeto, lo que está entre corchetes es la llave del objeto.

```js
const localCache = {};
// undefined

localCache["One"] = 1
localCache["Two"] = 2

console.log(localCache)
// {One: 1, Two: 2}
```

- [Tanstack](https://tanstack.com/query/latest)
- [Curso gratuito: React Query](https://fernando-herrera.com/course/react-query/)

### 9.17 useRef - Primer uso

`src > main`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import "./index.css";
import { FocusScreen } from "./04-useRef/FocusScreen";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <FocusScreen />
  </StrictMode>
);
```

`src > 04-useRef > FocusScreen.jsx`

```jsx
import { useRef } from "react";

export const FocusScreen = () => {
  const focusRef = useRef(); 👈👀

  const handleFocus = () => {
    // document.querySelector("input").focus();
    focusRef.current.select(); 👈👀
  };

  return (
    <>
      <h1>FocusScreen</h1>
      <hr />
      <input
        ref={focusRef} 👈👀
        type="text"
        placeholder="Enter your name"
      />

      <button onClick={handleFocus}👈👀>Set focus</button>
    </>
  );
};
```

- [useRef](https://react.dev/reference/react/useRef)
- [Apuntes useRef](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/YouTube/react-js-desde-cero.md#24-useref)
- [[react-js-desde-cero#**24.** useRef()]]

### 9.18 useLayoutEffect

`useLayoutEffect` es un hook en React que se utiliza para ejecutar efectos de manera sincrónica después de que todas las mutaciones del DOM hayan sido realizadas, pero antes de que el navegador haya tenido la oportunidad de pintar (renderizar) la pantalla. Esto lo hace útil para realizar tareas que necesiten medir el DOM y aplicar cambios antes de que el navegador lo pinte, asegurando que los cambios sean visibles en el mismo ciclo de renderizado.

```javascript
useLayoutEffect(() => {
  // Código del efecto
  return () => {
    // Código de limpieza (opcional)
  };
}, [dependencias]);
```

#### Parámetros

- **`efecto`:** Una función que contiene el código del efecto a ejecutar. Esta función puede opcionalmente devolver una función de limpieza que se ejecutará cuando el componente se desmonte o antes de ejecutar el efecto siguiente vez que las dependencias cambien.
- **`dependencias`:** Una lista de dependencias que, cuando cambian, hacen que el efecto se vuelva a ejecutar. Si se omite, el efecto se ejecutará en cada renderizado.

#### Ejemplo Práctico

Supongamos que tenemos un componente que necesita calcular el tamaño de un elemento del DOM después de que se haya renderizado y ajustar su tamaño en consecuencia.

```javascript
import React, { useLayoutEffect, useRef, useState } from 'react';

function ComponenteEjemplo() {
  const ref = useRef(null);
  const [ancho, setAncho] = useState(0);

  useLayoutEffect(() => {
    // Medir el ancho del elemento
    const elemento = ref.current;
    if (elemento) {
      setAncho(elemento.offsetWidth);
    }
  }, []); // Solo se ejecuta una vez, después del primer renderizado

  return (
    <div>
      <div ref={ref} style={{ width: '50%' }}>
        Este es el elemento a medir
      </div>
      <p>El ancho del elemento es: {ancho}px</p>
    </div>
  );
}

export default ComponenteEjemplo;
```

#### Cuándo Usar `useLayoutEffect`

- **Medición del DOM:** Cuando necesitas medir el DOM después de que React haya realizado todas las actualizaciones, pero antes de que el navegador pinte la pantalla.
- **Sincronización del DOM:** Cuando necesitas sincronizar el DOM con algunos cálculos o ajustes que deben ser visibles inmediatamente después del renderizado.
- **Efectos que bloquean el pintado:** Ten en cuenta que `useLayoutEffect` puede bloquear el pintado del navegador, lo que puede causar problemas de rendimiento si se usa en exceso.

#### Diferencia con `useEffect`

La principal diferencia entre `useLayoutEffect` y `useEffect` es el momento en que se ejecutan. `useEffect` se ejecuta después de que el navegador haya pintado la pantalla, mientras que `useLayoutEffect` se ejecuta antes de que el navegador pinte la pantalla. Por lo tanto, `useLayoutEffect` es útil para realizar tareas que necesitan ocurrir antes del pintado del navegador.

En resumen, `useLayoutEffect` se debe usar para efectos que afectan el diseño del DOM y necesitan ser aplicados antes de que el navegador lo pinte, mientras que `useEffect` es adecuado para la mayoría de los efectos secundarios que no requieren esta sincronización precisa.

#### `getBoundingClientRect`

`getBoundingClientRect` es un método que se utiliza en JavaScript y React para obtener el tamaño y la posición de un elemento en la página web. Este método devuelve un objeto `DOMRect` que proporciona información sobre las dimensiones del elemento y su posición relativa al viewport (la parte visible de la página web en el navegador).

##### Uso en JavaScript

En JavaScript, puedes usar `getBoundingClientRect` directamente en un elemento del DOM. Aquí hay un ejemplo:

```javascript
// Selecciona el elemento
const element = document.querySelector('#miElemento');

// Obtiene el rectángulo que describe el tamaño y la posición del elemento
const rect = element.getBoundingClientRect();

console.log(rect);
```

El objeto `rect` tiene las siguientes propiedades:

- `x` y `y`: Las coordenadas X e Y del borde superior izquierdo del elemento en relación con el viewport.
- `width` y `height`: El ancho y la altura del elemento.
- `top`, `right`, `bottom` y `left`: Las posiciones del borde del elemento en relación con el viewport.

##### Uso en React

En React, necesitas primero obtener una referencia al elemento del DOM usando el hook `useRef` o la API de referencias de React. Aquí hay un ejemplo usando un componente funcional con hooks:

```jsx
import React, { useRef, useEffect } from 'react';

const MiComponente = () => {
  const miElementoRef = useRef(null);

  useEffect(() => {
    const rect = miElementoRef.current.getBoundingClientRect();
    console.log(rect);
  }, []);

  return (
    <div ref={miElementoRef} id="miElemento">
      Contenido del elemento
    </div>
  );
};

export default MiComponente;
```

En este ejemplo:

1. Se crea una referencia usando `useRef`.
2. Se asigna la referencia al elemento `div` con la propiedad `ref`.
3. En el hook `useEffect`, que se ejecuta después de que el componente se ha montado, se llama a `getBoundingClientRect` en el elemento referenciado y se registra el resultado en la consola.

##### Ejemplo Práctico

Supongamos que deseas mover un elemento a una posición específica en la página basada en su posición actual. Puedes hacerlo utilizando `getBoundingClientRect`:

```jsx
import React, { useRef, useEffect } from 'react';

const MoverElemento = () => {
  const elementoRef = useRef(null);

  useEffect(() => {
    const rect = elementoRef.current.getBoundingClientRect();
    // Mueve el elemento 50 píxeles hacia abajo
    elementoRef.current.style.transform = `translateY(${rect.top + 50}px)`;
  }, []);

  return (
    <div ref={elementoRef} style={{ position: 'absolute' }}>
      ¡Muéveme!
    </div>
  );
};

export default MoverElemento;
```

En este ejemplo, el elemento se mueve 50 píxeles hacia abajo desde su posición actual utilizando las coordenadas obtenidas con `getBoundingClientRect`.

##### Conclusión

El método `getBoundingClientRect` es una herramienta poderosa para trabajar con la posición y el tamaño de los elementos del DOM, tanto en JavaScript como en React. Permite obtener información precisa sobre la ubicación de un elemento en la página, lo cual es esencial para muchas tareas, como la creación de interfaces de usuario dinámicas y responsivas.

Ahora en nuestro proyecto:

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import "./index.css";
import { Layout } from "./05-useLayoutEffect/Layout";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <Layout />
  </StrictMode>
);
```

`src > 05-useLayoutEffect > Layout.jsx`

```jsx
import React from "react";
import { useFetch } from "../hooks";
import { useCounter } from "../hooks/useCounter";
import { PokemonCard } from "../03-examples/PokemonCard";
import { LoadingMessage } from "../03-examples/LoadingMessage";

export const Layout = () => {
  const { counter, increase, decrease, reset } =
    useCounter(1);
  const { data, hasError, isLoading } = useFetch(
    `https://pokeapi.co/api/v2/pokemon/${counter}`
  );

  return (
    <>
      <h1>Pokemon information</h1>
      <hr />

      {isLoading ? (
        <LoadingMessage />
      ) : (
        <PokemonCard
          id={data.id}
          name={data.name}
          sprites={[data.sprites]}
        />
      )}

      <button
        onClick={() => (counter > 1 ? decrease() : null)}
      >
        Previous
      </button>
      <button onClick={() => increase()}>Next</button>
    </>
  );
};
```

`src > 03-examples > PokemonCard.jsx`

```jsx
import { useLayoutEffect, useRef, useState } from "react";

export const PokemonCard = ({ id, name, sprites = [] }) => {
  const h2Ref = useRef();
  const [boxSize, setBoxSize] = useState({
    width: 0,
    height: 0,
  });

  useLayoutEffect(() => {
    const { height, width } =
      h2Ref.current.getBoundingClientRect();

    setBoxSize({ height, width });
  }, [name]);

  return (
    <section>
      <h2 ref={h2Ref}>
        #{id} - {name}
      </h2>

      {sprites.map((img) => {
        return (
          <div key={id}>
            <img src={img.front_shiny} alt={name} />
            <img src={img.front_default} alt={name} />
            <img src={img.back_shiny} alt={name} />
            <img src={img.back_default} alt={name} />
          </div>
        );
      })}

      <pre>{JSON.stringify(boxSize)}</pre>
    </section>
  );
};
```

[useLayoutEffect](https://react.dev/reference/react/useLayoutEffect)

### 9.19 Memo - Método de React

`memo` es una función en React que se utiliza para optimizar el rendimiento de los componentes funcionales. Esta función memoriza el resultado de la renderización de un componente y lo vuelve a usar en las renderizaciones subsiguientes, siempre y cuando las props del componente no hayan cambiado. Esto evita renderizaciones innecesarias y puede mejorar el rendimiento de la aplicación.

```javascript
import React, { memo } from 'react';

const MiComponente = memo((props) => {
  // Renderizar el componente utilizando las props
  return <div>{props.valor}</div>;
});
```

#### Parámetros

- **`Componente`:** El componente funcional que deseas memorizar.
- **`areEqual` (opcional):** Una función de comparación personalizada que se usa para verificar si las props han cambiado. Si no se proporciona, `memo` usará una comparación superficial (shallow comparison).

#### Ejemplo Práctico

Supongamos que tenemos un componente que muestra un valor y queremos evitar que se vuelva a renderizar a menos que cambie el valor de la prop `valor`.

```javascript
import React, { memo, useState } from 'react';

const ComponenteValor = memo(({ valor }) => {
  console.log('Renderizando ComponenteValor');
  return <div>Valor: {valor}</div>;
});

function App() {
  const [valor, setValor] = useState(0);
  const [otroValor, setOtroValor] = useState(0);

  return (
    <div>
      <button onClick={() => setValor(valor + 1)}>Incrementar Valor</button>
      <button onClick={() => setOtroValor(otroValor + 1)}>Incrementar Otro Valor</button>
      <ComponenteValor valor={valor} />
      <div>Otro Valor: {otroValor}</div>
    </div>
  );
}

export default App;
```

En este ejemplo, `ComponenteValor` se renderiza solo cuando cambia la prop `valor`. Cuando el botón "Incrementar Otro Valor" se hace clic, `ComponenteValor` no se vuelve a renderizar, lo que mejora el rendimiento de la aplicación.

#### Uso de `memo` con Función de Comparación Personalizada

A veces, las props pueden ser objetos o arrays, y una comparación superficial podría no ser suficiente. En esos casos, puedes proporcionar una función de comparación personalizada.

```javascript
const ComponenteValor = memo(
  ({ objeto }) => {
    console.log('Renderizando ComponenteValor');
    return <div>Propiedad: {objeto.propiedad}</div>;
  },
  (prevProps, nextProps) => {
    // Comparación profunda de las props
    return prevProps.objeto.propiedad === nextProps.objeto.propiedad;
  }
);
```

#### Cuándo Usar `memo`

- **Componentes Puros:** `memo` es útil para componentes que son puros, es decir, su renderización depende exclusivamente de sus props.
- **Renderización Costosa:** Si tienes un componente que realiza cálculos intensivos o tiene un proceso de renderización costoso, `memo` puede ayudar a reducir el número de renderizaciones.
- **Evitación de Renderización Innecesaria:** En general, si notas que un componente se está renderizando más veces de las necesarias, `memo` puede ser una solución.

#### Limitaciones de `memo`

- **Comparación Superficial:** La comparación por defecto de `memo` es superficial, lo que significa que solo compara los valores primitivos de las props. Si las props son objetos complejos, puede que necesites una comparación más profunda.
- **Overhead Adicional:** En algunos casos, el overhead de la comparación de props puede ser mayor que el costo de volver a renderizar el componente. Es importante medir el rendimiento y asegurarse de que `memo` realmente mejora la eficiencia.

En resumen, `memo` es una herramienta poderosa para optimizar la renderización de componentes funcionales en React, especialmente en casos donde las props no cambian frecuentemente y la renderización es costosa.

En nuestro proyecto:

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import "./index.css";
import { Memorize } from "./06-memos/Memorize";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <Memorize />
  </StrictMode>
);
```

`src > 06-memos > Small.jsx`

```jsx
import { memo } from "react";

export const Small = 🔥memo(({ value }) => {
  console.log("I went back to drawing :/");

  return <small>{value}</small>;
})👈👀;

// CRA usa import React from ...
// const Small = React.memo(() => {})
```

`src > 06-memos > Memorize.jsx`

```jsx
import { useState } from "react";
import { useCounter } from "../hooks/useCounter";
import { Small } from "./Small";

export const Memorize = () => {
  const { counter, increase } = useCounter(0);
  const [show, setShow] = useState(true);

  return (
    <div>
      <h1>
        Counter: <Small value={counter} />
      </h1>
      <hr />
      <button onClick={() => increase()}>+1</button>

      <button onClick={() => setShow(!show)}>
        Show/Hide {JSON.stringify(show)}
      </button>
    </div>
  );
};
```

### 9.20 useMemo

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import "./index.css";
import { MemorizeHook } from "./06-memos/MemorizeHook";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <MemorizeHook />
  </StrictMode>
);
```

`src > 06-memos > MemorizeHook.jsx`

```jsx
import { useMemo, useState } from "react";
import { useCounter } from "../hooks/useCounter";

const heavyStuff = (iterationNumber = 100) => {
  for (let i = 0; i < iterationNumber; i++) {
    console.log(`Ahí vamos...`);
  }

  return `${iterationNumber} iteraciones realizadas!!`;
};

export const MemorizeHook = () => {
  const { counter, increase } = useCounter(0);
  const [show, setShow] = useState(true);

  const memorizedValue = useMemo(
    () => heavyStuff(counter),
    [counter]
  );

  return (
    <div>
      <h1>
        Counter: <small>{counter}</small>
      </h1>
      <hr />
      <h4>{memorizedValue}</h4>

      <button onClick={() => increase()}>+1</button>

      <button onClick={() => setShow(!show)}>
        Show/Hide {JSON.stringify(show)}
      </button>
    </div>
  );
};
```

- [useMemo](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/YouTube/react-js-desde-cero.md#25-usememo)
- [[react-js-desde-cero#**25.** useMemo()]]

### 9.21 useCallback

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import "./index.css";
import { CallbackHook } from "./06-memos/CallbackHook";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <CallbackHook />
  </StrictMode>
);
```

`src > 06-memos > ShowIncrement.jsx`

```jsx
import { memo } from "react";

export const ShowIncrement = memo(({ increase }) => {
  console.log("I generated myself again.");

  return (
    <button
      onClick={() => {
        increase();
      }}
    >
      Increase
    </button>
  );
});
```

`src > 06-memos > CallbackHook.jsx`

```jsx
import { useCallback, useState } from "react";
import { ShowIncrement } from "./ShowIncrement";

export const CallbackHook = () => {
  const [counter, setCounter] = useState(10);

  const handleIncrease = useCallback(() => {
    setCounter((c) => c + 1);
  }, []);

  return (
    <>
      <h1>useCallback Hook: {counter}</h1>
      <hr />

      <ShowIncrement increase={handleIncrease} />
    </>
  );
};
```

[Apuntes: useCallback](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/YouTube/react-js-desde-cero.md#26-usecallback)

### 9.22 useCallback con argumentos

`src > 06-memos > ShowIncrement.jsx`

```jsx
import { memo } from "react";

export const ShowIncrement = memo(({ increase }) => {
  console.log("I generated myself again.");

  return (
    <button
      onClick={() => {
        increase(5); 👈👀
      }}
    >
      Increase
    </button>
  );
});
```

`src > 06-memos > CallbackHook.jsx`

```jsx
import { useCallback, useState } from "react";
import { ShowIncrement } from "./ShowIncrement";

export const CallbackHook = () => {
  const [counter, setCounter] = useState(10);

  const handleIncrease = useCallback((value👈👀) => {
    setCounter((c) => c + value);👈👀
  }, []);

  return (
    <>
      <h1>useCallback Hook: {counter}</h1>
      <hr />

      <ShowIncrement increase={handleIncrease} />
    </>
  );
};
```

### 9.23 Tarea Memorize

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import "./index.css";
import { Padre } from "./07-tarea-memo/Padre";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <Padre />
  </StrictMode>
);
```

`src > 07-tarea-memo > Hijo.jsx`

```jsx
import React, { memo } from "react";

export const Hijo = memo(({ numero, incrementar }) => {
  console.log("Me volví a generar :(");

  return (
    <button
      className="btn btn-primary mr-3"
      onClick={() => incrementar(numero)}
    >
      {numero}
    </button>
  );
});
```

`src > 07-tarea-memo > Padre.jsx`

```jsx
import { Hijo } from "./Hijo";
import { useCallback, useState } from "react";

export const Padre = () => {
  const numeros = [2, 4, 6, 8, 10];
  const [valor, setValor] = useState(0);

  const incrementar = useCallback((num) => {
    setValor((v) => v + num);
  }, []);

  return (
    <div>
      <h1>Padre</h1>
      <p> Total: {valor} </p>

      <hr />

      {numeros.map((n) => (
        <Hijo
          key={n}
          numero={n}
          incrementar={incrementar}
        />
      ))}
    </div>
  );
};
```

[Download task](https://import.cdn.thinkific.com/643563/courses/1901683/07tareamemo-220620-120357.zip)

### 9.24 Código fuente de la sección

Aquí les dejo el código fuente de la sección, lo pueden descargar del material adjunto o bien ir al repositorio de GitHub para tenerlo a la mano o clonarlo si lo quieren tener en su cuenta de GitHub

[**Fin sección 9 - Hooks en detalle**](https://github.com/Klerith/react-hooks/tree/fin-seccion-9)

[Fin sección 9 - Nuevo useFetch](https://github.com/Klerith/react-hooks/tree/fin-seccion-9.2)  

**Nota:**

Espero que esta sección les gustara, especialmente para entrar en calor de todo lo que podemos hacer con los Hooks de React, tanto los creados por ellos como los personalizados que podemos hacer nosotros, aún faltan más Hooks que ver...

Si el curso les está gustando, por favor, ¡no se olviden de calificar el curso y ponerme 5 estrellas! Eso me ayudaría mucho, nuevamente gracias por todo su apoyo que me permite seguir creando cursos como estos.

**atte:**

**Fernando Herrera**

## 🟣 10. Profundizando Hooks - useReducer

### 10.1 Introducción a la sección


### 10.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- useReducer
- Reducers
- Teoría de un reducer
- Aplicación de TODOs
- CRUD local

Esta es una sección dedicada a comprender el concepto de un Reducer, el cual es sumamente importante para poder entrar a Redux o bien usar el contextAPI fácilmente.

### 10.3 Introducción al concepto de un reducer

En React, un `reducer` es una función que determina cómo cambiará el estado de una aplicación en respuesta a una acción. Los `reducers` son una parte central del patrón de arquitectura Redux, pero también pueden ser utilizados con el hook `useReducer` que React proporciona para manejar el estado local del componente de una manera similar.

Un `reducer` es una función pura que toma dos argumentos:

1. **El estado actual** (o el estado anterior).
2. **Una acción**: un objeto que describe lo que sucedió y que típicamente tiene una propiedad `type` y, a veces, una `payload` que contiene los datos adicionales necesarios para realizar la actualización del estado.

La función `reducer` devuelve el nuevo estado basado en la acción que recibió.

Aquí hay un ejemplo básico de un `reducer` en React:

```javascript
const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    case 'reset':
      return { count: 0 };
    default:
      throw new Error('Acción no soportada');
  }
}
```

En este ejemplo, el `reducer` maneja tres tipos de acciones: `increment`, `decrement` y `reset`, que respectivamente incrementan, decrementan y resetean el contador.

Para usar este `reducer` en un componente con el hook `useReducer`, harías algo como esto:

```javascript
import React, { useReducer } from 'react';

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>Increment</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>Decrement</button>
      <button onClick={() => dispatch({ type: 'reset' })}>Reset</button>
    </div>
  );
}

export default Counter;
```

Aquí, `useReducer` inicializa el estado con `initialState` y retorna el estado actual y la función `dispatch`. La función `dispatch` se usa para enviar acciones al `reducer`, que actualiza el estado en consecuencia.

En resumen:

1. Es una función común y corriente.
2. Debe ser una función pura.
	1. No debe tener efectos secundarios.
	2. No debe realizar tareas asíncronas.
	3. Debe retornar siempre un nuevo estado
	4. No debe llamar al `localStorage` o `sessionStorage`.
	5. No debe requerir más que una acción que puede tener un argumento.
3. Debe de retornar un nuevo estado.
4. Usualmente, solo recibe dos argumentos.
	1. El valor inicial (initialState).
	2. La acción a ejecutar.

- [Apuntes: useReducer()](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/YouTube/react-js-desde-cero.md#28-usereducer)
- [[react-js-desde-cero#**28.** useReducer()]]

### 10.4 Continuación del Proyecto - HookApp

`src > main.jsx`

```jsx
import "./08-useReducer/intro-reducer";
```

`src > 08-useReducer > intro-reducer.js`

```js
console.log("Hi world");
```

### 10.5 Idea general de un reducer - Vía código

`src > 08-useReducer > intro-reducer.js`

```js
const initialState = [
  {
    id: 1,
    todo: "Collecting the Soul Stone",
    done: false,
  },
];

const todoReducer = (state = initialState, action = {}) => {
  if (action.type === "[TODO] add todo") {
    return [...state, action.payload];
  }
  return state;
};

let todos = todoReducer();

const newTodo = {
  id: 2,
  todo: "Collecting the power stone",
  done: false,
};

const addTodoAction = {
  type: "[TODO] add todo",
  payload: newTodo,
};

todos = todoReducer(todos, addTodoAction);

console.log({ state: todos });

// Modifying in this way is bad practice
// todos.push({
//   id: 2,
//   todo: "Collecting the power stone",
//   done: false,
// });
```

### 10.6 useReducer - Todo List

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import "./index.css";

import { TodoApp } from "./08-useReducer/TodoApp";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <TodoApp />
  </StrictMode>
);
```

`src > 08-useReducer > todoReducer.js`

```jsx
export const todoReducer = (initialState = [], action) => {
  switch (action.type) {
   🔥 case "ABC": 👈👀👇
      throw new Error(
        "Action.type = ABC isn't implemented"
      );

    default:
      return initialState;
  }
};
```

`src > 08-useReducer > TodoApp.jsx`

```jsx
import { useReducer } from "react";
import { todoReducer } from "./todoReducer";

const initialState = [
  {
    id: new Date().getTime(),
    description: "Collecting the Soul Stone",
    done: false,
  },
  {
    id: new Date().getTime() * 3,
    description: "Collecting the Soul Stone",
    done: false,
  },
];

export const TodoApp = () => {
  const [todos, dispatch] = useReducer(
    todoReducer, // List of "cases" to choose
    initialState // New incoming data
  );

  return (
    <>
      <h1>TodoApp</h1>
      <hr />
      <ul>
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3</li>
      </ul>
    </>
  );
};
```

[useReducer](https://es.react.dev/reference/react/useReducer)

### 10.7 Creando el cascarón de la lista de TODOs

`src > 08-useReducer > TodoApp.jsx`

```jsx
import { useReducer } from "react";
import { todoReducer } from "./todoReducer";

const initialState = [
  {
    id: new Date().getTime(),
    description: "Collecting the Soul Stone",
    done: false,
  },
  {
    id: new Date().getTime() * 3,
    description: "Collecting the Soul Stone",
    done: false,
  },
];

export const TodoApp = () => {
  const [todos, dispatch] = useReducer(
    todoReducer, // List of "cases" to choose
    initialState // New incoming data
  );

  return (
    <>
      <h1>
        TodoApp: 10, <small>Pending: 2</small>
      </h1>
      <hr />

      <div>
        <div>
          <ul>
            {todos.map((todo) => (
              <li key={todo.id}>
                <span>Item 1</span>
                <button>Delete</button>
              </li>
            ))}
          </ul>
        </div>

        <div>
          <h4>Add TODO</h4>
          <hr />
          <form action="">
            <input
              type="text"
              placeholder="what is to be done?"
            />
            <button type="submit">Add</button>
          </form>
        </div>
      </div>
    </>
  );
};
```

### 10.8 Tarea: Crear componentes y emitir eventos

### 10.9 Resolución de la tarea - TodoApp
`src > 08-useReducer > TodoApp.jsx`

```jsx
import { useReducer } from "react";
import { todoReducer } from "./todoReducer";
import { TodoList } from "./TodoList";
import { TodoAdd } from "./TodoAdd";

const initialState = [
  {
    id: new Date().getTime(),
    description: "Collecting the Soul Stone",
    done: false,
  },
  {
    id: new Date().getTime() * 3,
    description: "Collecting the Soul Stone",
    done: false,
  },
];

export const TodoApp = () => {
  const [todos, dispatch] = useReducer(
    todoReducer, // List of "cases" to choose
    initialState // New incoming data
  );

  const handleNewTodo = (todo) => {
    const newList = { ...todos, todo };

    return newList;
  };

  return (
    <>
      <h1>
        TodoApp: 10, <small>Pending: 2</small>
      </h1>
      <hr />

      <div>
        <div>
          <TodoList todos={todos} />
        </div>

        <div>
          <h4>Add TODO</h4>
          <hr />
          <TodoAdd updateTodos={handleNewTodo} />
        </div>
      </div>
    </>
  );
};
```

`src > 08-useReducer > TodoList.jsx`

```jsx
import React from "react";
import { TodoItem } from "./TodoItem";

export const TodoList = ({ todos }) => {
  return (
    <ul>
      {todos.map((todo) => (
        <TodoItem
          key={todo.id}
          id={todo.id}
          task={todo.description}
        />
      ))}
    </ul>
  );
};
```

`src > 08-useReducer > TodoItem.jsx`

```jsx
export const TodoItem = ({
  id = "01",
  task = "Task 01",
}) => {
  return (
    <>
      <li>
        <span>{task}</span>
        <br />
        <button>Delete</button>
      </li>
    </>
  );
};
```

`src > 08-useReducer > TodoAdd.jsx`

```jsx
import { useState } from "react";
import { useForm } from "../hooks/useForm";

export const TodoAdd = ({ updateTodos }) => {
  const {
    description, // formState Unstructured
    formState,
    handleInputChange,
    handleResetForm,
  } = useForm({
    id: new Date().getTime() * 3,
    description: "",
    done: false,
  });

  const handleSubmit = (event) => {
    event.preventDefault();

    if (description.length <= 1) return;

    updateTodos(formState);

    handleResetForm();
  };

  return (
    <form action="" onSubmit={handleSubmit}>
      <input
        type="text"
        placeholder="Enter a task"
        name="description" // [name] of useForm
        value={description}
        onChange={handleInputChange}
      />
      <button type="submit">Add</button>
    </form>
  );
};
```

Para esta clase se usó el `useForm()` de clases anteriores. Tener en cuenta que el `formState` se está enviando desestructurado, por eso podemos usar `description` directamente.

### 10.10 Agregar un nuevo TODO

`src > 08-useReducer > todoReducer.js`

```jsx
export const todoReducer = (initialState = [], action) => {
  switch (action.type) { 👈👀👇
    case "[TODO] Add Todo":
      return [...initialState, action.payload];

    default:
      return initialState;
  }
};
```

`src > 08-useReducer > TodoApp.jsx`

```jsx
import { useReducer } from "react";
import { todoReducer } from "./todoReducer";
import { TodoList } from "./TodoList";
import { TodoAdd } from "./TodoAdd";

const initialState = [
  {
    id: new Date().getTime(),
    description: "Collecting the Soul Stone",
    done: false,
  },
  {
    id: new Date().getTime() * 3,
    description: "Collecting the Soul Stone",
    done: false,
  },
];

export const TodoApp = () => {
  const [todos, dispatch] = useReducer(
    todoReducer, // List of "cases" to choose
    initialState // New incoming data
  );

  const handleNewTodo = (todo) => {
    const action = { 👈👀👇
      type: "[TODO] Add Todo",
      payload: todo,
    };

    dispatch(action); 👈👀
  };

  return (
    <>
      <h1>
        TodoApp: 10, <small>Pending: 2</small>
      </h1>
      <hr />

      <div>
        <div>
          <TodoList todos={todos} />
        </div>

        <div>
          <h4>Add TODO</h4>
          <hr />
          <TodoAdd updateTodos={handleNewTodo} />
        </div>
      </div>
    </>
  );
};
```

### 10.11 Guardar y Leer TODOs en LocalStorage

En React, el hook `useReducer` acepta un tercer parámetro opcional llamado `init`. Este es útil para inicializar el estado de manera más compleja o diferida.

#### Sintaxis de `useReducer`:

```jsx
const [state, dispatch] = useReducer(reducer, initialState, init);
```

#### ¿Cómo funciona cada parámetro?

1. **`reducer`**: Una función pura que toma el estado actual y una acción, y devuelve un nuevo estado.
2. **`initialState`**: Valor inicial del estado.
3. **`init`** (opcional): Una función de inicialización que transforma el `initialState` antes de usarlo.

El `init` se utiliza cuando necesitas inicializar el estado de forma más compleja o cuando `initialState` es solo un valor básico que necesita ser transformado o calculado. Esto es útil en casos como:

- Cargar un estado inicial desde `localStorage`.
- Realizar cálculos previos antes de establecer el estado.
- Prevenir la creación de objetos complejos innecesarios en cada render.

#### Ejemplo sin `init`:

```jsx
const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    default:
      return state;
  }
}

function Counter() {
  const [state, dispatch] = useReducer(
    reducer,
    initialState
  );

  return (
    <div>
      <p>Count: {state.count}</p>
      <button
        onClick={() => dispatch({ type: "increment" })}
      >
        +
      </button>
      <button
        onClick={() => dispatch({ type: "decrement" })}
      >
        -
      </button>
    </div>
  );
}
```

#### Ejemplo con `init`:

```jsx
const initialState = 0;

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return state + 1;
    case "decrement":
      return state - 1;
    default:
      return state;
  }
}

// Función de inicialización
function init(initialValue) {
  return { count: initialValue };
}

function Counter() {
  const [state, dispatch] = useReducer(
    reducer,
    initialState,
    init
  );

  return (
    <div>
      <p>Count: {state.count}</p>
      <button
        onClick={() => dispatch({ type: "increment" })}
      >
        +
      </button>
      <button
        onClick={() => dispatch({ type: "decrement" })}
      >
        -
      </button>
    </div>
  );
}
```

¿Qué hace `init` aquí?

1. **`initialState`** es `0`.
2. La función `init` transforma ese valor inicial a un objeto `{ count: 0 }`.
3. Esto es útil si necesitas una transformación previa o cálculo antes de usar el estado.

#### ✅ Ventajas de usar `init`:

- **Optimización de rendimiento**: Evita cálculos innecesarios en cada render.
- **Estado complejo**: Facilita inicializar estructuras de datos más elaboradas.
- **Flexibilidad**: Puedes calcular el estado inicial desde una fuente externa (como `localStorage`).

#### DevTools

Para visualizar los datos almacenados en el `localStorage` nos vamos a los DevTools y buscamos:

`application / Local Storage / http...`

Aparecerá una tabla `Key | Value` ahora seleccionamos `todos` y veremos los datos en la parte inferior.

Ahora en nuestro proyecto:

`src > 08-useReducer > TodoApp.jsx`

```jsx
import { useEffect, useReducer } from "react";
import { todoReducer } from "./todoReducer";
import { TodoList } from "./TodoList";
import { TodoAdd } from "./TodoAdd";

const initialState = [
  // {
  //   id: new Date().getTime(),
  //   description: "Collecting the Soul Stone",
  //   done: false,
  // },
];

const init = () => { 👈👀👇
  return JSON.parse(localStorage.getItem("todos") || []);
};

export const TodoApp = () => {
  const [todos, dispatch] = useReducer(
    todoReducer, // List of "cases" to choose
    initialState, // New incoming data
    init
  );

  useEffect(() => {
    // Only strings 👈👀👇
    localStorage.setItem("todos", JSON.stringify(todos));
  }, [todos]); // Runs only when “todos” changes

  const handleNewTodo = (todo) => {
    const action = {
      type: "[TODO] Add Todo",
      payload: todo,
    };

    dispatch(action);
  };

  return (
    <>
      <h1>
        TodoApp: 10, <small>Pending: 2</small>
      </h1>
      <hr />

      <div>
        <div>
          <TodoList todos={todos} />
        </div>

        <div>
          <h4>Add TODO</h4>
          <hr />
          <TodoAdd updateTodos={handleNewTodo} />
        </div>
      </div>
    </>
  );
};
```

- [[react-hooks-mern#9.16 Incorporar caché]]
- [# Uso del local storage en JavaScript](https://www.youtube.com/watch?v=hb8O0qRqiSk)

### 10.12 Borrar un TODO

`src > 08-useReducer > todoReducer.js`

```js
export const todoReducer = (initialState = [], action) => {
  switch (action.type) {
    case "[TODO] Add Todo":
      return [...initialState, action.payload];

    case "[TODO] Remove Todo": 👈👀👇
      return initialState.filter(
        (todo) => todo.id !== action.payload
      );
    default:
      return initialState;
  }
};
```

`src > 08-useReducer > TodoApp.jsx`

```jsx
import { useEffect, useReducer } from "react";
import { todoReducer } from "./todoReducer";
import { TodoList } from "./TodoList";
import { TodoAdd } from "./TodoAdd";

const initialState = [
  // {
  //   id: new Date().getTime(),
  //   description: "Collecting the Soul Stone",
  //   done: false,
  // },
];

const init = () => {
  return JSON.parse(localStorage.getItem("todos") || []);
};

export const TodoApp = () => {
  const [todos, dispatch] = useReducer(
    todoReducer, // List of "cases" to choose
    initialState, // New incoming data
    init
  );

  useEffect(() => {
    localStorage.setItem("todos", JSON.stringify(todos));
  }, [todos]);

  const handleNewTodo = (todo) => {
    const action = {
      type: "[TODO] Add Todo",
      payload: todo,
    };

    dispatch(action);
  };

  const handleDeleteTodo = (id) => {
    dispatch({ 👈👀👇
      type: "[TODO] Remove Todo",
      payload: id,
    });
  };

  return (
    <>
      <h1>
        TodoApp: 10, <small>Pending: 2</small>
      </h1>
      <hr />

      <div>
        <div>
          <TodoList
            todos={todos}
            onDeleteTodo={handleDeleteTodo} 👈👀
          />
        </div>

        <div>
          <h4>Add TODO</h4>
          <hr />
          <TodoAdd updateTodos={handleNewTodo} />
        </div>
      </div>
    </>
  );
};
```

`src > 08-useReducer > TodoList.jsx`

```jsx
import React from "react";
import { TodoItem } from "./TodoItem";

export const TodoList = ({ todos = [], onDeleteTodo👈👀 }) => {
  return (
    <ul>
      {todos.map((todo) => (
        <TodoItem
          key={todo.id}
          id={todo.id}
          task={todo.description}
          onDeleteTodo={onDeleteTodo} 👈👀
        />
      ))}
    </ul>
  );
};
```

`src > 08-useReducer > TodoItem.jsx`

```jsx
export const TodoItem = ({
  id = "01",
  task = "Task 01",
  onDeleteTodo, 👈👀
}) => {
  return (
    <>
      <li>
        <span>{task}</span>
        <br />
        <button onClick={() => onDeleteTodo(id)}>
          Delete 👈👀👆
        </button>
      </li>
    </>
  );
};
```

Pasamos la función `handleDeleteTodo(id)` desde el padre hasta el último hijo del hijo, esto para llegar hasta donde está el `button` y poder hacer `onClick` pasando la función con su `id`.

### 10.13 Toggle Todo - Marcar como completado o pendiente un TODO

`src > 08-useReducer > todoReducer.js`

```jsx
export const todoReducer = (initialState = [], action) => {
  switch (action.type) {
    case "[TODO] Add Todo":
      return [...initialState, action.payload];

    case "[TODO] Remove Todo":
      return initialState.filter(
        (todo) => todo.id !== action.payload
      );

    case "[TODO] Toggle Todo": 👈👀👇
      return initialState.map((todo) => {
        if (todo.id === action.payload) {
          return {
            ...todo,
            done: !todo.done,
          };
        }

        // .map creates a new array with the modifications of each element that passed through it.
        return todo; // [{}, {}, {}]
      });

    default:
      return initialState;
  }
};
```

`src > 08-useReducer > TodoApp.jsx`

```jsx
import { useEffect, useReducer } from "react";
import { todoReducer } from "./todoReducer";
import { TodoList } from "./TodoList";
import { TodoAdd } from "./TodoAdd";

const initialState = [
  // {
  //   id: new Date().getTime(),
  //   description: "Collecting the Soul Stone",
  //   done: false,
  // },
];

const init = () => {
  return JSON.parse(localStorage.getItem("todos") || []);
};

export const TodoApp = () => {
  const [todos, dispatch] = useReducer(
    todoReducer, // List of "cases" to choose
    initialState, // New incoming data
    init
  );

  useEffect(() => {
    localStorage.setItem("todos", JSON.stringify(todos));
  }, [todos]);

  const handleNewTodo = (todo) => {
    const action = {
      type: "[TODO] Add Todo",
      payload: todo,
    };

    dispatch(action);
  };

  const handleDeleteTodo = (id) => {
    dispatch({
      type: "[TODO] Remove Todo",
      payload: id,
    });
  };

  const handleToggleTodo = (id) => {
    dispatch({ 👈👀👇
      type: "[TODO] Toggle Todo",
      payload: id,
    });
  };

  return (
    <>
      <h1>
        TodoApp: 10, <small>Pending: 2</small>
      </h1>
      <hr />

      <div>
        <div>
          <TodoList
            todos={todos}
            onDeleteTodo={handleDeleteTodo}
            onToggleTodo={handleToggleTodo}👈👀
          />
        </div>

        <div>
          <h4>Add TODO</h4>
          <hr />
          <TodoAdd updateTodos={handleNewTodo} />
        </div>
      </div>
    </>
  );
};
```

`src > 08-useReducer > TodoList.jsx`

```jsx
import React from "react";
import { TodoItem } from "./TodoItem";

export const TodoList = ({
  todos = [],
  onDeleteTodo,
  onToggleTodo, 👈👀
}) => {
  return (
    <ul>
      {todos.map((todo) => (
        <TodoItem
          key={todo.id}
          id={todo.id}
          task={todo.description}
          done={todo.done}
          onDeleteTodo={onDeleteTodo}
          onToggleTodo={onToggleTodo} 👈👀
        />
      ))}
    </ul>
  );
};
```

`src > 08-useReducer > TodoItem.jsx`

```jsx
export const TodoItem = ({
  id = "01",
  task = "Task 01",
  done,
  onDeleteTodo,
  onToggleTodo,
}) => {
  return (
    <>
      <li>
        <span
          className={`${👈👀👇
            done ? "text-decoration-line-through" : ""
          }`}
          onClick={() => onToggleTodo(id)}👈👀
        >
          {task}
        </span>
        <br />
        <button onClick={() => onDeleteTodo(id)}>
          Delete
        </button>
      </li>
    </>
  );
};
```

[Doc .map](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

### 10.14 Tarea - useTodo

`src > 08-useReducer > TodoApp.jsx`

```jsx
import { useEffect, useReducer } from "react";
import { todoReducer } from "./todoReducer";
import { TodoList } from "./TodoList";
import { TodoAdd } from "./TodoAdd";
import { useTodo } from "../hooks/useTodo";

export const TodoApp = () => {
  const {
    todos,
    todosCount,
    pendingTodos,
    handleNewTodo,
    handleDeleteTodo,
    handleToggleTodo,
  } = useTodo();

  console.log(todosCount, pendingTodos);

  return (
    <>
      <h1>
        TodoApp: {todosCount},
        <small>Pending: {pendingTodos}</small>
      </h1>
      <hr />

      <div>
        <div>
          <TodoList
            todos={todos}
            onDeleteTodo={handleDeleteTodo}
            onToggleTodo={handleToggleTodo}
          />
        </div>

        <div>
          <h4>Add TODO</h4>
          <hr />
          <TodoAdd updateTodos={handleNewTodo} />
        </div>
      </div>
    </>
  );
};
```

`src > hooks > useTodo.js`

```jsx
import { useEffect, useReducer } from "react";
import { todoReducer } from "../08-useReducer/todoReducer";

const initialState = [];
const init = () => {
  // const obj = localStorage.getItem("todos");

  return JSON.parse(localStorage.getItem("todos") || []);
};

export const useTodo = () => {
  const [todos, dispatch] = useReducer(
    todoReducer,
    initialState,
    init
  );

  useEffect(() => {
    localStorage.setItem("todos", JSON.stringify(todos));
  }, [todos]);

  const todosCount = todos.length;

  const pendingTodos = todos.filter((item) => {
    // !item.done
    return item.done === false;
  }).length;

  // console.log(todosCount, pendingTodos);

  const handleNewTodo = (todo) => {
    const action = {
      type: "[TODO] Add Todo",
      payload: todo,
    };

    dispatch(action);
  };

  const handleDeleteTodo = (id) => {
    const action = {
      type: "[TODO] Remove Todo",
      payload: id,
    };

    dispatch(action);
  };

  const handleToggleTodo = (id) => {
    const action = {
      type: "[TODO] Toggle Todo",
      payload: id,
    };

    dispatch(action);
  };

  return {
    todos,
    todosCount,
    pendingTodos,
    handleNewTodo,
    handleDeleteTodo,
    handleToggleTodo,
  };
};
```

### 10.15 Resolución de la tarea - useTodos

### 10.16 Código fuente de la sección

Aquí les dejo el código fuente de la sección tal cual lo dejé al final de la última clase, espero que estemos aprendiendo mucho y sobre todo que cada vez comprendamos cómo funcionan los Hooks.

[**GitHub - Fin sección 10**](https://github.com/Klerith/react-hooks/tree/fin-seccion-10)

## 🟣 11. Profundizando Hooks - useContext

### 11.1 Introducción a la sección

### 11.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Context
- Provider
- useContext
- React Router
- Links y NavLinks
- CreateContext
- SPA ( Single Page Application )

El objetivo de la sección es principalmente aprender sobre el Context, el Router es un valor agregado que explotaremos mucho más en próximas secciones, pero al usar un Router, podemos explicar claramente el problema y necesidad del context.

### 11.3 Introducción al Context 

En React, el **Context** es una herramienta que permite compartir datos globales entre componentes sin necesidad de pasar props manualmente en cada nivel del árbol de componentes. Es especialmente útil para temas como:

- **Temas (dark mode, light mode)**
- **Autenticación de usuarios**
- **Configuraciones de idioma**
- **Datos compartidos (carrito de compras, estado global)**

El Context sirve para evitar lo que se llama _prop drilling_, que ocurre cuando pasas datos de un componente padre a uno muy profundo a través de múltiples niveles intermedios.

#### ¿Cómo se usa?

1. **Crear el Contexto:** Se crea un contexto usando `React.createContext`.
2. **Proveer el Contexto:** Un componente `Provider` envuelve a los componentes que necesitan acceder al contexto.
3. **Consumir el Contexto:** Los componentes acceden al contexto usando `useContext`.

#### Ejemplo básico:

```jsx
import React, { createContext, useContext, useState } from 'react';

// 1. Crear el contexto
const UserContext = createContext();

// 2. Proveedor del contexto
const UserProvider = ({ children }) => {
  const [user, setUser] = useState('Ghost');
  return (
    <UserContext.Provider value={{ user, setUser }}>
      {children}
    </UserContext.Provider>
  );
};

// 3. Consumir el contexto en un componente hijo
const UserProfile = () => {
  const { user } = useContext(UserContext);
  return <p>Usuario: {user}</p>;
};

// 4. Usar el proveedor en la aplicación
const App = () => {
  return (
    <UserProvider>
      <UserProfile />
    </UserProvider>
  );
};

export default App;
```

![example](https://i.postimg.cc/4dF7wqyM/14-create-context.png)

![contex](https://i.postimg.cc/RhcGrh69/11-context.png)

#### Diagrama **sin Context** (prop drilling)

```mermaid
graph TD
    A[Root Component] --> B[Component 1]
    B --> C[Component 2]
    C --> D[Component 3]
    D --> E[Component 4 initiating change]
    E --> F[Component 5]
    F --> G[Component 6]
```

- Los datos fluyen de un componente a otro, pasando `props` manualmente.
- El componente `E` inicia el cambio, pero las props deben propagarse a través de varios niveles.

#### Diagrama **con Context**

```mermaid
graph TD
    A[Root Component] --> B[Component 1]
    A --> C[Component 2]
    A --> D[Component 3]
    A --> E[Component 4 initiating change]
    A --> F[Component 5]
    A --> G[Component 6]
    S[(State Context)] --> B
    S --> C
    S --> D
    S --> E
    S --> F
    S --> G
```

- El **State Context** proporciona los datos directamente a todos los componentes, eliminando la necesidad de prop drilling.
- El componente `E` inicia el cambio, pero todos los componentes tienen acceso al estado global.

### 11.4 Preparación de nuestra aplicación con rutas

```bash
# Instalar React Router
yarn add react-router-dom
yarn add react-router-dom@7.1.1
```

`src > main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
// I will see which of the two imports works 👈👀👇
// import { BrowserRouter } from "react-router-dom";
import { BrowserRouter } from "react-router";

import "./index.css";

import { MainApp } from "./09-useContext/MainApp";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <BrowserRouter>
      <MainApp />
    </BrowserRouter>
  </StrictMode>
);
```

`src > 09-useContext > MainApp.jsx`

```jsx
export const MainApp = () => {
  return (
    <>
      <h1>MainApp</h1>
      <hr />
    </>
  );
};
```

`src > 09-useContext > AboutPage.jsx`

```jsx
export const AboutPage = () => {
  return <div>AboutPage</div>;
};
```

`src > 09-useContext > HomePage.jsx`

```jsx
export const HomePage = () => {
  return <div>HomePage</div>;
};
```

`src > 09-useContext > Loginpage.jsx`

```jsx
export const LoginPage = () => {
  return <div>LoginPage</div>;
};
```

📌 `Higher-Order Component (HOC):` Componente de orden superior que recibe otros componentes dentro del él. Permite que los hijos tengan acceso a la info que provee el padre.

```js
<div>
  <h1></h1>
  <hr />
</div>
```

- [React Router v7](https://reactrouter.com/)
- [React Router v5](https://v5.reactrouter.com/)
- [Instalación v7.1.1](https://classic.yarnpkg.com/en/package/react-router-dom)
- [Uso](https://reactrouter.com/start/library/installation)

### 11.5 Configurar Router en React

`src > 09-useContext > MainApp.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { HomePage } from "./HomePage";
import { AboutPage } from "./AboutPage";
import { LoginPage } from "./LoginPage";

export const MainApp = () => {
  return (
    <>
      <h1>MainApp</h1>
      <hr />

      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="login" element={<LoginPage />} />
        <Route path="about" element={<AboutPage />} />
        {/* <Route path="/*" element={<LoginPage />} /> */}
        <Route
          path="/*"
          element={<Navigate to={<HomePage />} />}
        />
      </Routes>
    </>
  );
};
```

[React Router: routing](https://reactrouter.com/start/library/routing)

### 11.6 Link

La diferencia principal entre la etiqueta `<a>` en HTML y el componente `<Link>` de React Router es su comportamiento en el contexto de las aplicaciones de una sola página (SPA):

1. **`<a>` en HTML:**
    
    - Navega a una nueva página completa y recarga la página en el navegador.
    - Utiliza el atributo `href` para especificar la URL.
2. **`<Link>` en React Router:**
    
    - Navega dentro de la misma aplicación SPA sin recargar la página.
    - Utiliza el atributo `to` para especificar la ruta dentro de la aplicación, manteniendo la experiencia de navegación fluida.

**En resumen:**

`<a>` recarga la página, mientras que `<Link>` evita la recarga y permite la navegación de página en página dentro de una aplicación React.

📌 Para estilizar `Link` se sigue usando `a` en el CSS.

`src > 09-useContext > MainApp.jsx`

```jsx
import {
  Navigate,
  Route,
  Routes,
} from "react-router";
import { HomePage } from "./HomePage";
import { AboutPage } from "./AboutPage";
import { LoginPage } from "./LoginPage";
import { Navbar } from "./Navbar";

export const MainApp = () => {
  return (
    <>
      <h1>MainApp</h1>
      <Navbar /> 👈👀
      <hr />

      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="login" element={<LoginPage />} />
        <Route path="about" element={<AboutPage />} />
        {/* <Route path="/*" element={<LoginPage />} /> */}
        <Route
          path="/*"
          element={<Navigate to={<HomePage />} />}
        />
      </Routes>
    </>
  );
};
```

`src > 09-useContext > Navbar.jsx`

```jsx
import { Link } from "react-router-dom";

export const Navbar = () => {
  return (
    <>
      <Link to="/">Home</Link> 👈👀
      <Link to="/about">About</Link>
      <Link to="/login">Login</Link>
    </>
  );
};
```

`src > index.css`

```css
body {
  padding: 20px;
}

button {
  margin-right: 10px;
}

a {
  margin-right: 5px;
}
```

### 11.7 NavLink

**`NavLink`** es un componente de **React Router** que se utiliza para crear enlaces de navegación con estilo activado cuando la ruta correspondiente está activa. A diferencia de `<Link>`, `NavLink` agrega una clase CSS especial cuando la ruta está activa, lo que permite resaltar el enlace.

```jsx
import { NavLink } from 'react-router-dom';

<NavLink to="/home" activeClassName="active-link">
  Home
</NavLink>
```

#### Explicación:

- **`to`**: Define la ruta a la que el enlace llevará.
- **`activeClassName`**: Asigna una clase CSS cuando el enlace está activo (cuando la ruta coincide).
- **`isActive` (opcional)**: Permite personalizar cómo se determina si el enlace está activo, como usar un método para compararlo con la URL actual.

#### Estilo:

```css
.active-link {
  color: red;
  font-weight: bold;
}
```

**En resumen:** `NavLink` es útil para agregar estilos activos a los enlaces en tu aplicación React, destacando el enlace cuando la ruta está activa.

En nuestro proyecto:

`src > 09-useContext > mainApp.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { HomePage } from "./HomePage";
import { AboutPage } from "./AboutPage";
import { LoginPage } from "./LoginPage";
import { Navbar } from "./Navbar";

export const MainApp = () => {
  return (
    <>
      <Navbar />
      <hr />

      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="login" element={<LoginPage />} />
        <Route path="about" element={<AboutPage />} />
        <Route
          path="/*"
          element={<Navigate to={<HomePage />} />}
        />
      </Routes>
    </>
  );
};
```

`src > 09-useContext > Navbar.jsx`

```jsx
import { Link, NavLink } from "react-router-dom";

export const Navbar = () => {
  return (
    <nav>
      <div>
        <Link to="/">useContext</Link>
        <div>
          <ul>
            <NavLink to="/">Home</NavLink>

            <NavLink to="about">About</NavLink>

            <NavLink to="login">Login</NavLink>
          </ul>
        </div>
      </div>
    </nav>
  );
};

// Antes también...
{
  /* 
<NavLink
  className={({ isActive }) =>
    `nav-link ${isActive ? "active" : ""}`
  }
  to="/"
>
  Home
</NavLink> 
*/
}
```

`src > index.css`

```css
body {
  padding: 20px;
}

button {
  margin-right: 10px;
}

a {
  margin-right: 5px;
}

.active {
  color: palevioletred;
  font-weight: bold;
}
```

[NavLink](https://api.reactrouter.com/v7/functions/react_router.NavLink)

### 11.8 CreateContext y ContextProvider

En **React**, `createContext` y `Context.Provider` se utilizan juntos para crear y gestionar un **Contexto** que permite compartir datos globales entre componentes sin necesidad de prop drilling (pasar props manualmente a través de múltiples niveles).

#### 🎯 `createContext`

- **`createContext`** crea un objeto de contexto que puede ser utilizado para almacenar y compartir datos.
- Devuelve un objeto con dos propiedades principales:
    - `Context.Provider`: Proporciona los datos.
    - `Context.Consumer`: Consume los datos (aunque se suele usar `useContext` en su lugar).

```jsx
import React, { createContext } from 'react';

// Crear el contexto
export const UserContext = createContext(null);
```

#### 🎯 `Context.Provider`

- **`Context.Provider`** se utiliza para envolver los componentes y proporcionarles un valor que estará disponible para todos los descendientes.
- Se coloca en un componente de nivel superior.

```jsx
import React from 'react';
import { UserContext } from './UserContext';

const App = () => {
  const user = { name: "Ghost", role: "Admin" };

  return (
    <UserContext.Provider value={user}>
      <UserProfile />
    </UserContext.Provider>
  );
};

const UserProfile = () => {
  return (
    <UserContext.Consumer>
      {(user) => <h1>Usuario: {user.name}</h1>}
    </UserContext.Consumer>
  );
};

export default App;
```

#### Mejor práctica con `useContext`

En lugar de usar `.Consumer`, es más común usar el **hook `useContext`**:

```jsx
import React, { useContext } from 'react';
import { UserContext } from './UserContext';

const UserProfile = () => {
  const user = useContext(UserContext);
  return <h1>Usuario: {user.name}</h1>;
};

export default UserProfile;
```

Resumen:

- **`createContext`**: Crea un contexto para compartir datos.
- **`Context.Provider`**: Proporciona los datos a los componentes hijos.
- **`useContext`** (recomendado): Extrae datos de un contexto de forma sencilla.

✅ Ideal para **temas, usuarios, autenticación o configuración global**.

Ahora en nuestro proyecto:

`src > 09-useContext > MainApp.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { HomePage } from "./HomePage";
import { AboutPage } from "./AboutPage";
import { LoginPage } from "./LoginPage";
import { Navbar } from "./Navbar";
import { UserProvider } from "./context/UserProvider";

export const MainApp = () => {
  return (
    <UserProvider>
      <Navbar />
      <hr />

      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="login" element={<LoginPage />} />
        <Route path="about" element={<AboutPage />} />
        <Route
          path="/*"
          element={<Navigate to={<HomePage />} />}
        />
      </Routes>
    </UserProvider>
  );
};
```

`src > 09-useContext > context > UserContext.jsx`

```jsx
import { createContext } from "react";

export const UserContext = createContext();
```

`src > 09-useContext > context > UserProvider.jsx`

```jsx
import { UserContext } from "./UserContext";

const user = {
  id: 123,
  name: "Ale Roses",
  email: "ghost",
};

export const UserProvider = ({ children }) => {
  return (
    <UserContext.Provider value={{ hi: "World" }}>
      {children}
    </UserContext.Provider>
  );
};
```

![userProvider](https://i.postimg.cc/MTrCdY83/11-user-Provider.png)

### 11.9 useContext

**`useContext`** es un **hook** de React que permite acceder a valores de un **Contexto** de manera sencilla, evitando la necesidad de usar `Context.Consumer`. Se utiliza principalmente para compartir datos globales entre componentes sin necesidad de **prop drilling** (pasar props manualmente a través de múltiples niveles).

- Es un **hook** integrado en React.
- Permite acceder al valor de un **Contexto** directamente desde cualquier componente hijo.
- Solo funciona con **React Functional Components**.

#### ¿Cómo se usa?

1. **Crear el Contexto:**

```jsx
import React, { createContext } from 'react';

// Crear el contexto
export const UserContext = createContext(null);
```

2. **Proveer el Contexto con `Context.Provider`:**

```jsx
import React from 'react';
import { UserContext } from './UserContext';

const App = () => {
  const user = { name: "Ghost", role: "Admin" };

  return (
    <UserContext.Provider value={user}>
      <UserProfile />
    </UserContext.Provider>
  );
};

export default App;
```

3. **Consumir el Contexto con `useContext`:**

```jsx
import React, { useContext } from 'react';
import { UserContext } from './UserContext';

const UserProfile = () => {
  const user = useContext(UserContext);
  return <h1>Bienvenido, {user.name} - Rol: {user.role}</h1>;
};

export default UserProfile;
```

🎯 Explicación:

1. **`createContext`** crea un contexto.
2. **`UserContext.Provider`** proporciona un valor (`user`) a los componentes hijos.
3. **`useContext(UserContext)`** permite acceder al valor del contexto sin necesidad de pasar props manualmente.

#### Ventajas:

- Evita el **prop drilling**.
- Código más limpio y fácil de mantener.
- Ideal para **temas, autenticación y datos globales**.

**En resumen:** `useContext` simplifica el acceso a datos globales en React, haciendo que tu código sea más limpio y mantenible. 🚀

Ahora en nuestro proyecto:

`src > 09-useContext > context > UserProvider.jsx`

```jsx
import { useState } from "react";
import { UserContext } from "./UserContext";

// const user = {
//   id: 123,
//   name: "Ale Roses",
//   email: "ghost",
// };

export const UserProvider = ({ children }) => {
  const [user, setUser] = useState();

  return (
    // <UserContext.Provider value={{ hi: "World", user }}>
    <UserContext.Provider value={{ user, setUser }}>
      {children}
    </UserContext.Provider>
  );
};
```

`src > 09-useContext > HomePage.jsx`

```jsx
import { useContext } from "react";
import { UserContext } from "./context/UserContext";

export const HomePage = () => {
  const { user } = useContext(UserContext);
  return (
    <>
      <h1>
        HomePage <small>{user?.name}</small>
      </h1>
      <hr />

      <pre>{JSON.stringify(user, null, 3)}</pre>
    </>
  );
};
```

`src > 09-useContext > LoginPage.jsx`

```jsx
import { useContext } from "react";
import { UserContext } from "./context/UserContext";

export const LoginPage = () => {
  // Matches the closest context
  const { user, setUser } = useContext(UserContext);

  return (
    <>
      <h1>LoginPage</h1>
      <hr />

      <pre>{JSON.stringify(user, null, 3)}</pre>

      <button
        onClick={() =>
          setUser({
            id: 123,
            name: "Ghost",
            email: "ghost@gmail.com",
          })
        }
      >
        Set User
      </button>
    </>
  );
};
```

### 11.10 Código fuente de la sección

Vista general:

![useContext](https://i.postimg.cc/ZKVgnvhV/11-create-Context.png)

Aquí les dejo el código fuente de la sección por si lo llegan a necesitar.

[**Github- Fin sección 11**](https://github.com/Klerith/react-hooks/tree/fin-seccion-11)

## 🟡 12. Pruebas unitarias y de integración - Hooks

### 12.1 Introducción a la sección

### 12.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Pruebas sobre Hooks y CustomHooks

Ese es el tema principal, demostrar cómo podemos evaluar cada unos de los hooks aplicados anteriormente con sus casos reales de uso.

Hay varios extras, como la prueba de un Reducer, que realmente no es nada complicado, también quiero aclarar qué nos toca evaluar a nosotros y qué no es responsabilidad nuestra.

### 12.3 Inicio de proyecto - Pruebas sobre Hooks

- [[react-hooks-mern#8. Testing - Probando la aplicación de GifExpert#🟣 Configurar el ambiente de pruebas]]
- [Configurar el ambiente de pruebas](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/devTalles/react-hooks-mern.md#-configurar-el-ambiente-de-pruebas)

### 12.4 Pruebas sobre useCounter - CustomHook

Pruebas en componentes:

```bash
yarn test
# p: useCounter.js
```

`test/hooks/useCounter.test.js`

```jsx
import { renderHook } from "@testing-library/react";
import { useCounter } from "../../src/hooks/useCounter";

describe("Tests in the useCounter", () => {
  const value = 100;

  test("should return default values", () => {
    const { result } = renderHook(() => useCounter());
    const { counter, decrease, increase, reset } =
      result.current;

    expect(counter).toBe(10);
    expect(decrease).toEqual(expect.any(Function));
    expect(increase).toEqual(expect.any(Function));
    expect(reset).toEqual(expect.any(Function));
  });

  test("should generate the counter with the value of 100", () => {
    const { result } = renderHook(() => useCounter(value));

    // console.log(result);
    const { counter } = result.current;

    expect(counter).toBe(100);
  });
});
```

### 12.5 Ejecutar funciones del customHook dentro de las pruebas

`src/hooks/useCounter.js`

```js
import { useState } from "react";

export const useCounter = (initialValue = 10) => {
  const [counter, setCounter] = useState(initialValue);

  const increase = (value = 1) => {
    setCounter((v) => v + value);
  };

  const decrease = (value = 1) => {
    if (counter === 0) return;

    setCounter((v) => v - value);
  };

  const reset = () => {
    setCounter(10);
  };
  return {
    counter,
    increase,
    decrease,
    reset,
  };
};

// Representación de un objeto en string
const obj = {};
// undefined
obj.toString();
// '[object Object]'
```

`test/hooks/useCounter.test.js`

```jsx
import { renderHook } from "@testing-library/react";
import { useCounter } from "../../src/hooks/useCounter";
import { act } from "react";

describe("Tests in the useCounter", () => {
  const value = 100;

  test("should return default values", () => {
    const { result } = renderHook(() => useCounter());
    const { counter, decrease, increase, reset } =
      result.current;

    expect(counter).toBe(10);
    expect(decrease).toEqual(expect.any(Function));
    expect(increase).toEqual(expect.any(Function));
    expect(reset).toEqual(expect.any(Function));
  });

  test("should generate the counter with the value of 100", () => {
    const { result } = renderHook(() => useCounter(value));

    // console.log(result);
    const { counter } = result.current;

    expect(counter).toBe(100);
  });

  test("should increase the counter", () => {
    const { result } = renderHook(() => useCounter());
    const { increase } = result.current;

    act(() => {
      increase();
      increase(2);
    });

    expect(result.current.counter).toBe(13);
  });

  test("should decrease the counter", () => {
    const { result } = renderHook(() => useCounter());
    const { decrease } = result.current;

    act(() => {
      decrease();
      decrease(2);
    });

    expect(result.current.counter).toBe(7);
  });

  test("should reset the counter", () => {
    const { result } = renderHook(() => useCounter());
    const { reset } = result.current;

    act(() => {
      reset();
    });

    expect(result.current.counter).toBe(10);
  });
});
```

### 12.6 Pruebas sobre useForm - CustomHook

`test/hooks/useForm.test.js`

```jsx
import { renderHook } from "@testing-library/react";
import { useForm } from "../../src/hooks/useForm";
import { act } from "react";

describe("Tests in the useForm", () => {
  const initialForm = {
    name: "Ghost",
    email: "ghost@mail.com",
  };

  test("should return the default values", () => {
    const { result } = renderHook(() =>
      useForm(initialForm)
    );

    expect(result.current).toEqual({
      name: "Ghost",
      email: "ghost@mail.com",
      formState: initialForm,
      handleInputChange: expect.any(Function),
      handleResetForm: expect.any(Function),
    });
  });

  test("should change the form name", () => {
    const newValue = "Phantom";
    const { result } = renderHook(() =>
      useForm(initialForm)
    );

    const { name, handleInputChange } = result.current;

    act(() => {
      handleInputChange({
        target: { name: "name", value: newValue },
      });
    });

    expect(result.current.name).toBe(newValue);
    expect(result.current.formState.name).toBe(newValue);
  });

  test("It should reset the form.", () => {
    const newValue = "Phantom";
    const { result } = renderHook(() =>
      useForm(initialForm)
    );

    const { handleInputChange, handleResetForm } =
      result.current;

    act(() => {
      handleInputChange({
        target: { name: "name", value: newValue },
      });
      handleResetForm();
    });

    expect(result.current.name).toBe(initialForm.name);
    expect(result.current.formState.name).toBe(
      initialForm.name
    );
  });
});
```

### 12.7 Pruebas con múltiples hooks simultáneos

`test/hooks/03-examples/MultipleCustomHook.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { MultipleCustomHook } from "../../src/03-examples/MultipleCustomHook";

describe("Tests in the MultipleCustomHook", () => {
  test("should display the default component", () => {
    render(<MultipleCustomHook />);

    // screen.debug();
    expect(screen.getByText("Loading component..."));
    expect(screen.getByText("Pokemon information"));

    // Si usas cualquier nombre en name: puedes ver los nombres que realmente fueron usados, luego podras colocar un nombre real
    const nextButton = screen.getByRole("button", {
      name: "Next", 👈👀
    });

    console.log(nextButton.disabled);
    expect(nextButton.disabled).toBeFalsy();
  });
});
```

### 12.8 Evaluar respuesta del useFetch

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { BrowserRouter } from "react-router";

import "./index.css";

import { MultipleCustomHook } from "./03-examples/MultipleCustomHook";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <BrowserRouter>
      <MultipleCustomHook />
    </BrowserRouter>
  </StrictMode>
);
```

`test/hooks/03-examples/MultipleCustomHook.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { MultipleCustomHook } from "../../src/03-examples/MultipleCustomHook";
import { useFetch } from "../../src/hooks";
import { useCounter } from "../../src/hooks/useCounter";

// Point directly to the source file
jest.mock("../../src/hooks/useFetch");
jest.mock("../../src/hooks/useCounter");

describe("Tests in the MultipleCustomHook", () => {
  const mockIncrease = jest.fn();

  // All tests will have this info
  useCounter.mockReturnValue({
    counter: 1,
    increase: mockIncrease,
  });

  // Make sure that they are reset to their original state
  beforeEach(() => {
    jest.clearAllMocks();
  });

  test("should display the default component", () => {
    useFetch.mockReturnValue({
      data: null,
      isLoading: true,
      hasError: null,
    });

    render(<MultipleCustomHook />);

    // screen.debug();
    expect(screen.getByText("Loading component..."));
    expect(screen.getByText("Pokemon information"));

    const nextButton = screen.getByRole("button", {
      name: "Next",
    });

    // console.log(nextButton.disabled);
    expect(nextButton.disabled).toBeFalsy();
  });

  test("should display a pokemon", () => {
    useFetch.mockReturnValue({
      data: {
        id: 1,
        name: "bulbasaur",
        sprites: {
          img: {
            front_shiny: "https://shiny/1.png",
            front_default: "https://shiny/1.png",
            back_shiny: "https://shiny/1.png",
            back_default: "https://shiny/1.png",
          },
        },
      },

      isLoading: false,
      hasError: null,
      error: null,
    });

    render(<MultipleCustomHook />);
    // screen.debug();

    expect(
      screen.getByText("Pokemon information")
    ).toBeTruthy();

    const nextButton = screen.getByRole("button", {
      name: "Next",
    });

    expect(nextButton.disabled).toBeFalsy();
  });

  test("should call the increase function", () => {
    useFetch.mockReturnValue({
      data: {
        id: 1,
        name: "bulbasaur",
        sprites: {
          img: {
            front_shiny: "https://shiny/1.png",
            front_default: "https://shiny/1.png",
            back_shiny: "https://shiny/1.png",
            back_default: "https://shiny/1.png",
          },
        },
      },

      isLoading: false,
      hasError: null,
      error: null,
    });

    render(<MultipleCustomHook />);
    // screen.debug();

    const nextButton = screen.getByRole("button", {
      name: "Next",
    });
    fireEvent.click(nextButton);

    // screen.debug();
    expect(mockIncrease).toHaveBeenCalled();
  });
});
```

### 12.9 Pruebas sobre el Reducer

`test/08-useReducer/todoReducer.test.js`

```jsx
import { todoReducer } from "../../src/08-useReducer/todoReducer";

describe("Testing in todoReducer", () => {
  const initialState = [
    {
      id: 1,
      description: "Demo todo",
      done: false,
    },
  ];

  test("should return the initial state", () => {
    const newState = todoReducer(initialState, {});

    expect(newState).toBe(initialState);
  });

  test("should add a TODO", () => {
    const action = {
      type: "[TODO] Add Todo",
      payload: {
        id: 2,
        description: "New Todo #2",
        done: false,
      },
    };

    const newState = todoReducer(initialState, action);
    // console.log(newState);

    expect(newState.length).toBe(2);
    expect(newState).toContain(action.payload);
  });

  test("should delete a TODO", () => {
    const action = {
      type: "[TODO] Remove Todo",
      payload: 1,
    };

    const newState = todoReducer(initialState, action);

    // console.log(newState);
    expect(newState.length).toBe(0);
  });

  test("should do the TODO Toggle", () => {
    const action = {
      type: "[TODO] Toggle Todo",
      payload: 1,
    };

    const newState = todoReducer(initialState, action);

    // console.log(newState[0].done);

    expect(newState[0].done).toBeTruthy();
  });
});
```

### 12.10 Resolución de la tarea

`test/08-useReducer/todoReducer.test.js`

```jsx
import { todoReducer } from "../../src/08-useReducer/todoReducer";

describe("Testing in todoReducer", () => {
  const initialState = [
    {
      id: 1,
      description: "Demo todo",
      done: false,
    },
  ];

  test("should return the initial state", () => {
    const newState = todoReducer(initialState, {});

    expect(newState).toBe(initialState);
  });

  test("should add a TODO", () => {
    const action = {
      type: "[TODO] Add Todo",
      payload: {
        id: 2,
        description: "New Todo #2",
        done: false,
      },
    };

    const newState = todoReducer(initialState, action);
    // console.log(newState);

    expect(newState.length).toBe(2);
    expect(newState).toContain(action.payload);
  });

  test("should delete a TODO", () => {
    const action = {
      type: "[TODO] Remove Todo",
      payload: 1,
    };

    const newState = todoReducer(initialState, action);

    // console.log(newState);
    expect(newState.length).toBe(0);
  });

  test("should do the TODO Toggle", () => {
    const action = {
      type: "[TODO] Toggle Todo",
      payload: 1,
    };

    const newState = todoReducer(initialState, action);
    // console.log(newState[0].done);
    expect(newState[0].done).toBeTruthy();

    const newStateTwo = todoReducer(newState, action);
    expect(newStateTwo[0].done).toBeFalsy();
  });
});
```

### 12.11 Pruebas en el componente TodoItem

`src/08-useReducer/TodoItem.jsx`

```js
export const TodoItem = ({
  id = "01",
  task = "Task 01",
  done,
  onDeleteTodo,
  onToggleTodo,
}) => {
  return (
    <>
      <li className="test">
        <span
          className={`${
            done ? "text-decoration-line-through" : ""
          }`}
          onClick={() => onToggleTodo(id)}
          aria-label="spantodo" 👈👀
        >
          {task}
        </span>
        <br />
        <button onClick={() => onDeleteTodo(id)}>
          Delete
        </button>
      </li>
    </>
  );
};
```

`test/08-useReducer/TodoItem.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { TodoItem } from "../../src/08-useReducer/TodoItem";

describe("Testing in TodoItem", () => {
  const todo = {
    id: 1,
    description: "Soul Stone",
    done: false,
  };

  const onDeleteTodoMock = jest.fn();
  const onToggleTodoMock = jest.fn();

  beforeEach(() => jest.clearAllMocks);

  test("must show the TODO pending completion", () => {
    render(
      <TodoItem
        todo={todo}
        onToggleTodo={onToggleTodoMock}
        onDeleteTodo={onDeleteTodoMock}
      />
    );

    const liElement = screen.getByRole("listitem");
    const spanElement = screen.getByLabelText("spantodo");

    // screen.debug();

    expect(liElement.className).toBe("test");
    expect(spanElement.className).toBe("");
    expect(spanElement.className).toContain("");
  });
});
```

### 12.12 Pruebas en los eventos del TodoItem

`test/08-useReducer/TodoItem.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { TodoItem } from "../../src/08-useReducer/TodoItem";

describe("Testing in TodoItem", () => {
  const todo = {
    id: "01",
    description: "Soul Stone",
    done: false,
  };

  const onDeleteTodoMock = jest.fn();
  const onToggleTodoMock = jest.fn();

  beforeEach(() => jest.clearAllMocks);

  test("must show the TODO pending completion", () => {
    render(
      <TodoItem
        todo={todo}
        onToggleTodo={onToggleTodoMock}
        onDeleteTodo={onDeleteTodoMock}
      />
    );

    const liElement = screen.getByRole("listitem");
    const spanElement = screen.getByLabelText("spantodo");

    // screen.debug();

    expect(liElement.className).toBe("test");
    expect(spanElement.className).toBe("");
    expect(spanElement.className).toContain("");
  });

  test("should display the completed TODO", () => {
    todo.done = true;

    render(
      <TodoItem
        todo={todo}
        onToggleTodo={onToggleTodoMock}
        onDeleteTodo={onDeleteTodoMock}
      />
    );

    const spanElement = screen.getByLabelText("spantodo");

    // console.log({ spanElement });
    // console.log(todo.done);

    // Did not work
    // expect(spanElement.className).toContain(
    //   "text-decoration-line-through"
    // );
  });

  test("span should call the ToggleAll when clicked.", () => {
    render(
      <TodoItem
        todo={todo}
        onToggleTodo={onToggleTodoMock}
        onDeleteTodo={onDeleteTodoMock}
      />
    );

    const spanElement = screen.getByLabelText("spantodo");

    fireEvent.click(spanElement);

    expect(onToggleTodoMock).toHaveBeenCalled();
    expect(onToggleTodoMock).toHaveBeenCalledWith(todo.id);
  });

  test("the button should call the deleteTodo", () => {
    render(
      <TodoItem
        todo={todo}
        onToggleTodo={onToggleTodoMock}
        onDeleteTodo={onDeleteTodoMock}
      />
    );

    const buttonElement = screen.getByText("Delete");
    const deleteButton = screen.getByRole("button");

    fireEvent.click(buttonElement);

    expect(onDeleteTodoMock).toHaveBeenCalled();
    expect(onDeleteTodoMock).toHaveBeenCalledWith(todo.id);
  });
});
```

### 12.13 Pruebas en el TodoApp

`test/08-useReducer/TodoApp.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { TodoApp } from "../../src/08-useReducer/TodoApp";
import { useTodo } from "../../src/hooks/useTodo";

jest.mock("../../src/hooks/useTodo");

describe("Testing in TodoApp", () => {
  useTodo.mockReturnValue({
    todos: [
      { id: 1, description: "Todo #test", done: false },
      { id: 2, description: "Todo #react", done: false },
    ],
    todosCount: 2,
    pendingTodos: 1,
    handleNewTodo: jest.fn(),
    handleDeleteTodo: jest.fn(),
    handleToggleTodo: jest.fn(),
  });

  test("It should show the correct component", () => {
    render(<TodoApp />);

    // screen.debug();
    expect(screen.getByText("Todo #test")).toBeTruthy();
    expect(screen.getByText("Todo #react")).toBeTruthy();
    expect(screen.getByRole("textbox")).toBeTruthy();

    // console.log(screen.getByRole("textbox").className);
  });
});
```

### 12.14 Pruebas con useContext

`src/09-useContext/HomePage.jsx`

```jsx
import { useContext } from "react";
import { UserContext } from "./context/UserContext";

export const HomePage = () => {
  const { user } = useContext(UserContext);
  return (
    <>
      <h1>
        HomePage <small>{user?.name}</small>
      </h1>
      <hr />

      <pre aria-label="pre">
        {JSON.stringify(user, null, 3)}
      </pre>
    </>
  );
};
```

`src/hooks/09-useContext/HomePage.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { HomePage } from "../../09-useContext/HomePage";
import { UserContext } from "../../09-useContext/context/UserContext";

describe("Testing in HomePage", () => {
  const user = {
    id: 1,
    name: "Ghost",
  };

  test("should display the component without the user", () => {
    render(
      <UserContext.Provider value={{ user: null }}>
        <HomePage />
      </UserContext.Provider>
    );

    // area-label
    const preTag = screen.getByLabelText("pre");

    expect(preTag.innerHTML).toBe("null");

    // screen.debug();
  });

  test("should display the component with the user", () => {
    render(
      <UserContext.Provider value={{ user }}>
        <HomePage />
      </UserContext.Provider>
    );

    const preTag = screen.getByLabelText("pre");

    expect(preTag.innerHTML).toContain(user.name);
    expect(preTag.innerHTML).toContain(user.id.toString());
    expect(preTag.innerHTML).toContain(`${user.id}`);
    // screen.debug();
  });
});
```

### 12.15 Pruebas de funciones del context

`src/09-useContext/LoginPage.test.jsx`

```jsx
import { useContext } from "react";
import { UserContext } from "./context/UserContext";

export const LoginPage = () => {
  // Matches the closest context
  const { user, setUser } = useContext(UserContext);

  return (
    <>
      <h1>LoginPage</h1>
      <hr />

      <pre aria-label="pre">
        {JSON.stringify(user, null, 3)}
      </pre>

      <button
        aria-label="button"
        onClick={() =>
          setUser({
            id: 123,
            name: "Ghost",
            email: "ghost@gmail.com",
          })
        }
      >
        Set User
      </button>
    </>
  );
};
```

`test/09-useContext/LoginPage.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { UserContext } from "../../src/09-useContext/context/UserContext";
import { LoginPage } from "../../src/09-useContext/LoginPage";

describe("Testing in LoginPage", () => {
  const user = {
    id: 1,
    name: "Ghost",
  };

  test("must display the component without the user", () => {
    render(
      <UserContext.Provider value={{ user: null }}>
        <LoginPage />
      </UserContext.Provider>
    );

    // screen.debug();

    const pre = screen.getByLabelText("pre");
    expect(pre.innerHTML).toBe("null");
  });

  test("should call the setUser when the button is clicked", () => {
    const setUserMock = jest.fn();

    render(
      <UserContext.Provider
        value={{ user: null, setUser: setUserMock }}
      >
        <LoginPage />
      </UserContext.Provider>
    );

    const pre = screen.getByLabelText("pre");
    // const button = screen.getByLabelText("button");
    const button = screen.getByRole("button");

    fireEvent.click(button);
    expect(setUserMock).toHaveBeenCalledWith({
      id: 1,
      email: "ghost@gmail.com",
      id: 123,
      name: "Ghost",
    });

    // screen.debug();
  });
});
```

### 12.16 Pruebas generales en nuestro AppRouter

`test/09-useContext/MainApp.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { MainApp } from "../../src/09-useContext/MainApp";
import { MemoryRouter } from "react-router";

describe("Testing in MainApp", () => {
  test("should display the HomePage", () => {
    render(
      <MemoryRouter>
        <MainApp />
      </MemoryRouter>
    );

    expect(screen.getByText("Home")).toBeTruthy();
    // screen.debug();
  });

  test("should display the HomePage", () => {
    render(
      <MemoryRouter initialEntries={["/login"]}>
        <MainApp />
      </MemoryRouter>
    );

    expect(screen.getByText("LoginPage")).toBeTruthy();
    // screen.debug();
  });
});
```

### 12. 17 Código fuente de la sección

Aquí les dejo el código tal cual lo deje en la siguiente clase, espero les sirva y lo usen para comparar contra el suyo:

[**GitHub: Fin sección 12**](https://github.com/Klerith/react-hooks/tree/fin-seccion-12)

#### screen.getByRole('span')

Nota: En varios capítulos Fernando ha comentado que no sabe por qué no funciona la búsqueda por `role` para `span` y que piensa que debería funcionar, y le añade un `aria-label` al elemento `span` para buscarlo por ese texto.

El elemento `<span>` no tiene significado semántico y por eso no tiene ningún role, al igual que un `<div>` o un `<p>`. Son únicamente contenedores de texto.

Al no tener significado semántico, tampoco tiene sentido ponerles un atributo `aria-label`.

Para el resto de elementos que sí tienen un role, como puede ser un enlace o un botón, tampoco se debería usar el `aria-label` para buscar por ese texto en un test, porque estaríamos introduciendo  errores de accesibilidad.

Si modificamos el `aria-label` de un elemento podemos romper la experiencia de un usuario que use un lector de pantalla, o que un asistente de voz no encuentre ese elemento.

Es siempre mejor alternativa usar el `screen.getByTestId()`.

## 🟣 13.  Bonus: Repositorio de Custom Hooks

### 13.1 Introducción a la sección

### 13.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Subir código a nuestro repositorio
- Tener un listado de `customHooks` y código que podemos reutilizar
- Una idea para mantener tu repositorio ordenado con ejemplos

No es una sección obligatoria, pero puede ayudarles a tener su código ordenado y fácil de utilizar en proyectos futuros.

### 13.3 Repositorio con customHooks

Creamos una nueva carpeta para alojar los hooks con los que hemos venido trabajando:

```bash
.
├── 01-intro-react
├── 02-intro-js
├── 03-counter-app-vite
├── 04-gif-expert-app
├── 05-hook-app
└── 06-custom-hooks 👈👀👇
    ├── useCounter.js
    ├── useFetch.js
    ├── useForm.js
    └── useTodo.js
```

Podemos usar el siguiente comando para hacer:

```bash
~/FH/06-custom-hooks
❯ cp ../05-hook-app/src/hooks/*.js .
```

Ahora crea un repositorio y sube la carpeta `06` a GitHub.

[[git-github#19. Uso de GitHub]]

### 13.4 Mejorando la estructura y ayuda de los Hooks

```bash
mkdir useCounter useFetch useForm useTodos

~/FH/06-custom-hooks/useTodos
❯ cp ../../05-hook-app/src/08-useReducer/todoReducer.js .
```

[Repo: custom-hooks](https://github.com/aleroses/custom-hooks/)

### 13.5 Código fuente de la sección

Aquí les dejo el repositorio del proyecto por si acaso lo llegan a necesitar.

[**Gisthub - Repositorio de custom hooks**](https://github.com/Klerith/custom-hooks)

colocar vim en git por defecto

## 🟣 14. HeroesApp - Single Page Application (SPA)

### 14.1 Introducción a la sección

### 14.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- SPA ( Single Page Application ) a profundidad
- Diferentes temas en la misma aplicación aplicados a diferentes rutas
- Multiples Routers
- Push y Replace en el History
- Leer argumentos por URL
- QueryParams
- Aplicar filtros utilizando QueryStrings

En esta sección aún no haremos protección de rutas, pero dejaremos el estilo de esos componentes listos para la siguiente sección.

Aquí quiero enfocarme en la funcionalidad de la aplicación suponiendo que estamos autenticados.

### 14.3 Demostración del objetivo al final de la sección

### 14.4 Inicio de proyecto - HeroesApp

```bash
yarn create vite 07-heroes-spa
# React
# JavaScript + SWC

cd 07-heroes-spa
yarn
code-insiders .
yarn dev

# Abrir explorador
nemo .
# añadimos las imagenes
```

Arrancamos con la siguiente estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── assets 👈👀👇
│   │   └── heroes # img
│   │       ├── *.jpg
│   │       ├── *.jpg
│   │       └── *.jpg
│   ├── auth
│   │   ├── components
│   │   ├── hooks
│   │   └── pages
│   ├── heroes
│   │   ├── components
│   │   ├── helpers
│   │   ├── hooks
│   │   └── pages
│   ├── HeroesApp.jsx
│   ├── main.jsx
│   └── styles.css
├── vite.config.js
└── yarn.lock
```

`index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link
      rel="icon"
      type="image/svg+xml"
      href="/vite.svg"
    />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />

    <title>Vite + React</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>

    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { HeroesApp } from "./HeroesApp";

import "./styles.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <HeroesApp />
  </StrictMode>
);
```

`src/HeroesApp.jsx`

```jsx
export const HeroesApp = () => {
  return (
    <>
      <h1>HeroesApp</h1>
    </>
  );
};
```

- [Boostrap](https://getbootstrap.com/)
- [Download Heroes](https://import.cdn.thinkific.com/643563/courses/1901683/heroes-220621-112204.zip)

### 14.5 Nota de Actualización - React Router Docs

Antes de iniciar con el siguiente video, la documentación que se presenta en _React router docs_ ha sido actualizada(6.X.X) y ya no se ofrece el mismo quick start.

Para efectos del curso, te recomendamos seguir con la configuración que se presenta en el video de la siguiente lección.

[React Router 7.1.2](https://reactrouter.com/home)

### 14.6 Creando un primer Router

Instalar React Router Dom

```bash
# Instalar React Router
yarn add react-router-dom
yarn add react-router-dom@7.1.2
```

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { BrowserRouter } from "react-router";

import { HeroesApp } from "./HeroesApp";
import "./styles.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <BrowserRouter>
      <HeroesApp />
    </BrowserRouter>
  </StrictMode>
);
```

`src/HeroesApp.jsx`

```jsx
import { AppRouter } from "./router/AppRouter";

export const HeroesApp = () => {
  return (
    <>
      <AppRouter />
    </>
  );
};
```

`src/router/AppRouter.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { MarvelPage } from "../heroes/pages/MarvelPage";
import { DCPage } from "../heroes/pages/DCPage";
import { LoginPage } from "../auth/pages/LoginPage";

export const AppRouter = () => {
  return (
    <>
      <Routes>
        <Route path="marvel" element={<MarvelPage />} />
        <Route path="dc" element={<DCPage />} />
        <Route path="login" element={<LoginPage />} />
        <Route
          path="/"
          element={<Navigate to="/marvel" />}
        />
      </Routes>
    </>
  );
};
```

`src/heroes/pages/MarvelPage.jsx`

```jsx
export const MarvelPage = () => {
  return (
    <>
      <h1>MarvelPage</h1>
    </>
  );
};
```

`src/heroes/pages/DCPage.jsx`

```jsx
export const DCPage = () => {
  return (
    <>
      <h1>DCPage</h1>
    </>
  );
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
export const LoginPage = () => {
  return (
    <>
      <h1>LoginPage</h1>
    </>
  );
};
```

- [[react-hooks-mern#🟣 11. Profundizando Hooks - useContext#4. Preparación de nuestra aplicación con rutas]]
- [React - Migrar React Router V5 a V6](https://www.youtube.com/watch?v=FR7x0tqwafc)
- [React Router Instalation](https://reactrouter.com/start/library/installation)

### 14.7 Colocar clase de la ruta activa

Actualmente tenemos la siguiente estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── assets
│   │   └── heroes
│   │       ├── *.jpg
│   │       └── *.jpg
│   ├── auth
│   │   ├── components
│   │   ├── hooks
│   │   ├── index.js
│   │   └── pages
│   │       ├── index.js
│   │       └── LoginPage.jsx
│   ├── heroes
│   │   ├── components
│   │   ├── helpers
│   │   ├── hooks
│   │   ├── index.js
│   │   └── pages
│   │       ├── DCPage.jsx
│   │       ├── index.js
│   │       └── MarvelPage.jsx
│   ├── HeroesApp.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── ui
│       ├── components
│       │   ├── index.js
│       │   └── Navbar.jsx
│       ├── hooks
│       └── index.js
├── vite.config.js
└── yarn.lock
```

Creamos varios archivos `index.js` para hacer exportaciones de barril, tener en cuenta que este método no es recomendable cuando el proyecto se hace mas grande.

`src/ui/components/Navbar.jsx`

```jsx
import { Link, NavLink } from "react-router";

export const Navbar = () => {
  return (
    <nav className="p-3">
      <Link to="/">Asociaciones</Link>

      <div>
        <NavLink to="marvel">Marvel</NavLink>
        <NavLink to="dc">DC</NavLink>
      </div>

      <div>
        <ul>
          <span>Ghost/Logout</span>
          <button>Logout</button>
        </ul>
      </div>
    </nav>
  );
};
```

`src/router/AppRouter.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { MarvelPage } from "../heroes/pages/MarvelPage";
import { DCPage } from "../heroes/pages/DCPage";
import { LoginPage } from "../auth/pages/LoginPage";
import { Navbar } from "../ui";

export const AppRouter = () => {
  return (
    <>
      <Navbar />
      <Routes>
        <Route path="marvel" element={<MarvelPage />} />
        <Route path="dc" element={<DCPage />} />
        <Route path="login" element={<LoginPage />} />
        <Route
          path="/"
          element={<Navigate to="marvel" />}
        />
      </Routes>
    </>
  );
};
```

`src/ui/components/index.js`

```js
export * from "./Navbar";
```

`src/ui/index.js`

```js
export * from "./components";
```

`src/heroes/pages/index.js`

```js
export * from "./DCPage";
export * from "./MarvelPage";
```

`src/heroes/index.js`

```js
export * from "./pages";
```

`src/auth/pages/index.js`

```js
export * from "./LoginPage";
```

`src/auth/index.js`

```js
export * from "./pages";
```

`src/styles.css

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

a {
  color: azure;
}

.active {
  color: palevioletred;
  font-weight: bold;
}

a:hover {
  color: palevioletred;
  font-weight: bold;
}
```

[Klerith/Navbar.js](https://gist.github.com/Klerith/566b484ac6fe46c8fa949e61df671a18)

### 14.8 Creando un segundo Router

Estructura:

```bash
├── src
│   ├── assets
│   │   └── heroes
│   │       ├── *.jpg
│   │       └── *.jpg
│   ├── auth
│   │   ├── components
│   │   ├── hooks
│   │   ├── index.js
│   │   └── pages
│   │       ├── index.js
│   │       └── LoginPage.jsx
│   ├── heroes
│   │   ├── components
│   │   ├── helpers
│   │   ├── hooks
│   │   ├── index.js
│   │   ├── pages
│   │   │   ├── DCPage.jsx
│   │   │   ├── HeroPage.jsx
│   │   │   ├── index.js
│   │   │   ├── MarvelPage.jsx
│   │   │   └── SearchPage.jsx
│   │   └── routes
│   │       └── HeroesRoutes.jsx
│   ├── HeroesApp.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── ui
│       ├── components
│       │   ├── index.js
│       │   └── Navbar.jsx
│       ├── hooks
│       └── index.js
├── vite.config.js
└── yarn.lock
```


`src/heroes/routes/HeroesRoutes.jsx`

```jsx
import { Navigate, Routes, Route } from "react-router";
import { Navbar } from "../../ui";
import {
  DCPage,
  HeroPage,
  MarvelPage,
  SearchPage,
} from "../pages";

export const HeroesRoutes = () => {
  return (
    <>
      <Navbar />

      <div>
        <Routes>
          <Route path="marvel" element={<MarvelPage />} />
          <Route path="dc" element={<DCPage />} />

          {/* New Routes */}
          <Route path="search" element={<SearchPage />} />
          <Route path="hero" element={<HeroPage />} />

          <Route
            path="/"
            element={<Navigate to="marvel" />}
          />
        </Routes>
      </div>
    </>
  );
};
```

`src/ui/components/Navbar.jsx`

```jsx
import { Link, NavLink } from "react-router";

export const Navbar = () => {
  return (
    <nav className="p-3">
      <Link to="/">Asociaciones</Link>

      <div>
        <NavLink to="/marvel">Marvel</NavLink>
        <NavLink to="/dc">DC</NavLink>
        <NavLink to="/search">Search</NavLink>
      </div>

      <div>
        <ul>
          <span>Ghost/Logout</span>
          <button>Logout</button>
        </ul>
      </div>
    </nav>
  );
};
```

`src/heroes/pages/SearchPage.jsx`

```jsx
export const SearchPage = () => {
  return (
    <>
      <h3>SearchPage</h3>
    </>
  );
};
```

`src/heroes/pages/HeroPage.jsx`

```jsx
export const HeroPage = () => {
  return (
    <>
      <h3>Hero</h3>
    </>
  );
};
```

`src/heroes/pages/index.js`

```js
export * from "./DCPage";
export * from "./MarvelPage";
export * from "./SearchPage";
export * from "./HeroPage";
```

`src/heroes/index.js`

```js
export * from "./pages";
export * from "./routes/HeroesRoutes";
```

`src/router/AppRouter.jsx`

```jsx
import { Route, Routes } from "react-router";

import { LoginPage } from "../auth";
import { HeroesRoutes } from "../heroes";

export const AppRouter = () => {
  return (
    <>
      <Routes>
        <Route path="login" element={<LoginPage />} />
        <Route path="/*" element={<HeroesRoutes />} />
      </Routes>
    </>
  );
};
```

### 14.9 Navigate push / replace - useNavigate

`useNavigate` es un **custom hook** de React Router que permite programáticamente redirigir al usuario a una ruta específica. Es útil para cambiar de página sin usar enlaces `<Link>` o `<Navigate>`.

Uso básico:

```jsx
import { useNavigate } from 'react-router-dom';

function MyComponent() {
  const navigate = useNavigate();

  const handleNavigation = () => {
    navigate('/destination'); // Redirige a "/destination"
  };

  return <button onClick={handleNavigation}>Go to Destination</button>;
}
```

#### Características:

1. **Navegación hacia adelante o atrás**:
    
    ```javascript
    navigate(-1); // Ir hacia atrás
    navigate(1);  // Ir hacia adelante
    ```
    
2. **Reemplazar el historial**:
    
    ```javascript
    navigate('/path', { replace: true }); // No guarda en el historial
    ```
    
3. **Pasar estado**:
    
    ```javascript
    navigate('/path', { state: { key: 'value' } });
    ```

Es ideal para manejar redirecciones después de eventos como formularios o acciones específicas del usuario.

Ahora en nuestro proyecto:

`src/ui/components/Navbar.jsx`

```jsx
import { Link, NavLink, useNavigate } from "react-router";

export const Navbar = () => {
  const navigate = useNavigate();

  const handleLogout = () => {
    navigate("/login", {
      replace: true,
    });
  };

  return (
    <nav className="p-3">
      <Link to="/">Asociaciones</Link>

      <div>
        <NavLink to="/marvel">Marvel</NavLink>
        <NavLink to="/dc">DC</NavLink>
        <NavLink to="/search">Search</NavLink>
      </div>

      <div>
        <ul>
          <span>Ghost/Logout</span>
          <button onClick={handleLogout}>Logout</button>
        </ul>
      </div>
    </nav>
  );
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
import { useNavigate } from "react-router-dom";

export const LoginPage = () => {
  const navigate = useNavigate();

  const handleLogin = () => {
    navigate("/", {
      replace: true,
    });
  };

  return (
    <div className="container mt-5">
      <h1>Login</h1>
      <hr />

      <button onClick={handleLogin}>Login</button>
    </div>
  );
};
```

### 14.10 Lista de Heroes

Estructura actual:

```bash
├── src
│   ├── assets
│   │   └── heroes
│   │       ├── *.jpg
│   │       └── *.jpg
│   ├── auth
│   │   ├── components
│   │   ├── hooks
│   │   ├── index.js
│   │   └── pages
│   │       ├── index.js
│   │       └── LoginPage.jsx
│   ├── heroes
│   │   ├── components
│   │   │   ├── HeroList.jsx
│   │   │   └── index.js
│   │   ├── data
│   │   │   └── heroes.js
│   │   ├── helpers
│   │   │   ├── getHeroesByPublisher.js
│   │   │   └── index.js
│   │   ├── hooks
│   │   ├── index.js
│   │   ├── pages
│   │   │   ├── DCPage.jsx
│   │   │   ├── HeroPage.jsx
│   │   │   ├── index.js
│   │   │   ├── MarvelPage.jsx
│   │   │   └── SearchPage.jsx
│   │   └── routes
│   │       └── HeroesRoutes.jsx
│   ├── HeroesApp.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── ui
│       ├── components
│       │   ├── index.js
│       │   └── Navbar.jsx
│       ├── hooks
│       └── index.js
├── vite.config.js
└── yarn.lock
```

`src/heroes/data/heroes.js`

```js
export const heroes = [
  {
    id: "dc-batman",
    superhero: "Batman",
    publisher: "DC Comics",
    alter_ego: "Bruce Wayne",
    first_appearance: "Detective Comics #27",
    characters: "Bruce Wayne",
  },
  {
    id: "dc-superman",
    superhero: "Superman",
    publisher: "DC Comics",
    alter_ego: "Kal-El",
    first_appearance: "Action Comics #1",
    characters: "Kal-El",
  },
  {
    id: "dc-flash",
    superhero: "Flash",
    publisher: "DC Comics",
    alter_ego: "Jay Garrick",
    first_appearance: "Flash Comics #1",
    characters:
      "Jay Garrick, Barry Allen, Wally West, Bart Allen",
  },
  {
    id: "dc-green",
    superhero: "Green Lantern",
    publisher: "DC Comics",
    alter_ego: "Alan Scott",
    first_appearance: "All-American Comics #16",
    characters:
      "Alan Scott, Hal Jordan, Guy Gardner, John Stewart, Kyle Raynor, Jade, Sinestro, Simon Baz",
  },
  {
    id: "dc-arrow",
    superhero: "Green Arrow",
    publisher: "DC Comics",
    alter_ego: "Oliver Queen",
    first_appearance: "More Fun Comics #73",
    characters: "Oliver Queen",
  },
  {
    id: "dc-wonder",
    superhero: "Wonder Woman",
    publisher: "DC Comics",
    alter_ego: "Princess Diana",
    first_appearance: "All Star Comics #8",
    characters: "Princess Diana",
  },
  {
    id: "dc-martian",
    superhero: "Martian Manhunter",
    publisher: "DC Comics",
    alter_ego: "J'onn J'onzz",
    first_appearance: "Detective Comics #225",
    characters: "Martian Manhunter",
  },
  {
    id: "dc-robin",
    superhero: "Robin/Nightwing",
    publisher: "DC Comics",
    alter_ego: "Dick Grayson",
    first_appearance: "Detective Comics #38",
    characters: "Dick Grayson",
  },
  {
    id: "dc-blue",
    superhero: "Blue Beetle",
    publisher: "DC Comics",
    alter_ego: "Dan Garret",
    first_appearance: "Mystery Men Comics #1",
    characters: "Dan Garret, Ted Kord, Jaime Reyes",
  },
  {
    id: "dc-black",
    superhero: "Black Canary",
    publisher: "DC Comics",
    alter_ego: "Dinah Drake",
    first_appearance: "Flash Comics #86",
    characters: "Dinah Drake, Dinah Lance",
  },
  {
    id: "marvel-spider",
    superhero: "Spider Man",
    publisher: "Marvel Comics",
    alter_ego: "Peter Parker",
    first_appearance: "Amazing Fantasy #15",
    characters: "Peter Parker",
  },
  {
    id: "marvel-captain",
    superhero: "Captain America",
    publisher: "Marvel Comics",
    alter_ego: "Steve Rogers",
    first_appearance: "Captain America Comics #1",
    characters: "Steve Rogers",
  },
  {
    id: "marvel-iron",
    superhero: "Iron Man",
    publisher: "Marvel Comics",
    alter_ego: "Tony Stark",
    first_appearance: "Tales of Suspense #39",
    characters: "Tony Stark",
  },
  {
    id: "marvel-thor",
    superhero: "Thor",
    publisher: "Marvel Comics",
    alter_ego: "Thor Odinson",
    first_appearance: "Journey into Myster #83",
    characters: "Thor Odinson",
  },
  {
    id: "marvel-hulk",
    superhero: "Hulk",
    publisher: "Marvel Comics",
    alter_ego: "Bruce Banner",
    first_appearance: "The Incredible Hulk #1",
    characters: "Bruce Banner",
  },
  {
    id: "marvel-wolverine",
    superhero: "Wolverine",
    publisher: "Marvel Comics",
    alter_ego: "James Howlett",
    first_appearance: "The Incredible Hulk #180",
    characters: "James Howlett",
  },
  {
    id: "marvel-daredevil",
    superhero: "Daredevil",
    publisher: "Marvel Comics",
    alter_ego: "Matthew Michael Murdock",
    first_appearance: "Daredevil #1",
    characters: "Matthew Michael Murdock",
  },
  {
    id: "marvel-hawkeye",
    superhero: "Hawkeye",
    publisher: "Marvel Comics",
    alter_ego: "Clinton Francis Barton",
    first_appearance: "Tales of Suspense #57",
    characters: "Clinton Francis Barton",
  },
  {
    id: "marvel-cyclops",
    superhero: "Cyclops",
    publisher: "Marvel Comics",
    alter_ego: "Scott Summers",
    first_appearance: "X-Men #1",
    characters: "Scott Summers",
  },
  {
    id: "marvel-silver",
    superhero: "Silver Surfer",
    publisher: "Marvel Comics",
    alter_ego: "Norrin Radd",
    first_appearance: "The Fantastic Four #48",
    characters: "Norrin Radd",
  },
];
```

`src/heroes/helpers/getHeroesByPublisher.js`

```jsx
import { heroes } from "../data/heroes";

export const getHeroesByPublisher = (publisher) => {
  const validPublishers = ["DC Comics", "Marvel Comics"];

  if (!validPublishers.includes(publisher)) {
    throw new Error(
      `${publisher} is not a valid publisher`
    );
  }

  return heroes.filter(
    (heroe) => heroe.publisher === publisher
  );
};
```

`src/heroes/helpers/index.js`

```js
export * from "./getHeroesByPublisher";
```

`src/heroes/components/HeroList.jsx`

```jsx
import React from "react";
import { getHeroesByPublisher } from "../helpers";

export const HeroList = ({ publisher }) => {
  const heroes = getHeroesByPublisher(publisher);

  return (
    <ul>
      {heroes.map((hero) => {
        return <li key={hero.id}>{hero.superhero}</li>;
      })}
    </ul>
  );
};
```

`src/heroes/components/index.js`

```js
export * from "./HeroList";
```

`src/heroes/pages/DCPage.jsx`

```jsx
import { HeroList } from "../components";

export const DCPage = () => {
  const publisher = "DC Comics";

  return (
    <>
      <h1>{publisher}</h1>
      <hr />

      <HeroList publisher={publisher} />
    </>
  );
};
```

`src/heroes/pages/MarvelPage.jsx`

```jsx
import { HeroList } from "../components";

export const MarvelPage = () => {
  const publisher = "Marvel Comics";

  return (
    <>
      <h1>{publisher}</h1>
      <hr />

      <HeroList publisher={publisher} />
    </>
  );
};
```

[HeroesList - Data](https://gist.github.com/Klerith/934da045caae0fec3a1067d013926c46)

### 14.11 Tarjetas con la información del Héroe

`src/heroes/components/HeroList.jsx`

```jsx
import { HeroCard } from "./HeroCard";
import { getHeroesByPublisher } from "../helpers";

export const HeroList = ({ publisher }) => {
  const heroes = getHeroesByPublisher(publisher);

  return (
    <div className="row rows-cols-1 row-cols-md-3 g-3">
      {heroes.map((hero) => {
        return <HeroCard key={hero.id} {...hero} />;
      })}
    </div>
  );
};
```

`src/heroes/components/index.js`

```js
export * from "./HeroCard";
export * from "./HeroList";
```

`src/heroes/components/HeroCard.jsx`

```jsx
export const HeroCard = ({
  id,
  superhero,
  publisher,
  alter_ego,
  first_appearance,
  characters,
}) => {
  const heroImageUrl = `./assets/heroes/${id}.jpg`;

  return (
    <div className="col">
      <div className="card">
        <div className="row no-gutters">
          <div className="col-4">
            <img
              className="card-img"
              src={heroImageUrl}
              alt={superhero}
            />
          </div>

          <div className="col-8">
            <div className="card-body">
              <h5>{superhero}</h5>
              <p className="card-text">{alter_ego}</p>

              <p>{characters}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  );
};
```

### 14.12 Tarjeta del Héroe - parte 2

`src/heroes/components/HeroCard.jsx`

```jsx
import { Link } from "react-router-dom";

const CharactersByHero = ({ alter_ego, characters }) => {
  // if (alter_ego === characters) return <></>;
  // return <p>{characters}</p>;

  return alter_ego === characters ? (
    <></>
  ) : (
    <p>{characters}</p>
  );
};

export const HeroCard = ({
  id,
  superhero,
  publisher,
  alter_ego,
  first_appearance,
  characters,
}) => {
  const heroImageUrl = `./assets/heroes/${id}.jpg`;
  // const charactersByHero = <p>{characters}</p>;

  return (
    <div className="col">
      <div className="card">
        <div className="row no-gutters">
          <div className="col-4">
            <img
              className="card-img"
              src={heroImageUrl}
              alt={superhero}
            />
          </div>

          <div className="col-8">
            <div className="card-body">
              <h5>{superhero}</h5>
              <p className="card-text">{alter_ego}</p>

              {/* {alter_ego !== characters && charactersByHero} */}

              <CharactersByHero
                characters={characters}
                alter_ego={alter_ego}
              />

              <p>
                <small>{first_appearance}</small>
              </p>

              <Link to={`/hero/${id}`}>More...</Link>
            </div>
          </div>
        </div>
      </div>
    </div>
  );
};
```

### 14.13 Leer argumentos por URL

`useParams` es un **hook** de React Router que se utiliza para acceder a los parámetros de la URL dinámica en una aplicación React.

Uso básico:

Cuando defines rutas con parámetros en React Router, como `/:id`, puedes usar `useParams` para acceder al valor de esos parámetros.

```jsx
import { useParams } from 'react-router-dom';

function ProductDetail() {
  const { id } = useParams(); // Extrae el parámetro "id" de la URL

  return <h1>Detalles del producto con ID: {id}</h1>;
}
```

#### Ejemplo de configuración de rutas:

```jsx
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
import ProductDetail from './ProductDetail';

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/product/:id" element={<ProductDetail />} />
      </Routes>
    </Router>
  );
}
```

#### Características:

1. **Devuelve un objeto**:
    
    - Cada parámetro de la URL es una clave en el objeto devuelto por `useParams`.
    - Ejemplo: Para la URL `/product/123`, `useParams()` devuelve `{ id: "123" }`.
2. **Siempre devuelve strings**:
    
    - Los valores siempre se manejan como cadenas, incluso si parecen números.
3. **Uso con múltiples parámetros**:
    
    ```jsx
    const { category, id } = useParams();
    // Para una ruta como /category/electronics/product/123
    // useParams() devolverá: { category: "electronics", id: "123" }
    ```
    

Es útil para obtener información dinámica de la URL, como identificadores o nombres, en aplicaciones basadas en rutas.

En nuestro proyecto:

Estructura:

```bash
├── src
│   ├── auth
│   │   ├── components
│   │   ├── hooks
│   │   ├── index.js
│   │   └── pages
│   │       ├── index.js
│   │       └── LoginPage.jsx
│   ├── heroes
│   │   ├── components
│   │   │   ├── HeroCard.jsx
│   │   │   ├── HeroList.jsx
│   │   │   └── index.js
│   │   ├── data
│   │   │   └── heroes.js
│   │   ├── helpers
│   │   │   ├── getHeroById.js
│   │   │   ├── getHeroesByPublisher.js
│   │   │   └── index.js
│   │   ├── hooks
│   │   ├── index.js
│   │   ├── pages
│   │   │   ├── DCPage.jsx
│   │   │   ├── HeroPage.jsx
│   │   │   ├── index.js
│   │   │   ├── MarvelPage.jsx
│   │   │   └── SearchPage.jsx
│   │   └── routes
│   │       └── HeroesRoutes.jsx
│   ├── HeroesApp.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── ui
│       ├── components
│       │   ├── index.js
│       │   └── Navbar.jsx
│       ├── hooks
│       └── index.js
├── vite.config.js
└── yarn.lock
```

`src/heroes/pages/HeroPage.jsx`

```jsx
import { Navigate, useParams } from "react-router";
import { getHeroById } from "../helpers";

export const HeroPage = () => {
  const { id } = useParams();
  const hero = getHeroById(id);

  console.log(hero);

  if (!hero) {
    return <Navigate to="/marvel" />;
  }

  return (
    <>
      <h1>{hero.superhero}</h1>
    </>
  );
};
```

`src/heroes/helpers/getHeroById.js`

```jsx
import { heroes } from "../data/heroes";

export const getHeroById = (id) => {
  return heroes.find((hero) => hero.id === id);

  // Undefined.hero
};
```

`src/heroes/helpers/index.js`

```js
export * from "./getHeroById";
export * from "./getHeroesByPublisher";
```

`src/heroes/routes/HeroesRoutes.jsx`

```jsx
import { Navigate, Routes, Route } from "react-router";
import { Navbar } from "../../ui";
import {
  DCPage,
  HeroPage,
  MarvelPage,
  SearchPage,
} from "../pages";

export const HeroesRoutes = () => {
  return (
    <>
      <Navbar />

      <div className="container">
        <Routes>
          <Route path="marvel" element={<MarvelPage />} />
          <Route path="dc" element={<DCPage />} />

          {/* New Routes */}
          <Route path="search" element={<SearchPage />} />

          {/* :id es solo un nombre */}
          <Route path="hero/:id" element={<HeroPage />} />

          <Route
            path="/"
            element={<Navigate to="marvel" />}
          />
        </Routes>
      </div>
    </>
  );
};
```

Nota: React Components/Route.Provider/value/matches/{params}

[Route-params](https://reactrouter.com/start/library/url-values#route-params)

### 14.14 Estilo del componente HeroScreen

#### Dudas sobre rutas

Dentro del proyecto se usa el archivo `HeroPage.jsx` justo en la ruta `07-heroes-spa/src/heroes/pages`. En dicho archivo se usan imágenes que están en la ruta `07-heroes-spa/assets/heroes`.

Mi duda es, ¿por qué al colocar dentro de un elemento `img` la ruta `src={`/assets/heroes/${hero.id}.jpg`}` funciona? ¿No se supone que tengo que navegar hasta esa ruta? Algo así como lo siguiente  `../../../assets/heroes`...

##### ¿Por qué funciona `/assets/heroes/...`?

La razón por la cual la ruta `src={`/assets/heroes/${hero.id}.jpg`}` funciona en tu archivo `HeroPage.jsx` se debe a cómo los bundlers modernos como Vite manejan las rutas de los recursos y cómo está configurado tu proyecto.

En tu proyecto, no tienes una carpeta `public`, pero cuando usas una ruta que comienza con `/assets/...`, Vite trata esa ruta como relativa a la raíz del proyecto durante el tiempo de desarrollo y como una ruta pública después del build.

1. **Vite trata `/assets/...` como una ruta pública:**
    
    - Cuando defines recursos estáticos (como imágenes) dentro de una carpeta como `assets` en la raíz del proyecto, Vite los expone automáticamente como recursos accesibles mediante rutas absolutas a partir de `/assets/...`.
    - Esto significa que, aunque técnicamente el archivo `HeroPage.jsx` está en una ubicación anidada, puedes usar rutas absolutas (`/assets/...`) sin necesidad de navegar usando `../../../`.
2. **Comportamiento en desarrollo y producción:**
    
    - Durante el desarrollo, Vite sirve los archivos directamente desde el sistema de archivos, haciendo que la ruta `/assets/...` sea válida.
    - En producción, Vite empaqueta los recursos estáticos, optimiza las rutas, y se asegura de que `/assets/...` apunte a los archivos correctos en el build.
3. **Diferencia entre rutas absolutas y relativas:**
    
    - Si usaras una ruta relativa como `../../../assets/heroes/${hero.id}.jpg`, funcionaría también, pero está vinculada a la estructura actual de carpetas, lo que puede volverse complicado si cambias la ubicación del archivo `HeroPage.jsx`.
    - La ruta absoluta `/assets/...` es más robusta porque no depende de la ubicación del archivo que la referencia.

Ejemplo en contexto:

Supongamos que tienes la siguiente estructura de archivos y el ID del héroe es `superman`:

- Archivo de imagen: `07-heroes-spa/assets/heroes/superman.jpg`
- Archivo `HeroPage.jsx`: `07-heroes-spa/src/heroes/pages/HeroPage.jsx`

Si usas:

```jsx
<img src={`/assets/heroes/${hero.id}.jpg`} alt={hero.name} />
```

Esta ruta es procesada automáticamente por Vite para que apunte al archivo correcto, sin importar la ubicación del archivo `HeroPage.jsx`.

Nota adicional:

Si decides mover la carpeta `assets` dentro de `src`, necesitarías ajustar las rutas ya que Vite no manejaría automáticamente los recursos como públicos. En ese caso, tendrías que importar explícitamente las imágenes o usar rutas relativas. Por ejemplo:

```jsx
import supermanImage from '../../assets/heroes/superman.jpg';

<img src={supermanImage} alt="Superman" />
```

Esto es útil cuando prefieres importar directamente los archivos en lugar de usar rutas públicas. Sin embargo, con tu configuración actual, `/assets/...` es más práctico y directo.

En nuestro proyecto:

`src/heroes/pages/HeroPage.jsx`

```jsx
import {
  Navigate,
  useNavigate,
  useParams,
} from "react-router";
import { getHeroById } from "../helpers";

export const HeroPage = () => {
  const { id } = useParams();
  const navigate = useNavigate();
  const hero = getHeroById(id);

  // console.log(hero);
  const handleNavigateBack = () => {
    navigate(-1);
  };

  if (!hero) {
    return <Navigate to="/marvel" />;
  }

  return (
    <div>
      <div className="col-4">
        <img
          src={`/assets/heroes/${hero.id}.jpg`}
          alt={hero.superhero}
          className="img-thumbnail"
        />
      </div>

      <div className="col-8">
        <h3>{hero.superhero}</h3>
        <ul>
          <li>
            <b>Alter ego:</b> {hero.alter_ego}
          </li>
          <li>
            <b>Publisher:</b> {hero.publisher}
          </li>
          <li>
            <b>First appearance:</b> {hero.first_appearance}
          </li>
        </ul>

        <h5>Characters</h5>
        <p>{hero.characters}</p>

        <button onClick={handleNavigateBack}>Return</button>
      </div>
    </div>
  );
};
```

### 14.15 Nota: useMemo

`src/heroes/pages/HeroPage.jsx`

```jsx
import { useMemo } from "react";
import {
  Navigate,
  useNavigate,
  useParams,
} from "react-router";
import { getHeroById } from "../helpers";

export const HeroPage = () => {
  const { id } = useParams();
  const navigate = useNavigate();

  // Cuando el id cambie se volvera a ejecutar
  const hero = useMemo(() => getHeroById(id), [id]);

  const handleNavigateBack = () => {
    navigate(-1);
  };

  if (!hero) {
    return <Navigate to="/marvel" />;
  }

  return (
    <div>
      <div className="col-4">
        <img
          src={`/assets/heroes/${hero.id}.jpg`}
          alt={hero.superhero}
          className="img-thumbnail"
        />
      </div>

      <div className="col-8">
        <h3>{hero.superhero}</h3>
        <ul>
          <li>
            <b>Alter ego:</b> {hero.alter_ego}
          </li>
          <li>
            <b>Publisher:</b> {hero.publisher}
          </li>
          <li>
            <b>First appearance:</b> {hero.first_appearance}
          </li>
        </ul>

        <h5>Characters</h5>
        <p>{hero.characters}</p>

        <button onClick={handleNavigateBack}>Return</button>
      </div>
    </div>
  );
};
```

`src/heroes/components/HeroList.jsx`

```jsx
import { useMemo } from "react";
import { HeroCard } from "./HeroCard";
import { getHeroesByPublisher } from "../helpers";

export const HeroList = ({ publisher }) => {
  const heroes = useMemo(
    () => getHeroesByPublisher(publisher),
    [publisher]
  );

  return (
    <div className="row rows-cols-1 row-cols-md-3 g-3">
      {heroes.map((hero) => {
        return <HeroCard key={hero.id} {...hero} />;
      })}
    </div>
  );
};
```

### 14.16 Animaciones en nuestro componente

En esta clase se usa **Animate style** para añadir animaciones, para más detalles revisar la documentación. 

Añadimos el CDN en el `index`.

`index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link
      rel="icon"
      type="image/svg+xml"
      href="/vite.svg"
    />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />

    <title>Vite + React</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
      crossorigin="anonymous"
    />
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
    />
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>

    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

`src/heroes/components/HeroCard.jsx`

```jsx
  return (
    <div className="col animate__animated animate__fadeIn">
    </div>
  );
```

`src/heroes/pages/HeroPage.jsx`

```jsx
  return (
    <div>
      <div className="col-4">
        <img
          src={`/assets/heroes/${hero.id}.jpg`}
          alt={hero.superhero}
          className="img-thumbnail animate__animated animate__fadeInLeft"
        />
      </div>
    </div>
  );
```

[Animate CSS](https://animate.style/)

### 14.17 Diseño de la pantalla de búsqueda

`src/ui/components/Navbar.jsx`

```jsx
import { Link, NavLink, useNavigate } from "react-router";

export const Navbar = () => {
  const navigate = useNavigate();

  const handleLogout = () => {
    navigate("/login", {
      replace: true,
    });
  };

  return (
    <nav className="p-3">
      <Link to="/">Asociaciones</Link>

      <div>
        <NavLink to="/marvel">Marvel</NavLink>
        <NavLink to="/dc">DC</NavLink>
        <NavLink to="/search">Search</NavLink> 👈👀
      </div>

      <div>
        <ul>
          <span>Ghost/Logout</span>
          <button onClick={handleLogout}>Logout</button>
        </ul>
      </div>
    </nav>
  );
};
```

`src/heroes/pages/SearchPage.jsx`

```jsx
import { HeroCard } from "../components/HeroCard";

export const SearchPage = () => {
  return (
    <>
      <h1>Search</h1>
      <hr />

      <div>
        <h4>Searching</h4>
        <hr />
        <form action="">
          <input
            type="text"
            placeholder="Search a hero"
            name="searchText"
            autoComplete="off"
          />
          <button>Search</button>
        </form>
      </div>

      <div>
        <h4>Results</h4>
        <hr />

        <div>Search a Hero</div>
        <div>
          There's no results <b>QUERY</b>
        </div>

        {/* <HeroCard/> */}
      </div>
    </>
  );
};
```

### 14.18 SearchComponent

Los **query parameters** en JavaScript (y React) son valores adicionales que se envían en una URL tras el signo de interrogación (`?`) como pares clave-valor. Por ejemplo, en la URL:

```
https://example.com?page=1&sort=asc
```

`page` y `sort` son query parameters.

#### Manejo en JavaScript puro

Puedes usar la interfaz `URLSearchParams` para trabajar con ellos:

```javascript
// Obtiene la URL actual
const url = new URL(window.location.href);
const params = new URLSearchParams(url.search);

// Obtener un parámetro
const page = params.get('page'); // "1"

// Agregar o actualizar un parámetro
params.set('filter', 'active');

// Eliminar un parámetro
params.delete('sort');

// Convertir a string para actualizar la URL
console.log(params.toString()); // "page=1&filter=active"
```

### Manejo en React

En React, los query parameters se manejan comúnmente con herramientas como `react-router-dom`.

1. **Acceder a los query parameters**: Utilizando `useSearchParams` (React Router v6+):

```javascript
import { useSearchParams } from 'react-router-dom';

function MyComponent() {
  const [searchParams, setSearchParams] = useSearchParams();

  // Leer parámetros
  const page = searchParams.get('page'); // "1"

  // Actualizar parámetros
  const updateParams = () => {
    setSearchParams({ page: '2', sort: 'desc' });
  };

  return (
    <div>
      <p>Page: {page}</p>
      <button onClick={updateParams}>Actualizar</button>
    </div>
  );
}
```

2. **Sincronización con la URL**: Cambiar los parámetros actualiza la URL automáticamente, y puedes usar rutas dinámicas para mantenerlas organizadas.

#### Buenas prácticas

- **Validación de valores**: Siempre verifica los valores antes de usarlos.
- **Evitar sobrecargar la URL**: Usa los query parameters solo para datos que necesiten ser persistidos en la URL.
- **Codificación**: Usa `encodeURIComponent` para codificar valores especiales.
- **Estado vs Query Parameters**: Usa query parameters solo para datos relacionados con la navegación, no para manejar todo el estado de la aplicación.

Ahora en nuestro proyecto usaremos el paquete `query-string`

```bash
# Install query-strings
yarn add query-string
```

Copiamos el `Custom Hook: useForm.jsx` que creamos y subimos a GitHub con anterioridad.

`src/heroes/hooks/useForm.jsx`

```jsx
import { useState } from "react";

export const useForm = (initialForm = {}) => {
  const [formState, setFormState] = useState(initialForm);

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  const handleResetForm = () => {
    setFormState(initialForm);
  };

  return {
    ...formState,
    formState,
    handleInputChange,
    handleResetForm,
  };
};
```

`src/heroes/pages/SearchPage.jsx`

```jsx
import { useLocation, useNavigate } from "react-router";
import queryString from "query-string";

import { useForm } from "../hooks/useForm";
import { HeroCard } from "../components";

export const SearchPage = () => {
  const { searchText, handleInputChange } = useForm({
    searchText: "",
  });

  const navigate = useNavigate();
  const location = useLocation();

  const { q = "" } = queryString.parse(location.search);

  console.log(q);

  const handleSearchSubmit = (event) => {
    event.preventDefault();

    if (searchText.trim().length <= 1) return;

    navigate(`?q=${searchText}`);
  };

  return (
    <>
      <h1>Search</h1>
      <hr />

      <div>
        <h4>Searching</h4>
        <hr />
        <form action="" onSubmit={handleSearchSubmit}>
          <input
            type="text"
            autoComplete="off"
            placeholder="Search a hero"
            name="searchText"
            value={searchText}
            onChange={handleInputChange}
          />
          <button>Search</button>
        </form>
      </div>

      <div>
        <h4>Results</h4>
        <hr />

        <div>Search a Hero</div>
        <div>
          There's no results <b>{q}</b>
        </div>

        {/* <HeroCard/> */}
      </div>
    </>
  );
};
```

Una alternativa al paquete que instalamos es directamente usar `useSearchParams()` de [React Router](https://reactrouter.com/start/library/url-values#url-search-params).



- [Repo: Custom Hook - useForm](https://github.com/Klerith/custom-hooks/blob/main/useForm/useForm.js)
- [Mi repo: useForm](https://github.com/aleroses/custom-hooks/blob/master/useForm/useForm.js)
- [Paquete: Query-string](https://classic.yarnpkg.com/en/package/query-string)
- [Doc query-string](https://github.com/sindresorhus/query-string)

### 14.19 Mostrar listado de héroes

`src/heroes/helpers/getHeroByName.js`

```js
import { heroes } from "../data/heroes";

export const getHeroByName = (name = "") => {
  name = name.toLocaleLowerCase().trim();

  if (name.length === 0) return [];

  return heroes.filter((hero) =>
    hero.superhero.toLocaleLowerCase().includes(name)
  );
};
```

`src/heroes/helpers/index.js`

```js
export * from "./getHeroById";
export * from "./getHeroByName";
export * from "./getHeroesByPublisher";
```

`src/heroes/pages/SearchPage.jsx`

```jsx
import { useLocation, useNavigate } from "react-router";
import queryString from "query-string";

import { useForm } from "../hooks/useForm";
import { HeroCard } from "../components";
import { getHeroByName } from "../helpers";

export const SearchPage = () => {
  const { searchText, handleInputChange } = useForm({
    searchText: "", // q
  });

  const navigate = useNavigate();
  const location = useLocation();

  const { q } = queryString.parse(location.search);

  const heroes = getHeroByName(q);

  console.log(q);

  const handleSearchSubmit = (event) => {
    event.preventDefault();

    if (searchText.trim().length <= 1) return;

    navigate(`?q=${searchText}`);
  };

  return (
    <>
      <h1>Search</h1>
      <hr />

      <div>
        <h4>Searching</h4>
        <hr />
        <form action="" onSubmit={handleSearchSubmit}>
          <input
            type="text"
            autoComplete="off"
            placeholder="Search a hero"
            name="searchText"
            value={searchText}
            onChange={handleInputChange}
          />
          <button>Search</button>
        </form>
      </div>

      <div>
        <h4>Results</h4>
        <hr />

        <div>Search a Hero</div>
        <div>
          There's no results <b>{q}</b>
        </div>

        {heroes.map((hero) => (
          <HeroCard key={hero.id} {...hero} />
        ))}
      </div>
    </>
  );
};
```

### 14.20 Mostrar mensajes condicionales

`src/heroes/pages/SearchPage.jsx`

```jsx
import { useLocation, useNavigate } from "react-router";
import queryString from "query-string";

import { useForm } from "../hooks/useForm";
import { HeroCard } from "../components";
import { getHeroByName } from "../helpers";

export const SearchPage = () => {
  const navigate = useNavigate();
  const location = useLocation();

  const { q } = queryString.parse(location.search);
  const heroes = getHeroByName(q);

  const showSearch = q?.length === 0;
  const showError = q?.length > 0 && heroes?.length === 0;

  const { searchText, handleInputChange } = useForm({
    searchText: q || "", // ""
  });

  console.log(q);

  const handleSearchSubmit = (event) => {
    event.preventDefault();

    // if (searchText.trim().length <= 1) return;

    navigate(`?q=${searchText}`);
  };

  return (
    <>
      <h1>Search</h1>
      <hr />

      <div>
        <h4>Searching</h4>
        <hr />
        <form action="" onSubmit={handleSearchSubmit}>
          <input
            type="text"
            autoComplete="off"
            placeholder="Search a hero"
            name="searchText"
            value={searchText}
            onChange={(e) => handleInputChange(e)}
          />
          <button>Search</button>
        </form>
      </div>

      <div>
        <h4>Results</h4>
        <hr />

        {/* First method */}
        {/* {q === "" ? (
          <div>Search a Hero</div>
        ) : (
          heroes.length === 0 && (
            <div>
              There's no results <b>{q}</b>
            </div>
          )
        )} */}

        {/* Second method */}
        <div style={{ display: showSearch ? "" : "none" }}>
          Search a Hero
        </div>
        <div style={{ display: showError ? "" : "none" }}>
          There's no results <b>{q}</b>
        </div>

        {heroes.map((hero) => (
          <HeroCard key={hero.id} {...hero} />
        ))}
      </div>
    </>
  );
};
```

### 14.21 Nota de actualización - Error imágenes producción

Si quieren hacer el build de la app para hacer el deploy, si se fijan verán que los assets con las imágenes no se copian automáticamente a la carpeta dist con el build de producción.

Esto es debido a Vite y como estamos creando las URL's de las imágenes en HeroCard.jsx.

Si importamos directamente una imagen con `import imgUrl from '/assets/heroes/marvel-spider.jpg'`, Vite se encargará de gestionarlo y añadirá el archivo al build de producción, pero nosotros estamos creando la URL con ``const heroImageUrl = `/assets/heroes/${ id }.jpg`;``, de ahí que Vite no las copie automáticamente.

La solución sería crear una carpeta llamada **public** en la raíz del proyecto (al mismo nivel que `package.json` o `index.html`) y dentro de esta carpeta mover la carpeta **heroes** que contiene todas las imágenes.

De esta forma ya añadimos la carpeta heroes al build de producción.

Para acceder a "public" tenemos que usar la ruta raíz /, por lo que ahora modificaremos la URL de heroImageUrl en el archivo HeroCard.jsx quedando: `const heroImageUrl = `/heroes/${ id }.jpg`;`.

De esta forma ya se copian automáticamente las imágenes, y funciona nuestra app tanto en desarrollo como producción.

Si quieren leer más sobre los assets y cómo manejarlos en Vite: [https://vitejs.dev/guide/assets.html](https://vitejs.dev/guide/assets.html).

[Super Hero Api](https://www.superheroapi.com/)

### 14.22 Código fuente de la sección

Aquí les dejo el código fuente tal cual lo dejé al final de la clase anterior, por si lo necesitan comparar contra el mío.

[**Github - Fin sección 14**](https://github.com/Klerith/react-heroes/tree/fin-seccion-14)

## 🟣 15. Protección de rutas

### 15.1 Introducción a la sección

### 15.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Rutas públicas
- Rutas privadas
- Login y logout - Sin backend aún
- Recordar cuál fue la última ruta visitada para mejorar la experiencia de usuario.
- Context
- Reducer

Esta es una sección pequeña pero importante para trabajar las bases de la autenticación y protección de nuestra aplicación.

### 15.3 Demostración del objetivo al final de la sección

### 15.4 Continuación de proyecto - Protección de Rutas

En todo momento toda la aplicación debe saber si el usuario está autenticado o no. Para hacer esto usaremos `context`.

La estructura actual es esta:

```bash
.
├── assets
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── auth 🔥
│   │   ├── components
│   │   ├── context 👈👀
│   │   ├── hooks
│   │   ├── index.js
│   │   ├── pages
│   │   │   ├── index.js
│   │   │   └── LoginPage.jsx
│   │   └── types 👈👀
│   ├── heroes
│   │   ├── components
│   │   │   ├── HeroCard.jsx
│   │   │   ├── HeroList.jsx
│   │   │   └── index.js
│   │   ├── data
│   │   │   └── heroes.js
│   │   ├── helpers
│   │   │   ├── getHeroById.js
│   │   │   ├── getHeroByName.js
│   │   │   ├── getHeroesByPublisher.js
│   │   │   └── index.js
│   │   ├── hooks
│   │   │   └── useForm.jsx
│   │   ├── index.js
│   │   ├── pages
│   │   │   ├── DCPage.jsx
│   │   │   ├── HeroPage.jsx
│   │   │   ├── index.js
│   │   │   ├── MarvelPage.jsx
│   │   │   └── SearchPage.jsx
│   │   └── routes
│   │       └── HeroesRoutes.jsx
│   ├── HeroesApp.jsx
│   ├── hook
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── ui
│       ├── components
│       │   ├── index.js
│       │   └── Navbar.jsx
│       ├── hooks
│       └── index.js
├── vite.config.js
└── yarn.lock
```

### 15.5 Context y Reducer de mi aplicación

Antes un ejemplo de Context y Reducer:

![Context + Reducer](https://i.postimg.cc/vH8rhB9K/15-use-Reducer.png)

`src/auth/types/types.js`

```js
export const types = {
  login: "[Auth] Login",
  logout: "[Auth] Logout",
};
```

`src/auth/context/AuthContext.jsx`

```jsx
import { createContext } from "react";

export const AuthContext = createContext();
```

`src/auth/context/AuthProvider.jsx`

```jsx
import React, { useReducer } from "react";
import { authReducer } from "./authReducer";

const initialState = {
  logged: false,
};

export const AuthProvider = ({ children }) => {
  const [authState, dispatch] = useReducer(
    authReducer,
    initialState
  );

  return (
    <AuthContext.Provider value={{}}>
      {children}
    </AuthContext.Provider>
  );
};
```

`src/auth/context/index.js`

```js
export * from "./AuthContext";
export * from "./AuthProvider";
export * from "./authReducer";
```

`src/auth/index.js`

```js
export * from "./pages";
export * from "./context";
```

`src/HeroesApp.jsx`

```jsx
import { AuthProvider } from "./auth";
import { AppRouter } from "./router/AppRouter";

export const HeroesApp = () => {
  return (
    <AuthProvider>
      <AppRouter />
    </AuthProvider>
  );
};
```

`src/auth/context/authReducer.js`

```js
import { types } from "../types/types";

// const initialState = {
//   logged: false,
// };

export const authReducer = (state = {}, action) => {
  switch (action.type) {
    case types.login:
      return {
        ...state,
        logged: true,
        name: action.payload,
      };
    case types.logout:
      return {
        logged: false,
      };

    default:
      return state;
  }
};
```

### 15.6 Login de un usuario

`src/auth/context/AuthProvider.jsx`

```jsx
import React, { useReducer } from "react";
import { authReducer } from "./authReducer";

import { types } from "../types/types";
import { AuthContext } from "./AuthContext";

const initialState = {
  logged: false,
};

export const AuthProvider = ({ children }) => {
  const [authState, dispatch] = useReducer(
    authReducer,
    initialState
  );

  const login = (name = "") => {
    const action = {
      type: types.login,
      payload: {
        id: "ABC",
        name: name,
      },
    };

    dispatch(action);
  };

  return (
    <AuthContext.Provider
      value={{ ...authState, login: login }}
    >
      {children}
    </AuthContext.Provider>
  );
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
import { useContext } from "react";
import { useNavigate } from "react-router-dom";
import { AuthContext } from "../context/AuthContext";

export const LoginPage = () => {
  const { login } = useContext(AuthContext);
  const navigate = useNavigate();

  const handleLogin = () => {
    login("Ghost Devil");

    navigate("/", {
      replace: true,
    });
  };

  return (
    <div className="container mt-5">
      <h1>Login</h1>
      <hr />

      <button onClick={handleLogin}>Login</button>
    </div>
  );
};
```

`src/ui/components/Navbar.jsx`

```jsx
import { useContext } from "react";
import { Link, NavLink, useNavigate } from "react-router";
import { AuthContext } from "../../auth/context/AuthContext";

export const Navbar = () => {
  const { user } = useContext(AuthContext);
  const navigate = useNavigate();

  const handleLogout = () => {
    navigate("/login", {
      replace: true,
    });
  };

  return (
    <nav className="p-3">
      <Link to="/">Asociaciones</Link>

      <div>
        <NavLink to="/marvel">Marvel</NavLink>
        <NavLink to="/dc">DC</NavLink>
        <NavLink to="/search">Search</NavLink>
      </div>

      <div>
        <ul>
          <span>{user?.name}</span>
          <button onClick={handleLogout}>Logout</button>
        </ul>
      </div>
    </nav>
  );
};
```

`src/auth/context/authReducer.js`

```js
import { types } from "../types/types";

// const initialState = {
//   logged: false,
// };

export const authReducer = (state = {}, action) => {
  switch (action.type) {
    case types.login:
      return {
        ...state,
        logged: true,
        user: action.payload,
      };
    case types.logout:
      return {
        logged: false,
      };

    default:
      return state;
  }
};
```

### 15.7 Mantener el usuario activo

La doble negación (`!!`) en JavaScript es un truco para convertir cualquier valor en su equivalente **booleano**.

¿Cómo funciona?

1. La primera negación (`!`) convierte el valor a un booleano y lo invierte.
2. La segunda negación (`!`) invierte el resultado nuevamente, devolviendo el valor booleano original.

Ejemplo:

```javascript
console.log(!!"texto"); // true (porque "texto" es un valor truthy)
console.log(!!0);       // false (porque 0 es un valor falsy)
console.log(!!null);    // false
```

#### ¿Cuándo se usa?

- Para verificar si un valor es **truthy** o **falsy** en lugar de evaluarlo directamente.
- Simplifica expresiones booleanas en código.

En nuestro proyecto:

`src/auth/context/AuthProvider.jsx`

```jsx
import React, { useReducer } from "react";
import { authReducer } from "./authReducer";

import { types } from "../types/types";
import { AuthContext } from "./AuthContext";

// const initialState = {
//   logged: false,
// };

const init = () => {
  const user = JSON.parse(localStorage.getItem("user"));

  return {
    logged: !!user,
    user: user,
  };
};

export const AuthProvider = ({ children }) => {
  const [authState, dispatch] = useReducer(
    authReducer,
    {},
    init
  );

  const login = (name = "") => {
    const user = {
      id: "ABC",
      name,
    };

    const action = {
      type: types.login,
      payload: user,
    };

    localStorage.setItem("user", JSON.stringify(user));

    dispatch(action);
  };

  return (
    <AuthContext.Provider
      value={{ ...authState, login: login }}
    >
      {children}
    </AuthContext.Provider>
  );
};
```

`src/auth/context/authReducer.js`

```js
import { types } from "../types/types";

// const initialState = {
//   logged: false,
// };

export const authReducer = (state = {}, action) => {
  switch (action.type) {
    case types.login:
      return {
        ...state,
        logged: true,
        user: action.payload,
      };
    case types.logout:
      return {
        logged: false,
      };

    default:
      return state;
  }
};
```

### 15.8 Logout del usuario

`src/auth/context/AuthProvider.jsx`

```jsx
import React, { useReducer } from "react";
import { authReducer } from "./authReducer";

import { types } from "../types/types";
import { AuthContext } from "./AuthContext";

// const initialState = {
//   logged: false,
// };

const init = () => {
  const user = JSON.parse(localStorage.getItem("user"));

  return {
    logged: !!user,
    user: user,
  };
};

export const AuthProvider = ({ children }) => {
  const [authState, dispatch] = useReducer(
    authReducer,
    {},
    init
  );

  const login = (name = "") => {
    const user = {
      id: "ABC",
      name,
    };

    const action = {
      type: types.login,
      payload: user,
    };

    localStorage.setItem("user", JSON.stringify(user));

    dispatch(action);
  };

  const logout = () => {
    localStorage.removeItem("user");

    const action = { type: types.logout };

    dispatch(action);
  };

  return (
    <AuthContext.Provider
      value={{
        ...authState,
        // Methods
        login: login,
        logout: logout,
      }}
    >
      {children}
    </AuthContext.Provider>
  );
};
```

`src/ui/components/Navbar.jsx`

```jsx
import { useContext } from "react";
import { Link, NavLink, useNavigate } from "react-router";
import { AuthContext } from "../../auth/context/AuthContext";

export const Navbar = () => {
  const { user, logout } = useContext(AuthContext);
  const navigate = useNavigate();

  const handleLogout = () => {
    logout();

    navigate("/login", {
      replace: true,
    });
  };

  return (
    <nav className="p-3">
      <Link to="/">Asociaciones</Link>

      <div>
        <NavLink to="/marvel">Marvel</NavLink>
        <NavLink to="/dc">DC</NavLink>
        <NavLink to="/search">Search</NavLink>
      </div>

      <div>
        <ul>
          <span>{user?.name}</span>
          <button onClick={handleLogout}>Logout</button>
        </ul>
      </div>
    </nav>
  );
};
```

### 15.9 Rutas privadas

Anteriormente, habíamos trabajado las rutas de la siguiente manera:

`src/router/AppRouter.jsx`

```jsx
import { Route, Routes } from "react-router";

import { LoginPage } from "../auth";
import { HeroesRoutes } from "../heroes";

export const AppRouter = () => {
  return (
    <>
      <Routes> 👈👀👇
        <Route path="login" element={<LoginPage />} />
        <Route path="/*" element={<HeroesRoutes />} />
      </Routes>
    </>
  );
};
```

Pero ahora para trabajar con rutas privadas, lo haremos de la siguiente manera:

`src/router/PrivateRoute.jsx`

```jsx
import { useContext } from "react";
import { AuthContext } from "../auth/context/AuthContext";
import { Navigate } from "react-router-dom";

export const PrivateRoute = ({ children }) => {
  const { logged } = useContext(AuthContext);

  return logged ? children : <Navigate to="/login" />;
};
```

`src/router/AppRouter.jsx`

```jsx
import { Route, Routes } from "react-router";

import { LoginPage } from "../auth";
import { HeroesRoutes } from "../heroes";
import { PrivateRoute } from "./PrivateRoute";

export const AppRouter = () => {
  return (
    <>
      <Routes>
        <Route path="login" element={<LoginPage />} />
        <Route
          path="/*"
          element={
            <PrivateRoute>
              <HeroesRoutes />
            </PrivateRoute>
          }
        />

        {/* <Route path="/*" element={<HeroesRoutes />} /> */}
      </Routes>
    </>
  );
};
```

### 15.10 Rutas públicas

`src/router/PuclicRoute.jsx`

```jsx
import { useContext } from "react";
import { AuthContext } from "../auth/context/AuthContext";
import { Navigate } from "react-router-dom";

export const PublicRoute = ({ children }) => {
  const { logged } = useContext(AuthContext);

  return !logged ? children : <Navigate to="/marvel" />;
};
```

`src/router/AppRouter.jsx`

```jsx
import { Route, Routes } from "react-router";

import { LoginPage } from "../auth";
import { HeroesRoutes } from "../heroes";
import { PrivateRoute } from "./PrivateRoute";
import { PublicRoute } from "./PublicRoute";

export const AppRouter = () => {
  return (
    <>
      <Routes>
        <Route
          path="login/*"
          element={
            <PublicRoute>
              <Routes>
                <Route path="/*" element={<LoginPage />} />
              </Routes>
            </PublicRoute>
          }
        />
        <Route
          path="/*"
          element={
            <PrivateRoute>
              <HeroesRoutes />
            </PrivateRoute>
          }
        />

        {/* <Route path="login" element={<LoginPage />} /> */}
        {/* <Route path="/*" element={<HeroesRoutes />} /> */}
      </Routes>
    </>
  );
};
```

- [Nested Routes and Outlets](https://reactrouter.com/tutorials/address-book#nested-routes-and-outlets)
- [Outlet](https://api.reactrouter.com/v7/functions/react_router.Outlet.html)

### 15.11 Recordar la última página visitada

Esta parte no me funcionó :v

`src/router/PrivateRoute.jsx`

```jsx
import { useContext } from "react";
import { Navigate, useLocation } from "react-router";

import { AuthContext } from "../auth/";

export const PrivateRoute = ({ children }) => {
  const { logged } = useContext(AuthContext);
  const { pathname, search } = useLocation();

  console.log(pathname, search);

  const lastPath = pathname + search;
  localStorage.setItem("lastPath", lastPath);

  console.log("re-render-");

  return logged ? children : <Navigate to="/login" />;
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
import { useContext } from "react";
import { useNavigate } from "react-router";
import { AuthContext } from "../context/AuthContext";

export const LoginPage = () => {
  const { login } = useContext(AuthContext);
  const navigate = useNavigate();

  const handleLogin = () => {
    const lastPath =
      localStorage.getItem("lastPath") || "/";

    login("Ghost");

    navigate(lastPath, {
      replace: true,
    });
  };

  return (
    <div className="container mt-5">
      <h1>Login</h1>
      <hr />

      <button onClick={handleLogin}>Login</button>
    </div>
  );
};
```

`src/ui/components/Navbar.jsx`

```jsx
import { useContext } from "react";
import { Link, NavLink, useNavigate } from "react-router";
import { AuthContext } from "../../auth/context/AuthContext";

export const Navbar = () => {
  const { user, logout } = useContext(AuthContext);
  const navigate = useNavigate();

  const handleLogout = () => {
    logout();

    navigate("/login", {
      replace: true,
    });
  };

  return (
    <nav className="p-3">
      <Link to="/">Asociaciones</Link>

      <div>
        <NavLink to="/marvel">Marvel</NavLink>
        <NavLink to="/dc">DC</NavLink>
        <NavLink to="/search">Search</NavLink>
      </div>

      <div>
        <ul>
          <span>{user?.name}</span>
          <button onClick={handleLogout}>Logout</button>
        </ul>
      </div>
    </nav>
  );
};
```

### 15.12 Código fuente de la sección

Aquí tienen mi código fuente por si lo necesitan comparar contra el suyo:

[**GitHub - Fin sección 15**](https://github.com/Klerith/react-heroes/tree/fin-seccion-15)

## 🟡 16. Pruebas de nuestra aplicación de Heroe

### 16.1 Introducción a la sección

### 16.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Nuevos tipos de pruebas
- Pruebas en rutas privadas y públicas
- MemoryRouter
- Pruebas en nuestro DashboardRouter
- Pruebas en el AppRouter
- Simular URLs y segmentos
- Simular queryParams y queryStrings

Recuerden que el objetivo de las pruebas, es ir probando cosas nuevas cada vez y tener un repertorio completo de diferentes casos.

### 16.3 Inicio de la sección - Pruebas en HeroApp

Configuramos el ambiente de pruebas:

- [8.3 Configurar el ambiente de pruebas](https://github.com/aleroses/Platzi/blob/master/DW/3-avanzado/1.react.js/devTalles/react-hooks-mern.md#83-configurar-el-ambiente-de-pruebas)
- [[react-hooks-mern#🟣 8. Testing - Probando la aplicación de GifExpert#8.3 Configurar el ambiente de pruebas]]

### 16.4 Pruebas en el authReducer

Función a probar:

`src/auth/context/authReducer.js`

```js
import { types } from "../types/types";

// const initialState = {
//   logged: false,
// };

export const authReducer = (state = {}, action) => {
  switch (action.type) {
    case types.login:
      return {
        ...state,
        logged: true,
        user: action.payload,
      };
    case types.logout:
      return {
        logged: false,
      };

    default:
      return state;
  }
};
```

Pruebas:

`test/auth/context/authReducer.test.js`

```js
import { authReducer } from "../../../src/auth/context/authReducer";
import { types } from "../../../src/auth/types/types";

describe("Testing in authReducer", () => {
  test("should return the defaul state", () => {
    const state = authReducer(
      {
        logged: false,
      },
      {}
    );

    expect(state).toEqual({ logged: false });
  });

  test("should call the authenticate login and set the user", () => {
    const action = {
      type: types.login,
      payload: {
        name: "Ale",
        id: "123",
      },
    };

    const state = authReducer({ logged: false }, action);

    expect(state).toEqual({
      logged: true,
      user: action.payload,
    });
  });

  test("should delete the user name (logout) and logged in falsely", () => {
    const action = {
      type: types.logout,
    };

    const state = authReducer(
      {
        logged: true,
        user: action.payload,
      },
      action
    );

    expect(state).toEqual({
      logged: false,
    });
  });
});
```

### 16.5 Pruebas sobre los Types

Objeto a probar:

`src/auth/types/types.js`

```js
export const types = {
  login: "[Auth] Login",
  logout: "[Auth] Logout",
};
```

Pruebas:

`test/auth/types/types.js`

```js
import { types } from "../../../src/auth/types/types";

describe("Testing in types.js", () => {
  test("should return these types:", () => {
    // console.log(types);

    expect(types).toEqual({
      login: "[Auth] Login",
      logout: "[Auth] Logout",
    });
  });
});
```

### 16.6 Pruebas en el PublicRoute

Router a probar:

`src/router/PublicRoute.jsx`

```jsx
import { useContext } from "react";
import { AuthContext } from "../auth/context/AuthContext";
import { Navigate } from "react-router-dom";

export const PublicRoute = ({ children }) => {
  const { logged } = useContext(AuthContext);

  return !logged ? children : <Navigate to="/marvel" />;
};
```

Pruebas:

`test/router/PublicRoute.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { AuthContext } from "../../src/auth/context/AuthContext";
import { PublicRoute } from "../../src/router/PublicRoute";

describe("Testing in PublicRoute", () => {
  test("should be shown to children if it is not authenticated.", () => {
    const contextValue = {
      logged: false,
    };

    render(
      <AuthContext.Provider value={contextValue}>
        <PublicRoute>
          <h1>Public Route</h1>
        </PublicRoute>
      </AuthContext.Provider>
    );

    expect(screen.getByText("Public Route")).toBeTruthy();

    // screen.debug();
  });

  test("Must navigate if you are authenticated", () => {
    // second;
  });
});
```

#### ReferenceError: `TextEncoder` is not defined

Para solucionar el error del título se debe añadir lo siguiente al archivo `jest.setup.js`:

```js
// En caso de necesitar la implementación del FetchAPI
import "whatwg-fetch"; // <-- yarn add whatwg-fetch

// Solución TextEncoder is not defined 👈👀👇
import { TextDecoder, TextEncoder } from "util";
global.TextEncoder = TextEncoder;
global.TextDecoder = TextDecoder;
```

### 16.7 Pruebas en el PublicRoute - Parte 2

`test/router/PublicRoute.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { AuthContext } from "../../src/auth/context/AuthContext";
import { PublicRoute } from "../../src/router/PublicRoute";
import {
  MemoryRouter,
  Route,
  Routes,
} from "react-router-dom";

describe("Testing in PublicRoute", () => {
  test("should be shown to children if it is not authenticated.", () => {
    const contextValue = {
      logged: false,
    };

    render(
      <AuthContext.Provider value={contextValue}>
        <PublicRoute>
          <h1>Public Route</h1>
        </PublicRoute>
      </AuthContext.Provider>
    );

    expect(screen.getByText("Public Route")).toBeTruthy();

    // screen.debug();
  });

  test("Must navigate if you are authenticated", () => {
    const contextValue = {
      logged: true,
      user: {
        name: "Strider",
        id: "ABC123",
      },
    };

    render(
      <AuthContext.Provider value={contextValue}>
        <MemoryRouter initialEntries={["/login"]}>
          <Routes>
            <Route
              path="login"
              element={
                <PublicRoute>
                  <h1>Public Route</h1>
                </PublicRoute>
              }
            />
            <Route
              path="marvel"
              element={<h1>Página marvel</h1>}
            />
          </Routes>
        </MemoryRouter>
      </AuthContext.Provider>
    );

    expect(screen.getByText("Página marvel")).toBeTruthy();
    // screen.debug();
  });
});
```

### 16.8 Pruebas en el PrivateRoute

Código a probar:

`src/router/PrivateRoute.jsx`

```jsx
import { useContext } from "react";
import { Navigate, useLocation } from "react-router";

import { AuthContext } from "../auth/";

export const PrivateRoute = ({ children }) => {
  const { logged } = useContext(AuthContext);
  const { pathname, search } = useLocation();

  // console.log(pathname, search);

  const lastPath = pathname + search;
  localStorage.setItem("lastPath", lastPath);

  // console.log("re-render-");

  return logged ? children : <Navigate to="/login" />;
};
```

Prueba:

`test/router/PrivateRoute.test.jsx`

```jsx
import { screen } from "@testing-library/dom";
import { AuthContext } from "../../src/auth/context/AuthContext";
import { PrivateRoute } from "../../src/router/PrivateRoute";
import { render } from "@testing-library/react";
import { MemoryRouter } from "react-router-dom";

describe("Testing in PrivateRoute", () => {
  test("should be shown to children if it is authenticated.", () => {
    Storage.prototype.setItem = jest.fn();

    const contextValue = {
      logged: true,
      user: {
        id: "abc",
        name: "Ale Ghost",
      },
    };

    render(
      <AuthContext.Provider value={contextValue}>
        <MemoryRouter initialEntries={["/search?q=batman"]}>
          <PrivateRoute>
            <h1>Private Route</h1>
          </PrivateRoute>
        </MemoryRouter>
      </AuthContext.Provider>
    );

    expect(screen.getByText("Private Route")).toBeTruthy();
    expect(localStorage.setItem).toHaveBeenCalledWith(
      "lastPath",
      "/search?q=batman"
    );

    // screen.debug();
  });
});
```

### 16.9 Pruebas en el AppRouter

Código a probar:

`src/router/AppRouter.jsx`

```jsx
import { Route, Routes } from "react-router";

import { LoginPage } from "../auth";
import { HeroesRoutes } from "../heroes";
import { PrivateRoute } from "./PrivateRoute";
import { PublicRoute } from "./PublicRoute";

export const AppRouter = () => {
  return (
    <>
      <Routes>
        <Route
          path="login/*"
          element={
            <PublicRoute>
              <Routes>
                <Route path="/*" element={<LoginPage />} />
              </Routes>
            </PublicRoute>
          }
        />
        <Route
          path="/*"
          element={
            <PrivateRoute>
              <HeroesRoutes />
            </PrivateRoute>
          }
        />
      </Routes>
    </>
  );
};
```

Prueba:

`test/router/AppRouter.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { AuthContext } from "../../src/auth";
import { MemoryRouter } from "react-router-dom";
import { AppRouter } from "../../src/router/AppRouter";

describe("Testing in AppRouter", () => {
  test("should display login if not authenticated", () => {
    const contextValue = {
      logged: false,
    };

    render(
      <MemoryRouter initialEntries={["/marvel"]}>
        <AuthContext.Provider value={contextValue}>
          <AppRouter />
        </AuthContext.Provider>
      </MemoryRouter>
    );

    // screen.debug();
    expect(screen.getAllByText("Login").length).toBe(2);
  });

  test("should display the marvel component if authenticated", () => {
    const contextValue = {
      logged: true,
      user: {
        id: "ABC",
        name: "Ale Ghost",
      },
    };

    render(
      <MemoryRouter initialEntries={["/login"]}>
        <AuthContext.Provider value={contextValue}>
          <AppRouter />
        </AuthContext.Provider>
      </MemoryRouter>
    );

    // screen.debug();
    expect(
      screen.getAllByText("Marvel").length
    ).toBeGreaterThanOrEqual(1);
  });
});
```

### ☣️ Errores...

Para estas pruebas tuve errores relacionados con `import queryString from "query-string";` en `SearchPage.jsx` y luego con `import { useNavigate } from "react-router";` en `LoginPage.jsx`. 

Se solucionan con:

`07-heroes-spa/jest.config.cjs`

```jsx
module.exports = {
  testEnvironment: "jest-environment-jsdom",
  setupFiles: ["./jest.setup.js"],
  transformIgnorePatterns: [ 👈👀👇
    "node_modules/(?!(query-string|decode-uri-component|split-on-first|filter-obj)/)",
  ],
};
```

Igualmente revisa esto:

`07-heroes-spa/jest.setup.js`

```js
// En caso de necesitar la implementación del FetchAPI
import "whatwg-fetch"; // <-- yarn add whatwg-fetch

// Solución TextEncoder is not defined 👈👀👇
import { TextDecoder, TextEncoder } from "util";
global.TextEncoder = TextEncoder;
global.TextDecoder = TextDecoder;
```

### 16.10 Pruebas en el NavBar

Componente a probar:

`src/ui/components/Navbar.jsx`

```jsx
import { useContext } from "react";
import { Link, NavLink, useNavigate } from "react-router";
import { AuthContext } from "../../auth/context/AuthContext";

export const Navbar = () => {
  const { user, logout } = useContext(AuthContext);
  const navigate = useNavigate();

  const handleLogout = () => {
    logout();

    navigate("/login", {
      replace: true,
    });
  };

  return (
    <nav className="p-3">
      <Link to="/">Asociaciones</Link>

      <div>
        <NavLink to="/marvel">Marvel</NavLink>
        <NavLink to="/dc">DC</NavLink>
        <NavLink to="/search">Search</NavLink>
      </div>

      <div>
        <ul>
          <span>{user?.name}</span>
          <button onClick={handleLogout}>Logout</button>
        </ul>
      </div>
    </nav>
  );
};
```

Pruebas a realizar:

`test/ui/components/Navbar.test.jsx`

```jsx
describe("testing in Navbar", () => {
  test("should display the user name", () => {
    // second;
  });

  test("should call the output and navigate when the buttom is clicked.", () => {
    // second;
  });
});
```

### 16.11 Solución de la tarea

Pruebas a realizar:

`test/ui/components/Navbar.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { AuthContext } from "../../../src/auth/context/AuthContext";
import { Navbar } from "../../../src/ui/components/Navbar";
import { MemoryRouter } from "react-router";

const mockedUseNavigate = jest.fn();

jest.mock("react-router", () => ({
  ...jest.requireActual("react-router"),
  useNavigate: () => mockedUseNavigate,
}));

describe("testing in Navbar", () => {
  const contextValue = {
    logged: true,
    user: {
      name: "Ale Ghost",
    },
    logout: jest.fn(),
  };

  beforeEach(() => jest.clearAllMocks());

  test("should display the user name", () => {
    render(
      <AuthContext.Provider value={contextValue}>
        <MemoryRouter>
          <Navbar />
        </MemoryRouter>
      </AuthContext.Provider>
    );

    // screen.debug()
    expect(screen.getByText("Ale Ghost")).toBeTruthy();
  });

  test("should call the output and navigate when the buttom is clicked.", () => {
    render(
      <AuthContext.Provider value={contextValue}>
        <MemoryRouter>
          <Navbar />
        </MemoryRouter>
      </AuthContext.Provider>
    );

    const logoutBtn = screen.getByRole("button");
    fireEvent.click(logoutBtn);

    expect(contextValue.logout).toHaveBeenCalled();
    expect(mockedUseNavigate).toHaveBeenCalledWith(
      "/login",
      { replace: true }
    );
  });
});
```

### 16.12 Pruebas en el SearchScreen

Código a probar:

`src/heroes/pages/SearchPage.jsx`

```jsx
import { useLocation, useNavigate } from "react-router";
import queryString from "query-string";

import { useForm } from "../hooks/useForm";
import { HeroCard } from "../components";
import { getHeroByName } from "../helpers";

export const SearchPage = () => {
  const navigate = useNavigate();
  const location = useLocation();

  const { q } = queryString.parse(location?.search);
  console.log(q, location.search);

  const heroes = getHeroByName(q);

  const showSearch = q?.length === 0;
  const showError = q?.length > 0 && heroes?.length === 0;

  const { searchText, handleInputChange } = useForm({
    searchText: q || "", // ""
  });

  console.log(q);

  const handleSearchSubmit = (event) => {
    event.preventDefault();

    // if (searchText.trim().length <= 1) return;

    navigate(`?q=${searchText}`);
  };

  return (
    <>
      <h1>Search</h1>
      <hr />

      <div>
        <h4>Searching</h4>
        <hr />
        <form action="" onSubmit={handleSearchSubmit}>
          <input
            type="text"
            autoComplete="off"
            placeholder="Search a hero"
            name="searchText"
            value={searchText}
            onChange={(e) => handleInputChange(e)}
          />
          <button>Search</button>
        </form>
      </div>

      <div>
        <h4>Results</h4>
        <hr />

        {/* First method */}
        {/* {q === "" ? (
          <div>Search a Hero</div>
        ) : (
          heroes.length === 0 && (
            <div>
              There's no results <b>{q}</b>
            </div>
          )
        )} */}

        {/* Second method */}
        <div style={{ display: showSearch ? "" : "none" }}>
          Search a Hero
        </div>
        <div style={{ display: showError ? "" : "none" }}>
          There's no results <b>{q}</b>
        </div>

        {heroes.map((hero) => (
          <HeroCard key={hero.id} {...hero} />
        ))}
      </div>
    </>
  );
};
```

Primera prueba:

`test/heroes/pages/SearchPage.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { SearchPage } from "../../../src/heroes/pages/SearchPage";
import { MemoryRouter } from "react-router-dom";

describe("Testing SearchPage", () => {
  test("should display correctly with the default values", () => {
    const { container } = render(
      <MemoryRouter>
        <SearchPage></SearchPage>
      </MemoryRouter>
    );

    // screen.debug()
    expect(container).toMatchSnapshot();
  });
});
```

### 16.13 Pruebas con los queryParameters

Código a probar:

`src/heroes/pages/SearchPage.jsx`

```jsx
import { useLocation, useNavigate } from "react-router";
import queryString from "query-string";

import { useForm } from "../hooks/useForm";
import { HeroCard } from "../components";
import { getHeroByName } from "../helpers";

export const SearchPage = () => {
  const navigate = useNavigate();
  const location = useLocation();

  const { q } = queryString.parse(location?.search);
  // console.log(q, location.search);

  const heroes = getHeroByName(q);

  const showSearch = q?.length === 0;
  const showError = q?.length > 0 && heroes?.length === 0;

  const { searchText, handleInputChange } = useForm({
    searchText: q || "", // ""
  });

  // console.log(q);

  const handleSearchSubmit = (event) => {
    event.preventDefault();

    // if (searchText.trim().length <= 1) return;

    navigate(`?q=${searchText}`);
  };

  return (
    <>
      <h1>Search</h1>
      <hr />

      <div>
        <h4>Searching</h4>
        <hr />
        <form action="" onSubmit={handleSearchSubmit}>
          <input
            type="text"
            autoComplete="off"
            placeholder="Search a hero"
            name="searchText"
            value={searchText}
            onChange={(e) => handleInputChange(e)}
          />
          <button>Search</button>
        </form>
      </div>

      <div>
        <h4>Results</h4>
        <hr />

        {/* Second method */}
        <div style={{ display: showSearch ? "" : "none" }}>
          Search a Hero
        </div>
        <div 👈👀👇
          aria-label="alert-danger"
          style={{ display: showError ? "" : "none" }}
        >
          There's no results <b>{q}</b>
        </div>

        {heroes.map((hero) => (
          <HeroCard key={hero.id} {...hero} />
        ))}
      </div>
    </>
  );
};
```

Segunda prueba:

`test/heroes/pages/SearchPage.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { SearchPage } from "../../../src/heroes/pages/SearchPage";
import { MemoryRouter } from "react-router-dom";

describe("Testing SearchPage", () => {
  test("should display correctly with the default values", () => {
    const { container } = render(
      <MemoryRouter>
        <SearchPage></SearchPage>
      </MemoryRouter>
    );

    // screen.debug()
    expect(container).toMatchSnapshot();
  });

  test("should display a Batman and the input with the value of the queryString", () => {
    render(
      <MemoryRouter initialEntries={["/search?q=batman"]}>
        <SearchPage />
      </MemoryRouter>
    );

    const input = screen.getByRole("textbox");
    expect(input.value).toBe("batman");
    // screen.debug();

    const img = screen.getByRole("img");
    expect(img.src).toContain(
      "/assets/heroes/dc-batman.jpg"
    );

    // u update
    const alert = screen.getByLabelText("alert-danger");
    // console.log(alert.style);

    expect(alert.style.display).toBe("none");
  });
});
```

### 16.14 Tarea - requireActual

Código a probar:

`src/heroes/pages/SearchPage.jsx`

```jsx
import { useLocation, useNavigate } from "react-router";
import queryString from "query-string";

import { useForm } from "../hooks/useForm";
import { HeroCard } from "../components";
import { getHeroByName } from "../helpers";

export const SearchPage = () => {
  const navigate = useNavigate();
  const location = useLocation();

  const { q } = queryString.parse(location?.search);
  // console.log(q, location.search);

  const heroes = getHeroByName(q);

  const showSearch = q?.length === 0;
  const showError = q?.length > 0 && heroes?.length === 0;

  const { searchText, handleInputChange } = useForm({
    searchText: q || "", // ""
  });

  // console.log(q);

  const handleSearchSubmit = (event) => {
    event.preventDefault();

    // if (searchText.trim().length <= 1) return;

    // console.log("From testing... FORM"); 👈👀

    navigate(`?q=${searchText}`);
  };

  return (
    <>
      <h1>Search</h1>
      <hr />

      <div>
        <h4>Searching</h4>
        <hr />
        <form
          aria-label="form"
          action=""
          onSubmit={handleSearchSubmit}
        >
          <input
            type="text"
            autoComplete="off"
            placeholder="Search a hero"
            name="searchText"
            value={searchText}
            onChange={(e) => handleInputChange(e)}
          />
          <button>Search</button>
        </form>
      </div>

      <div>
        <h4>Results</h4>
        <hr />

        {/* Second method */}
        <div style={{ display: showSearch ? "" : "none" }}>
          Search a Hero
        </div>
        <div
          aria-label="alert-danger"
          style={{ display: showError ? "" : "none" }}
        >
          There's no results <b>{q}</b>
        </div>

        {heroes.map((hero) => (
          <HeroCard key={hero.id} {...hero} />
        ))}
      </div>
    </>
  );
};
```

Tercera prueba:

`test/heroes/pages/SearchPage.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { MemoryRouter } from "react-router";

import { SearchPage } from "../../../src/heroes/pages/SearchPage";

const mockedUseNavigate = jest.fn();

jest.mock("react-router", () => ({
  ...jest.requireActual("react-router"),
  useNavigate: () => mockedUseNavigate,
}));

describe("Testing SearchPage", () => {
  beforeEach(() => jest.clearAllMocks());

  test("should display correctly with the default values", () => {
    const { container } = render(
      <MemoryRouter>
        <SearchPage></SearchPage>
      </MemoryRouter>
    );

    // screen.debug()
    expect(container).toMatchSnapshot();
  });

  test("should display a Batman and the input with the value of the queryString", () => {
    render(
      <MemoryRouter initialEntries={["/search?q=batman"]}>
        <SearchPage />
      </MemoryRouter>
    );

    const input = screen.getByRole("textbox");
    expect(input.value).toBe("batman");
    // screen.debug();

    const img = screen.getByRole("img");
    expect(img.src).toContain(
      "/assets/heroes/dc-batman.jpg"
    );

    // u update
    const alert = screen.getByLabelText("alert-danger");
    // console.log(alert.style);

    expect(alert.style.display).toBe("none");
  });

  test("should display an error if it does not find the hero (batman123).", () => {
    render(
      <MemoryRouter
        initialEntries={["/search?q=batman123"]}
      >
        <SearchPage />
      </MemoryRouter>
    );

    const alert = screen.getByLabelText("alert-danger");
    expect(alert.style.display).toBe("");
  });

  test("you must call the navegate to the new screen", () => {
    const inputValue = "superman";

    render(
      <MemoryRouter initialEntries={["/search"]}>
        <SearchPage />
      </MemoryRouter>
    );

    const input = screen.getByRole("textbox");
    fireEvent.change(input, {
      target: { name: "searchText", value: inputValue },
    });

    const form = screen.getByRole("form");
    fireEvent.submit(form);
    // console.log(input.value);

    expect(mockedUseNavigate).toHaveBeenCalledWith(
      `?q=${inputValue}`
    );
  });
});
```

### 16.15 Resumen de las pruebas realizadas

### 16.16 Código fuente de la sección

Aquí les dejo mi código fuente para que lo puedan evaluar contra el suyo. O bien tenerlo como parte de su repertorio de pruebas y aplicaciones hechas en React

[**GitHub - Fin sección 16**](https://github.com/Klerith/react-heroes/tree/fin-seccion-16)

---

## 🟣 17. JournalApp - MaterialUI - Estructura y Diseño

### 17.1 Introducción a la sección

### 17.2 Temas puntuales de la sección

¿Qué veremos en esta sección?

- Material UI
- Diferentes componentes de material
- Uso de funciones propias de MaterialUI
- Configuración de temas personalizados

### 17.3 Demostración del objetivo final de la sección

### 17.4 Inicio de proyecto - JournalApp

```bash
yarn create vite
# 08-journal-app
cd 08-journal-app
yarn
```

Dejamos la siguiente estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── auth
│   ├── journal
│   ├── JournalApp.jsx
│   ├── main.jsx
│   ├── router
│   ├── styles.css
│   └── theme
├── vite.config.js
└── yarn.lock
```

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { JournalApp } from "./JournalApp";

import "./styles.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <JournalApp />
  </StrictMode>
);
```

`src/JournalApp.jsx`

```jsx
export const JournalApp = () => {
  return (
    <>
      <h1>Hi world</h1>
    </>
  );
};
```

### 17.5 Configuración de Rutas principales y secundarias

Instalamos React router.

```bash
# Instalar React Router
yarn add react-router-dom 👈👀
yarn add react-router-dom@7.1.1
```

Estructura:

```bash
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── auth
│   │   ├── layout
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── journal
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   └── routes
│   │       └── JournalRoutes.jsx
│   ├── JournalApp.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── theme
├── vite.config.js
└── yarn.lock
```

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { BrowserRouter } from "react-router-dom";

import { JournalApp } from "./JournalApp";

import "./styles.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <BrowserRouter>
      <JournalApp />
    </BrowserRouter>
  </StrictMode>
);
```

`src/JournalApp.jsx`

```jsx
import { AppRouter } from "./router/AppRouter";

export const JournalApp = () => {
  return (
    <>
      <AppRouter />
    </>
  );
};
```

`src/router/AppRouter.jsx`

```jsx
import { Route, Routes } from "react-router";

import { AuthRoutes } from "../auth/routes/AuthRoutes";
import { JournalRoutes } from "../journal/routes/JournalRoutes";

export const AppRouter = () => {
  return (
    <Routes>
      {/* Login and Registration */}
      <Route path="/auth/*" element={<AuthRoutes />} />

      {/* JournalApp */}
      <Route path="/*" element={<JournalRoutes />} />
    </Routes>
  );
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
export const LoginPage = () => {
  return <div>LoginPage</div>;
};
```

`src/auth/pages/RegisterPage.jsx`

```jsx
export const RegisterPage = () => {
  return <div>RegisterPage</div>;
};
```

`src/auth/routes/AuthRoutes.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { LoginPage } from "../pages/LoginPage";
import { RegisterPage } from "../pages/RegisterPage";

export const AuthRoutes = () => {
  return (
    <Routes>
      <Route path="login" element={<LoginPage />} />
      <Route path="register" element={<RegisterPage />} />

      <Route
        path="/*"
        element={<Navigate to="/auth/login" />}
      />
    </Routes>
  );
};
```

`src/journal/pages/JournalPage.jsx`

```jsx
export const JournalPage = () => {
  return <div>JournalPage</div>;
};
```

`src/journal/routes/JournalRoutes.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router-dom";
import { JournalPage } from "../pages/JournalPage";

export const JournalRoutes = () => {
  return (
    <Routes>
      <Route path="/" element={<JournalPage />} />
      <Route path="/*" element={<Navigate to="/" />} />
    </Routes>
  );
};
```

Puedes hacer búsquedas como las siguientes:

```
http://localhost:5173/auth/register

/auth/register
/auth/login
```

[[react-hooks-mern#11.4 Preparación de nuestra aplicación con rutas]]

### 17.6 Nota importante

**Importante:**

En la próxima clase instalaremos los iconos de material, pero al hacerlo, esto incrementa el bundle size y el tiempo de transpilación, tengan presente esto porque hemos recibido bastantes preguntas relacionadas con el tema.
  
Más información y posibles acciones aquí:

[**mui.com - minimizing-bundle-size**](https://mui.com/material-ui/guides/minimizing-bundle-size/#development-environment\).)

### 17.7 Instalación de Material UI

Recuerda que este paquete depende de `react` y `react-dom`, por lo que deben estar instalados si o si para usarlo.

```bash
yarn add @mui/material @emotion/react @emotion/styled
```

#### Roboto font: Google Web Fonts

Pegar esto en el `index.html`:

```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap"
/>

<title>Journal App</title>
```

#### Icons

```bash
yarn add @mui/icons-material
```

- [Instalación Material UI](https://mui.com/material-ui/getting-started/installation/)
- [Uso Material UI](https://mui.com/material-ui/getting-started/usage/)
- [Example Projects](https://mui.com/material-ui/getting-started/example-projects/)
- [GitHub Material UI vite](https://github.com/mui/material-ui/tree/v6.x/examples/material-ui-vite)
- [Stackblitz](https://stackblitz.com/github/mui/material-ui/tree/v6.x/examples/material-ui-vite?file=README.md)

### 17.8 Configuración de MUI con Vite

Estructura actual:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── auth
│   │   ├── layout
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── journal
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   └── routes
│   │       └── JournalRoutes.jsx
│   ├── JournalApp.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── theme 👈👀👇
│       ├── AppTheme.jsx
│       └── theme.js
├── vite.config.js
└── yarn.lock
```

Si hiciste la instalación de Fuentes por comando puedes hacer lo siguiente para que funcione.

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { BrowserRouter } from "react-router-dom";
import { App } from "./App.jsx";

import "./styles.css";
import "@fontsource/roboto/300.css";
import "@fontsource/roboto/400.css";
import "@fontsource/roboto/500.css";
import "@fontsource/roboto/700.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <BrowserRouter>
      <JournalApp />
    </BrowserRouter>
  </StrictMode>
);
```

`src/theme/AppTheme.jsx`

```jsx
import { ThemeProvider } from "@emotion/react";
import { CssBaseline } from "@mui/material";
import { theme } from "./theme";

export const AppTheme = ({ children }) => {
  return (
    <ThemeProvider theme={theme}>
      <CssBaseline />
      {children}
    </ThemeProvider>
  );
};
```

`src/theme/theme.js`

```js
import { createTheme } from "@mui/material/styles";
import { red } from "@mui/material/colors";

export const theme = createTheme({
  palette: {
    primary: {
      main: "#262254",
    },
    secondary: {
      main: "#543884",
    },
    error: {
      main: red.A400,
    },
  },
});
```

`src/JournalApp.jsx`

```jsx
import { AppRouter } from "./router/AppRouter";
import { AppTheme } from "./theme/AppTheme";

export const JournalApp = () => {
  return (
    <AppTheme>
      <AppRouter />
    </AppTheme>
  );
};
```

`src/journal/pages/JournalPage.jsx`

```jsx
import { Typography } from "@mui/material";
import { MailOutline } from "@mui/icons-material";

export const JournalPage = () => {
  return (
    <>
      <Typography variant="h1" /* component={"h1"} */>
        JournalPage
        <MailOutline />
      </Typography>
    </>
  );
};
```

### 17.9 LoginPage - Diseño sin Layout

Entramos a la siguiente ruta para ver los cambios:

`http://localhost:5173/auth/login`

`src/styles.css`

```jsx
.box-shadow {
  box-shadow: 0px 5px 5px rgba(0, 0, 0, 0.2);
}
```

`src/auth/pages/LoginPage.jsx`

```jsx
import {
  Box,
  Typography,
  TextField,
} from "@mui/material";

export const LoginPage = () => {
  return (
    <Box
      component="main"
      sx={{
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        minHeight: "100vh",
        bgcolor: "primary.main",
        // padding: 4,
      }}
    >
      <Box
        component="section"
        className="box-shadow"
        sx={{
          width: {
            xs: "70%",
            sm: "60%",
            md: "40%",
            lg: "30%",
          }, // Ancho responsivo
          bgcolor: "white",
          padding: { xs: 2, sm: 3, md: 4 }, // Padding responsivo
          borderRadius: 2,
        }}
      >
        <Typography
          variant="h5"
          sx={{ mb: 2, textAlign: "center" }}
        >
          Login
        </Typography>
        <Box
          component="form"
          sx={{
            display: "flex",
            flexDirection: { xs: "column", md: "row" }, // Column en móvil, fila en grande
            gap: 2, // Espaciado entre los campos
          }}
        >
          <TextField
            id="email"
            label="Email"
            type="email"
            placeholder="email@google.com"
            size="small"
            // fullWidth
            // sx={{ flex: 1 }} // Que ambos ocupen el mismo espacio en filas grandes
          />
          <TextField
            id="password"
            label="Password"
            type="password"
            placeholder="password"
            size="small"
            // fullWidth
            // sx={{ flex: 1 }} // Igual ancho que el otro
          />
        </Box>
      </Box>
    </Box>
  );
};
```

Otra forma, usando `Grid2`

```jsx
import {
  Box,
  Typography,
  TextField,
  Grid2,
} from "@mui/material";

export const LoginPage = () => {
  return (
    <Box
      component="main"
      sx={{
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        minHeight: "100vh",
        bgcolor: "primary.main",
        // padding: 4,
      }}
    >
      <Box
        component="section"
        sx={{
          width: {
            xs: "80%",
            sm: "60%",
            md: "40%",
            lg: "30%",
          },
          bgcolor: "white",
          padding: { xs: 2, sm: 3, md: 4 },
          borderRadius: 2,
        }}
      >
        <Typography
          variant="h5"
          sx={{ mb: 2, textAlign: "center" }}
        >
          Login
        </Typography>
        <Grid2 container component="form" spacing={2}>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
            />
          </Grid2>
        </Grid2>
      </Box>
    </Box>
  );
};
```

📌 Nota: Grid2 cambió a Grid.

[Grid MUI](https://mui.com/material-ui/react-grid/)

### 17.10 LoginPage - Diseño - Segunda Parte

`src/auth/pages/LoginPage.jsx`

```jsx
import {
  Box,
  Typography,
  TextField,
  Grid2,
  Button,
  Link,
} from "@mui/material";
import { Link as RouterLink } from "react-router";
import { Google } from "@mui/icons-material";

export const LoginPage = () => {
  return (
    <Box
      component="main"
      sx={{
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        minHeight: "100vh",
        bgcolor: "primary.main",
        // padding: 4,
      }}
    >
      <Box
        component="section"
        sx={{
          width: {
            xs: "80%",
            sm: "60%",
            md: "40%",
            lg: "30%",
          },
          bgcolor: "white",
          padding: { xs: 2, sm: 3, md: 4 },
          borderRadius: 2,
        }}
      >
        <Typography
          variant="h5"
          sx={{ mb: 2, textAlign: "center" }}
        >
          Login
        </Typography>
        <Grid2 container component="form" spacing={2}>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
            />
          </Grid2>
        </Grid2>

        {/* New */} 👈👀👇
        <Grid2 container spacing={2} sx={{ mt: 2 }}>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <Button variant="contained" fullWidth>
              Login
            </Button>
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <Button
              variant="contained"
              fullWidth
              startIcon={<Google />}
            >
              Google
            </Button>
          </Grid2>
        </Grid2>
        <Grid2
          container
          // direction="row"
          justifyContent="end"
          sx={{ mt: 2 }}
        >
          <Link
            component={RouterLink}
            color="inherit"
            to="/auth/register"
          >
            Create an account.
          </Link>
        </Grid2>
      </Box>
    </Box>
  );
};
```

### 17.11 AuthLayout

`src/auth/layout/AuthLayout.jsx`

```jsx
import { Box, Typography } from "@mui/material";

export const AuthLayout = ({ children, title = "" }) => {
  return (
    <Box
      component="main"
      sx={{
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        minHeight: "100vh",
        bgcolor: "primary.main",
        // padding: 4,
      }}
    >
      <Box
        component="section"
        sx={{
          width: {
            xs: "80%",
            sm: "60%",
            md: "40%",
            lg: "30%",
          },
          bgcolor: "white",
          padding: { xs: 2, sm: 3, md: 4 },
          borderRadius: 2,
        }}
      >
        <Typography
          variant="h5"
          sx={{ mb: 2, textAlign: "center" }}
        >
          {title}
        </Typography>

        {/* Children */}
        {children}
      </Box>
    </Box>
  );
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
import {
  TextField,
  Grid2,
  Button,
  Link,
} from "@mui/material";
import { Link as RouterLink } from "react-router";
import { Google } from "@mui/icons-material";
import { AuthLayout } from "../layout/AuthLayout";

export const LoginPage = () => {
  return (
    <AuthLayout title="Login"> 👈👀👇
      <Grid2 container component="form" spacing={2}>
        <Grid2 size={{ xs: 12, md: 6 }}>
          <TextField
            id="email"
            label="Email"
            type="email"
            placeholder="email@google.com"
            size="small"
            fullWidth
          />
        </Grid2>
        <Grid2 size={{ xs: 12, md: 6 }}>
          <TextField
            id="password"
            label="Password"
            type="password"
            placeholder="password"
            size="small"
            fullWidth
          />
        </Grid2>
      </Grid2>

      {/* New */}
      <Grid2 container spacing={2} sx={{ mt: 2 }}>
        <Grid2 size={{ xs: 12, md: 6 }}>
          <Button variant="contained" fullWidth>
            Login
          </Button>
        </Grid2>
        <Grid2 size={{ xs: 12, md: 6 }}>
          <Button
            variant="contained"
            fullWidth
            startIcon={<Google />}
          >
            Google
          </Button>
        </Grid2>
      </Grid2>
      <Grid2
        container
        // direction="row"
        justifyContent="end"
        sx={{ mt: 2 }}
      >
        <Link
          component={RouterLink}
          color="inherit"
          to="/auth/register"
        >
          Create an account.
        </Link>
      </Grid2>
    </AuthLayout>
  );
};
```

### 17.12 RegisterPage - Diseño

`src/auth/pages/RegisterPage.jsx`

```jsx
import {
  Button,
  Grid2,
  TextField,
  Link,
  Typography,
} from "@mui/material";
import { AuthLayout } from "../layout/AuthLayout";
import { Link as RouterLink } from "react-router";

export const RegisterPage = () => {
  return (
    <AuthLayout title="Register">
      <Grid2 container component="form" spacing={2}>
        <Grid2 size={{ xs: 12, md: 6 }}>
          <TextField
            id="fullname"
            label="Full name"
            type="text"
            placeholder="Your full name"
            size="small"
            fullWidth
          />
        </Grid2>
        <Grid2 size={{ xs: 12, md: 6 }}>
          <TextField
            id="email"
            label="Email"
            type="email"
            placeholder="email@google.com"
            size="small"
            fullWidth
          />
        </Grid2>
        <Grid2 size={{ xs: 12, md: 6 }}>
          <TextField
            id="password"
            label="Password"
            type="password"
            placeholder="password"
            size="small"
            fullWidth
          />
        </Grid2>
      </Grid2>

      {/* New */}
      <Grid2 container spacing={2} sx={{ mt: 2 }}>
        <Grid2 size={{ xs: 12 }}>
          <Button variant="contained" fullWidth>
            Create account
          </Button>
        </Grid2>
      </Grid2>
      <Grid2
        container
        justifyContent="end"
        sx={{ mt: 2 }}
      >
        <Typography sx={{ mr: 1 }}>
          Already have an account?
        </Typography>
        <Link
          component={RouterLink}
          color="inherit"
          to="/auth/login"
        >
          Login
        </Link>
      </Grid2>
    </AuthLayout>
  );
};
```

### 17.13 JournalLayout y JournalPage

Estructura actual:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── journal
│   │   ├── layout 👈👀👇
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   └── routes
│   │       └── JournalRoutes.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/journal/pages/JournalPage.jsx`

```jsx
import { Typography } from "@mui/material";
import { JournalLayout } from "../layout/JournalLayout";

export const JournalPage = () => {
  return (
    <JournalLayout>
      <Typography>
        Lorem ipsum dolor, sit amet consectetur
        adipisicing elit. Labore ipsa saepe id similique?
        Illo reiciendis sunt a esse repellat. Accusantium
        quasi, consequatur cumque natus mollitia maiores
        voluptatum provident nobis fugiat.
      </Typography>

      {/* Nothing Selected */}
    </JournalLayout>
  );
};
```

`src/journal/layout/JournalLayout.jsx`

```jsx
import { Box } from "@mui/material";

const drawerWidth = 240;

export const JournalLayout = ({ children }) => {
  return (
    <Box sx={{ display: "flex" }}>
      {/* Navbar drawerWidth */}

      {/* Sidebar drawerWidth */}

      <Box component="main" sx={{ flexGrow: 1, p: 3 }}>
        {/* Toolbar */}

        {children}
      </Box>
    </Box>
  );
};
```

### 17.14 NavBar

Estructura actual:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── journal 👈👀👇
│   │   ├── components
│   │   │   └── NavBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   └── routes
│   │       └── JournalRoutes.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/journal/components/NavBar.jsx`

```jsx
import {
  LogoutOutlined,
  MenuOutlined,
} from "@mui/icons-material";
import {
  AppBar,
  Toolbar,
  IconButton,
  Grid2,
  Typography,
  Drawer,
} from "@mui/material";
import { useState } from "react";

export const NavBar = ({ drawerWidth = 240 }) => {
  const [open, setOpen] = useState(false);

  return (
    <>
      <AppBar
        // position="static"
        sx={{
          width: { sm: `calc(100% - ${drawerWidth}px)` },
          ml: { sm: `${drawerWidth}px` },
        }}
      >
        <Toolbar>
          <IconButton
            aria-label=""
            onClick={() => setOpen(true)}
            color="inherit"
            edge="start"
            sx={{
              display: { xs: "flex", sm: "none" },
              mr: 2,
            }}
          >
            <MenuOutlined />
          </IconButton>

          <Typography
            variant="h6"
            // noWrap
            component="span"
            sx={{ flexGrow: 1 }}
          >
            JournalApp
          </Typography>

          <IconButton aria-label="" color="error">
            <LogoutOutlined />
          </IconButton>
        </Toolbar>
      </AppBar>

      <Drawer
        anchor="left"
        open={open}
        onClose={() => setOpen(false)}
        sx={{ display: { xs: "flex", sm: "none" } }}
      >
        <Typography variant="h6" color="initial">
          Lolcat
        </Typography>
      </Drawer>
    </>
  );
};
```

`src/journal/layout/JournalLayout.jsx`

```jsx
import { Box } from "@mui/material";
import { NavBar } from "../components/NavBar";

const drawerWidth = 240;

export const JournalLayout = ({ children }) => {
  return (
    <Box sx={{ display: "flex" }}>
      {/* Navbar drawerWidth */}
      <NavBar drawerWidth={drawerWidth} />

      {/* Sidebar drawerWidth */}

      <Box component="main" sx={{ flexGrow: 1, p: 3 }}>
        {/* Toolbar */}

        {children}
      </Box>
    </Box>
  );
};
```

### 17.15 SideBar

Estructura actual:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── journal
│   │   ├── components
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx 👈👀
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   └── routes
│   │       └── JournalRoutes.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/journal/components/SideBar.jsx`

```jsx
import { TurnedInNot } from "@mui/icons-material";
import {
  Box,
  Drawer,
  Typography,
  Toolbar,
  Divider,
  List,
  ListItem,
  ListItemIcon,
  ListItemButton,
  ListItemText,
  Grid2,
} from "@mui/material";

export const SideBar = ({ drawerWidth = 240 }) => {
  return (
    <Drawer
      variant="permanent"
      anchor="left"
      open
      sx={{
        width: { sm: drawerWidth },
        flexShrink: { sm: 0 },
        display: { xs: "block" },
        "& .MuiDrawer-paper": {
          boxSizing: "border-box",
          width: drawerWidth,
        },
      }}
    >
      <Toolbar>
        <Typography variant="h6" noWrap component="div">
          Ghost...
        </Typography>
      </Toolbar>
      <Divider />

      <Box component="nav">
        <List>
          {["January", "February", "March", "April"].map(
            (text) => (
              <ListItem key={text} disablePadding>
                <ListItemButton component="a">
                  <ListItemIcon>
                    <TurnedInNot />
                  </ListItemIcon>
                  <Grid2 container>
                    <ListItemText
                      // primary={text}
                      secondary={"Lorem ipsum......"}
                    >
                      {text}
                    </ListItemText>
                  </Grid2>
                </ListItemButton>
              </ListItem>
            )
          )}
        </List>
      </Box>
    </Drawer>
  );
};
```

`src/journal/components/NavBar.jsx`

```jsx
import {
  LogoutOutlined,
  MenuOutlined,
} from "@mui/icons-material";
import {
  AppBar,
  Toolbar,
  IconButton,
  Typography,
} from "@mui/material";
import { useState } from "react";

export const NavBar = ({ drawerWidth = 240 }) => {
  const [open, setOpen] = useState(false);

  return (
    <>
      <AppBar
        // position="static"
        sx={{
          width: { sm: `calc(100% - ${drawerWidth}px)` },
          ml: { sm: `${drawerWidth}px` },
        }}
      >
        <Toolbar>
          <IconButton
            aria-label=""
            onClick={() => setOpen(true)}
            color="inherit"
            edge="start"
            sx={{
              display: { xs: "flex", sm: "none" },
              mr: 2,
            }}
          >
            <MenuOutlined />
          </IconButton>

          <Typography
            variant="h6"
            // noWrap
            component="span"
            sx={{ flexGrow: 1 }}
          >
            JournalApp
          </Typography>

          <IconButton aria-label="" color="error">
            <LogoutOutlined />
          </IconButton>
        </Toolbar>
      </AppBar>
    </>
  );
};
```

`src/journal/layout/JournalLayout.jsx`

```jsx
import { Box, Toolbar } from "@mui/material";
import { NavBar } from "../components/NavBar";
import { SideBar } from "../components/SideBar";

const drawerWidth = 280;

export const JournalLayout = ({ children }) => {
  return (
    <Box sx={{ display: "flex" }}>
      {/* Navbar drawerWidth */}
      <NavBar drawerWidth={drawerWidth} />

      {/* Sidebar drawerWidth */}
      <SideBar drawerWidth={drawerWidth} />

      <Box component="main" sx={{ flexGrow: 1, p: 3 }}>
        {/* Toolbar */}
        <Toolbar />
        {children}
      </Box>
    </Box>
  );
};
```

### 17.16 NothingSelectedView - No hay nada seleccionado

Estructura actual:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── journal
│   │   ├── components
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views 👈👀👇
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/journal/views/NothingSelectedView.jsx`

```jsx
import { StarOutline } from "@mui/icons-material";
import { Box, Grid2, Typography } from "@mui/material";

export const NothingSelectedView = () => {
  return (
    <Box
      component="main"
      sx={{
        minHeight: "calc(100vh - 110px)",
        display: "flex",
        flexDirection: "column",
        justifyContent: "center",
        alignItems: "center",
        bgcolor: "primary.main",
        borderRadius: 5,
      }}
    >
      <Grid2>
        <StarOutline
          sx={{ fontSize: 100, color: "white" }}
        />
      </Grid2>
      <Grid2>
        <Typography variant="h5" color="white">
          Select or create a note.
        </Typography>
      </Grid2>
    </Box>
  );
};
```

`src/journal/pages/JournalPage.jsx`

```jsx
import { JournalLayout } from "../layout/JournalLayout";
import { NothingSelectedView } from "../views/NothingSelectedView";

export const JournalPage = () => {
  return (
    <JournalLayout>
      {/* Nothing Selected */}
      <NothingSelectedView />
    </JournalLayout>
  );
};
```

### 17.17 NoteView

Estructura actual:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx 👈👀
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx 👈👀
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/journal/views/NoteView.jsx`

```jsx
import { SaveOutlined } from "@mui/icons-material";
import {
  Button,
  Grid2,
  Typography,
  TextField,
} from "@mui/material";
import { ImageGallery } from "../components/ImageGallery";

export const NoteView = () => {
  return (
    <>
      <Grid2
        container
        justifyContent="space-between"
        alignItems="center"
        sx={{ mb: 1 }}
      >
        <Grid2>
          <Typography
            variant="h5"
            fontSize={39}
            fontWeight="light"
          >
            August 28, 2023
          </Typography>
        </Grid2>

        <Grid2>
          <Button color="primary" sx={{ padding: 2 }}>
            <SaveOutlined sx={{ fontSize: 30, mr: 1 }} />
            Save
          </Button>
        </Grid2>

        <Grid2 container sx={{ flexGrow: 1 }}>
          <TextField
            id=""
            type="text"
            variant="filled"
            label="Title"
            value=""
            onChange=""
            placeholder="Enter a title"
            fullWidth
            sx={{ border: "none", mb: 1 }}
          />
          <TextField
            id=""
            type="text"
            variant="filled"
            // label="Title"
            value=""
            onChange=""
            placeholder="What happened today?"
            fullWidth
            multiline
            minRows={5}
            sx={{ border: "none", mb: 1 }}
          />
        </Grid2>

        {/* Image gallery */}
        <ImageGallery />
      </Grid2>
    </>
  );
};
```

`src/journal/pages/JournalPage.jsx`

```jsx
import { JournalLayout } from "../layout/JournalLayout";
import { NoteView } from "../views/NoteView";
// import { NothingSelectedView } from "../views/NothingSelectedView";

export const JournalPage = () => {
  return (
    <JournalLayout>
      {/* <NothingSelectedView /> */}

      <NoteView />
    </JournalLayout>
  );
};
```

`src/journal/componets/ImageGallery.jsx`

```jsx
export const ImageGallery = () => {
  return (
    <div>ImageGallery</div>
  )
}
```

### 17.18 ImageList - Galería de imágenes

`src/journal/componets/ImageGallery.jsx`

```jsx
import { ImageListItem, ImageList } from "@mui/material";

export const ImageGallery = ({}) => {
  return (
    <ImageList
      sx={{ width: "100%", height: 500 }}
      cols={4}
      rowHeight={200}
    >
      {itemData?.map((item) => (
        <ImageListItem key={item.img}>
          <img
            srcSet={`${item.img}?w=164&h=164&fit=crop&auto=format&dpr=2 2x`}
            src={`${item.img}?w=164&h=164&fit=crop&auto=format`}
            alt={item.title}
            loading="lazy"
          />
        </ImageListItem>
      ))}
    </ImageList>
  );
};

const itemData = [
  {
    img: "https://images.unsplash.com/photo-1551963831-b3b1ca40c98e",
    title: "Breakfast",
  },
  {
    img: "https://images.unsplash.com/photo-1551782450-a2132b4ba21d",
    title: "Burger",
  },
  {
    img: "https://images.unsplash.com/photo-1522770179533-24471fcdba45",
    title: "Camera",
  },
  {
    img: "https://images.unsplash.com/photo-1444418776041-9c7e33cc5a9c",
    title: "Coffee",
  },
  {
    img: "https://images.unsplash.com/photo-1533827432537-70133748f5c8",
    title: "Hats",
  },
  {
    img: "https://images.unsplash.com/photo-1558642452-9d2a7deb7f62",
    title: "Honey",
  },
  {
    img: "https://images.unsplash.com/photo-1516802273409-68526ee1bdd6",
    title: "Basketball",
  },
  {
    img: "https://images.unsplash.com/photo-1518756131217-31eb79b20e8f",
    title: "Fern",
  },
  {
    img: "https://images.unsplash.com/photo-1597645587822-e99fa5d45d25",
    title: "Mushrooms",
  },
  {
    img: "https://images.unsplash.com/photo-1567306301408-9b74779a11af",
    title: "Tomato basil",
  },
  {
    img: "https://images.unsplash.com/photo-1471357674240-e1a485acb3e1",
    title: "Sea star",
  },
  {
    img: "https://images.unsplash.com/photo-1589118949245-7d38baf380d6",
    title: "Bike",
  },
];
```

[Image List](https://mui.com/material-ui/react-image-list/)

### 17.19 Boton Flotante

`src/journal/pages/JournalPage.jsx`

```jsx
import { JournalLayout } from "../layout/JournalLayout";
import { NoteView } from "../views/NoteView";
import IconButton from "@mui/material/IconButton";
import { NothingSelectedView } from "../views/NothingSelectedView";
import { AddOutlined } from "@mui/icons-material";

export const JournalPage = () => {
  return (
    <JournalLayout>
      <NothingSelectedView />

      {/* <NoteView /> */}

      <IconButton
        aria-label=""
        size="large"
        sx={{
          color: "white",
          bgcolor: "error.main",
          ":hover": {
            bgcolor: "error.main",
            opacity: 0.9,
          },
          position: "fixed",
          right: 50,
          bottom: 50,
        }}
      >
        <AddOutlined sx={{ fontSize: 30 }} />
      </IconButton>
    </JournalLayout>
  );
};
```

### 17.20 Código fuente de la sección

Aquí les dejo el código fuente de la sección por si lo llegan a necesitar:

[GitHub - Fin sección 17](https://github.com/Klerith/react-journal-material/tree/fin-seccion-17)

## 🟣 18. Redux - ¿Qué es y conceptos? + React Redux

### 18.1 Introducción a la sección

### 18.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Redux
- Store
- Middlewares
- Dispatch
- Actions
- State
- Acciones asíncronas
- RTK Query
- Redux Toolkit
- Slices

Es una sección sumamente pequeña, pero quiero darles una explicación teórica sobre Redux antes de entrar en él, pero la ventaja es que para estas alturas, ya deberíamos de saber sobre el Reducer, el cual es el corazón del Redux, por consecuencia aprender Redux en este instante debería ser más fácil!

### 18.3 Explicación visual del patrón Redux

Redux es una biblioteca de JavaScript utilizada para gestionar el estado de las aplicaciones, especialmente en entornos como React. Su principal característica es imponer un flujo de datos unidireccional, lo que facilita la predictibilidad y el mantenimiento del estado de la aplicación.

#### ¿Qué es Redux?

Redux centraliza el estado de la aplicación en un único **store** (almacén). Este almacén contiene el estado global de la aplicación y es inmutable; cualquier modificación se realiza mediante **acciones** que describen qué ha ocurrido y **reducers** que especifican cómo el estado debe cambiar en respuesta a esas acciones.

##### ¿Cómo funciona Redux?

Redux sigue un patrón de arquitectura basado en tres principios:

1. **Single Source of Truth**: Todo el estado de la aplicación se almacena en un único objeto llamado **store**.
    
2. **El estado es de solo lectura**: La única forma de modificar el estado es emitiendo una **acción**.
    
3. **Los cambios se realizan con funciones puras**: Para especificar cómo cambia el estado, se usan **reducers**, que son funciones puras que toman el estado anterior y una acción, y devuelven un nuevo estado.

El flujo de datos en Redux sigue estos pasos:

1. **Dispatch de una acción**: Una acción, que es un objeto JavaScript con una propiedad `type`, es enviada utilizando `store.dispatch(action)`.
    
2. **Ejecución del reducer**: Redux pasa el estado actual y la acción al reducer, una función pura que determina cómo actualizar el estado.
    
3. **Actualización del estado**: El reducer devuelve un nuevo estado, que reemplaza al anterior en el store.
    
4. **Notificación a los suscriptores**: Redux notifica a todas las funciones suscritas sobre el cambio de estado, permitiendo que la interfaz de usuario se actualice en consecuencia.

##### Componentes clave de Redux

1. **Store**: Es el objeto que contiene el estado global de la aplicación.
    
2. **Actions**: Son objetos que describen qué sucedió. Tienen un tipo (`type`) y pueden llevar datos adicionales (payload).
    
3. **Reducers**: Son funciones puras que toman el estado actual y una acción, y devuelven un nuevo estado.
    
4. **Dispatch**: Es una función del store que se usa para enviar acciones y actualizar el estado.

#### ¿Qué es un reducer?

Un **reducer** es una función pura que toma el estado anterior y una acción como argumentos, y devuelve un nuevo estado. No debe modificar el estado actual, realizar operaciones con efectos secundarios ni depender de variables externas. Su responsabilidad es especificar cómo cambia el estado en respuesta a una acción.

Ejemplo de un reducer para gestionar una lista de tareas:

```javascript
function todos(state = [], action) {
  switch (action.type) {
    case 'ADD_TODO':
      return [...state, { text: action.text, completed: false }];
    case 'TOGGLE_TODO':
      return state.map((todo, index) =>
        index === action.index ? { ...todo, completed: !todo.completed } : todo
      );
    default:
      return state;
  }
}
```

#### Uso de Redux en operaciones síncronas

En operaciones síncronas, las acciones se envían directamente y los reducers procesan estas acciones de manera inmediata para actualizar el estado.

Ejemplo de una acción síncrona:

```javascript
const addTodo = (text) => ({
  type: 'ADD_TODO',
  text,
});
```

Al despachar `addTodo`, el reducer correspondiente actualizará el estado de forma inmediata.

#### Uso de Redux en operaciones asíncronas

Redux, por defecto, maneja flujos de datos síncronos. Para gestionar operaciones asíncronas, como llamadas a APIs, se utilizan **middlewares** que extienden la funcionalidad de Redux. Uno de los middlewares más comunes es **redux-thunk**, que permite que las acciones sean funciones en lugar de objetos, facilitando la ejecución de operaciones asíncronas.

Para utilizar `redux-thunk`, primero se instala y se aplica al store:

```javascript
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import rootReducer from './reducers';

const store = createStore(rootReducer, applyMiddleware(thunk));
```

Ejemplo de una acción asíncrona utilizando `redux-thunk`:

```javascript
const fetchPosts = () => {
  return (dispatch) => {
    dispatch({ type: 'FETCH_POSTS_REQUEST' });
    fetch('https://api.example.com/posts')
      .then((response) => response.json())
      .then((data) => dispatch({ type: 'FETCH_POSTS_SUCCESS', payload: data }))
      .catch((error) => dispatch({ type: 'FETCH_POSTS_FAILURE', error }));
  };
};
```

En este ejemplo, `fetchPosts` es una función que retorna otra función. Esta función interna realiza una llamada fetch y, según el resultado, despacha acciones que informan al reducer sobre el estado de la operación asíncrona.

Este enfoque permite que Redux maneje tanto flujos de datos síncronos como asíncronos de manera eficiente, manteniendo un estado predecible y coherente en la aplicación.

#### Diagrama Completo de Redux

```mermaid
graph TD
  A[Componente] -->|Dispatch| B[Acción]
  B --> C[Reducer]
  C --> D[Store]
  D -->|Selector| A
```

---

```mermaid
graph TD
  subgraph React
    A[Componente] -->|useDispatch| B{Acción}
    B -->|Síncrona| C[Acción Síncrona]
    B -->|Asíncrona| D[Acción Asíncrona]
    C --> E[Reducer]
    D -->|Thunk| F[Llamada API]
    F -->|Éxito| G[Acción de Éxito]
    F -->|Fallo| H[Acción de Fallo]
    G --> E
    H --> E
    E --> I[Store]
    I -->|useSelector| A
  end

  subgraph Redux
    E -->|Actualiza Estado| I
    I -->|Notifica Cambios| A
  end

  subgraph API Externa
    F -->|GET/POST| J[API Externa]
    J -->|Respuesta| F
  end

  style A fill:#f9f,stroke:#333,stroke-width:2px
  style B fill:#bbf,stroke:#333,stroke-width:2px
  style C fill:#f96,stroke:#333,stroke-width:2px
  style D fill:#f96,stroke:#333,stroke-width:2px
  style E fill:#6f9,stroke:#333,stroke-width:2px
  style F fill:#69f,stroke:#333,stroke-width:2px
  style G fill:#6f9,stroke:#333,stroke-width:2px
  style H fill:#f66,stroke:#333,stroke-width:2px
  style I fill:#9cf,stroke:#333,stroke-width:2px
  style J fill:#ccc,stroke:#333,stroke-width:2px
```

##### Explicación del Diagrama

1. **Componente (React)**:
   - El componente de React inicia el flujo al despachar una acción (`useDispatch`).
   - Puede despachar acciones **síncronas** (como incrementar un contador) o **asíncronas** (como una llamada a una API).

2. **Acción Síncrona**:
   - Una acción síncrona es un objeto simple que describe un cambio (por ejemplo, `{ type: 'INCREMENT' }`).
   - Esta acción es enviada directamente al **reducer**.

3. **Acción Asíncrona**:
   - Una acción asíncrona (manejada por Thunk o Redux Toolkit) realiza una operación asíncrona, como una llamada a una API.
   - Dependiendo del resultado de la API, se despacha una **acción de éxito** o una **acción de fallo**.

4. **Reducer**:
   - El reducer recibe la acción y el estado actual, y devuelve un nuevo estado.
   - Es una función pura que no tiene efectos secundarios.

5. **Store**:
   - El store contiene el estado global de la aplicación.
   - Cuando el reducer actualiza el estado, el store notifica a los componentes suscritos (`useSelector`).

6. **API Externa**:
   - Las acciones asíncronas interactúan con APIs externas para obtener o enviar datos.
   - La respuesta de la API determina si la acción fue exitosa o fallida.

7. **Notificación de Cambios**:
   - Cuando el estado en el store cambia, los componentes de React que usan `useSelector` se actualizan automáticamente.

---

```mermaid
graph TD;
    %% Sección de inicio
    A[Usuario interactúa con la UI] -->|Ejecuta función en React| B[Dispatch de una acción]

    %% Manejo de acciones síncronas
    B -->|Acción síncrona| C{¿Es asíncrona?}
    C -- No --> D[Reducer procesa la acción]
    D --> E[Genera un nuevo estado]
    E --> F[Store actualiza el estado global]
    F --> G[Componentes suscritos detectan cambios]
    G --> H[La UI se renderiza nuevamente]

    %% Manejo de acciones asíncronas con Redux-Thunk
    C -- Sí --> I[Llamada a una API u operación asíncrona]
    I --> J{¿Éxito o error?}
    J -- Éxito --> K[Dispatch de acción de éxito]
    J -- Error --> L[Dispatch de acción de error]

    K --> D
    L --> D

    %% Middleware en acción
    subgraph Middleware_Thunk
        B -->|Intercepta la acción| M[Verifica si la acción es una función]
        M -- Sí --> I
        M -- No --> D
    end

    %% Relación entre el store y los componentes de React
    subgraph Store_Global
        F --> O[Componentes obtienen el estado actualizado con useSelector]
        O --> G
    end

    %% Componentes despachando acciones
    subgraph Componentes_React
        P[useDispatch ejecuta acción] --> B
        G --> Q[UI actualizada]
    end
```

### 18.4 Redux, React Redux y RTK Query

**React Redux** y **Redux Toolkit** siguen siendo herramientas fundamentales en el ecosistema de Redux, pero cada una tiene un propósito y enfoque diferente.

#### React Redux

React Redux es la librería oficial que permite integrar Redux con React. Su función principal es conectar el store de Redux con los componentes de React, facilitando el acceso al estado global y la despacho de acciones.

Características principales:

1. **Provider**:
   - Provee el store de Redux a toda la aplicación mediante el componente `<Provider>`.

2. **Hooks**:
   - `useSelector`: Permite a los componentes acceder al estado global almacenado en el store.
   - `useDispatch`: Permite a los componentes despachar acciones para actualizar el estado.

3. **Conectores**:
   - Aunque los hooks son la forma recomendada, React Redux también soporta el uso de `connect` (una API más antigua) para conectar componentes de clase con el store.

4. **Rendimiento optimizado**:
   - React Redux optimiza el rendimiento al evitar renders innecesarios en los componentes cuando el estado cambia.

Uso típico:

React Redux se usa cuando ya tienes un store de Redux configurado y necesitas conectar tus componentes de React a ese store. Es la capa de integración entre React y Redux.

---

#### Redux Toolkit (RTK)

Redux Toolkit (RTK) es la librería oficial recomendada por el equipo de Redux para simplificar la configuración y el uso de Redux. Proporciona herramientas y abstracciones que reducen la cantidad de código repetitivo y mejoran la legibilidad.

Características principales:

1. **configureStore**:
   - Simplifica la creación del store de Redux, incluyendo la configuración automática de middlewares como Redux Thunk y Redux DevTools.

2. **createSlice**:
   - Permite definir reducers y acciones en un solo lugar, reduciendo la necesidad de escribir código repetitivo.
   - Genera automáticamente action creators y action types.

3. **createAsyncThunk**:
   - Facilita el manejo de operaciones asíncronas (como llamadas a APIs) sin necesidad de escribir lógica compleja.

4. **createEntityAdapter**:
   - Proporciona una forma eficiente de manejar colecciones de datos normalizadas en el store.

5. **Integración con React Redux**:
   - Redux Toolkit está diseñado para funcionar perfectamente con React Redux, por lo que puedes usar ambas librerías juntas.

Uso típico:

Redux Toolkit se usa para simplificar la configuración y el mantenimiento de un store de Redux. Es especialmente útil en aplicaciones grandes donde la cantidad de código y la complejidad pueden crecer rápidamente.

#### Diferencias clave entre React Redux y Redux Toolkit

| Característica                | React Redux                         | Redux Toolkit (RTK)                 |
|-------------------------------|--------------------------------------|--------------------------------------|
| **Propósito**                 | Integrar Redux con React             | Simplificar la configuración de Redux|
| **Creación del store**        | No proporciona herramientas para crear el store | Proporciona `configureStore` para crear el store fácilmente |
| **Definición de reducers**    | Requiere definir reducers y acciones manualmente | Usa `createSlice` para definir reducers y acciones de forma simplificada |
| **Manejo de operaciones asíncronas** | Requiere middleware adicional (como Redux Thunk) | Incluye `createAsyncThunk` para manejar operaciones asíncronas |
| **Código repetitivo**         | Genera más código repetitivo         | Reduce significativamente el código repetitivo |
| **Integración**               | Necesita Redux Toolkit o configuración manual para simplificar Redux | Diseñado para funcionar con React Redux |
| **Rendimiento**               | Optimizado para evitar renders innecesarios | Depende de React Redux para la optimización de renders |

### 18.5 Inicio de proyecto - Redux-Tool

Creamos el proyecto:

```bash
yarn create vite
# 09-toolkit-redux
# React
# JavaScript + SWC

cd 09-toolkit-redux
yarn
```

Instalamos Redux:

```bash
# Un solo comando
yarn add @reduxjs/toolkit react-redux

# Por separado
yarn add @reduxjs/toolkit
yarn add react-redux
```

`src/App.jsx`

```jsx
import { useState } from "react";
import reactLogo from "./assets/react.svg";
import viteLogo from "/vite.svg";
import "./App.css";

function App() {
  const [count, setCount] = useState(0);

  return (
    <>
      <div>
        <a href="https://vite.dev" target="_blank">
          <img
            src={viteLogo}
            className="logo"
            alt="Vite logo"
          />
        </a>
        <a href="https://react.dev" target="_blank">
          <img
            src={reactLogo}
            className="logo react"
            alt="React logo"
          />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button
          onClick={() => setCount((count) => count + 1)}
        >
          count is {count}
        </button>
      </div>
    </>
  );
}

export default App;
```

- [Redux DevTools](https://chromewebstore.google.com/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=en)
- [Redux Toolkit](https://redux-toolkit.js.org/)
- [¿Qué es Redux?](https://www.youtube.com/watch?v=j-jzI3wkkVk)

### 18.6 ConfigureStore y Slices

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── App.jsx
│   ├── main.jsx
│   └── store
│       ├── slices
│       │   ├── counter
│       │   │   └── counterSlice.js
│       │   ├── pokemon
│       │   └── todos
│       └── store.js
├── vite.config.js
└── yarn.lock
```

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { counterSlice } from "./slices/counter/counterSlice";

export const store = configureStore({
  reducer: {
    counter: counterSlice.reducer,
  },
});
```

`src/store/slices/counter/counterSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = { 👈👀
   🔥counter: 10,
};

export const counterSlice = createSlice({
  name: "counter",
  initialState,  👈👀
  reducers: {
    increment: (state) => {
      state.counter += 1;
    },
  },
});

export const { increment } = counterSlice.actions; 👈👀
```

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import { Provider } from "react-redux";
import { store } from "./store/store";

import App from "./App.jsx";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <Provider store={store}>
      <App />
    </Provider>
  </StrictMode>
);
```

### 18.7 Usar valores del store y despachar acciones

`src/App.jsx`

```jsx
import { useDispatch, useSelector } from "react-redux";

import { increment } from "./store/slices/counter/counterSlice";

function App() {
  const { counter } = useSelector(
    (state) => state.counter
  );
  const dispatch = useDispatch();

  return (
    <>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => dispatch(increment())}>
          count is {counter}
        </button>
      </div>
    </>
  );
}

export default App;
``` 

#### Ejemplo explicado

![](https://i.postimg.cc/y8LQBBb9/18-7-redux.png)

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── App.jsx
│   ├── main.jsx
│   └── store
│       ├── slices
│       │   ├── counter
│       │   │   ├── Counter.jsx
│       │   │   └── counterSlice.js
│       │   ├── pokemon
│       │   └── todos
│       └── store.js
├── vite.config.js
└── yarn.lock
```

1. Explicación de `createSlice` y las Exportaciones

Archivo: `counterSlice.js`

```javascript
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  value: 0,
};

export const counterSlice = createSlice({
  name: "counter",
  initialState, // 👈👀
  reducers: {
    increment: (state) => { state.value += 1; },
    decrement: (state) => { state.value -= 1; },
    reset: (state) => { state.value = 0; },
  },
});

export const { increment, decrement, reset } = counterSlice.actions;

// Beware of this export
export default counterSlice.reducer;
```

¿Qué hace `createSlice`?

`createSlice` es una función de Redux Toolkit que simplifica la creación de un "slice" del estado global. Un "slice" es una porción del estado que contiene la lógica relacionada con una funcionalidad específica (en este caso, un contador).

- **`name`**: Define el nombre del slice. En este caso, es `"counter"`.
- **`initialState`**: Define el estado inicial del slice. Aquí, el contador comienza en `0`.
- **`reducers`**: Define las funciones que actualizan el estado. Cada reducer recibe el estado actual y puede modificarlo directamente (gracias a Immer, que se encarga de la inmutabilidad).

¿De dónde sale `counterSlice.actions`?

Cuando llamas a `createSlice`, Redux Toolkit genera automáticamente **action creators** para cada reducer definido en `reducers`. Estos action creators se almacenan en `counterSlice.actions`.

- **`increment`**, **`decrement`**, **`reset`**: Son action creators que puedes usar para despachar acciones en tu aplicación.
- Por ejemplo, `increment()` devuelve una acción de tipo `"counter/increment"`.

¿De dónde sale `counterSlice.reducer`?

`createSlice` también genera un **reducer** que maneja todas las acciones definidas en `reducers`. Este reducer se almacena en `counterSlice.reducer`.

- **`counterSlice.reducer`**: Es la función que Redux usa para actualizar el estado cuando se despacha una acción.

![](https://i.postimg.cc/BnkkPm67/18-8-create-slice.png)

2. Configuración del Store

Archivo: `store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import counterSlice from "./slices/counter/counterSlice";

export const store = configureStore({
  reducer: {
    counter: counterSlice,
  },
});
```

¿Qué hace `configureStore`?

`configureStore` es una función de Redux Toolkit que simplifica la creación del store de Redux.

- **`reducer`**: Aquí defines los reducers que manejarán el estado global. En este caso, solo tenemos un reducer: `counterSlice`.

3. Conexión con React

Archivo: `main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import { Provider } from "react-redux";
import { store } from "./store/store";

import App from "./App.jsx";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <Provider store={store}>
      <App />
    </Provider>
  </StrictMode>
);
```

¿Qué hace `Provider`?

`Provider` es un componente de React Redux que hace que el store de Redux esté disponible para todos los componentes de la aplicación.

- **`store`**: Le pasas el store que configuraste en `store.js`.

4. Componente del Contador

Archivo: `Counter.jsx`

```jsx
import { useDispatch, useSelector } from "react-redux";
import { decrement, increment, reset } from "./counterSlice";

export const Counter = () => {
  const count = useSelector((state) => state.counter.value);
  const dispatch = useDispatch();

  return (
    <div>
      <h1>Counter: {count}</h1>
      <button onClick={() => dispatch(increment())}>Increase</button>
      <button onClick={() => dispatch(decrement())}>Decrement</button>
      <button onClick={() => dispatch(reset())}>Reset</button>
    </div>
  );
};
```

¿Qué hacen `useSelector` y `useDispatch`?

- **`useSelector`**: Es un hook de React Redux que te permite acceder al **estado** global. En este caso, `state.counter.value` obtiene el valor del contador.
- **`useDispatch`**: Es un hook que te permite despachar acciones para actualizar el estado. Aquí, se usa para despachar `increment`, `decrement` y `reset`.

5. Componente Principal

Archivo: `App.jsx`

```jsx
import { Counter } from "./store/slices/counter/counter";

const App = () => {
  return (
    <div>
      <h1>Counter App</h1>
      <Counter />
    </div>
  );
}

export default App;
```

`App` es el componente principal de la aplicación. Renderiza el componente `Counter`.

6. Flujo Completo

- **Store**: El store de Redux se configura en `store.js` y se provee a la aplicación mediante `Provider`.
- **Slice**: El slice `counterSlice.js` define la lógica del contador, incluyendo los reducers y las acciones.
- **Componente**: El componente `Counter.jsx` usa `useSelector` para acceder al estado y `useDispatch` para enviar acciones.
- **UI**: Cuando el usuario interactúa con los botones, se despachan acciones que actualizan el estado en el store, y la UI se actualiza automáticamente.

### 18.8 Tarea - decrement e incrementBy

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import { Provider } from "react-redux";
import { store } from "./store/store";

import App from "./App.jsx";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <Provider store={store}>
      <App />
    </Provider>
  </StrictMode>
);
```

`src/App.jsx`

```jsx
import { useDispatch, useSelector } from "react-redux";
import {
  increment,
  incrementBy,
  decrement,
} from "./store/slices/counter/counterSlice";

function App() {
  const { counter } = useSelector(
    (state) => state.counter
  );
  const dispatch = useDispatch();

  return (
    <>
      <h1>Count is {counter}</h1>
      <div className="card">
        <button onClick={() => dispatch(increment())}>
          Increment
        </button>
        <button onClick={() => dispatch(incrementBy(5))}>
          IncrementByTwo
        </button>
        <button onClick={() => dispatch(decrement())}>
          Decrement
        </button>
      </div>
    </>
  );
}

export default App;
```

`src/store/slices/counter/counterSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  counter: 0,
};

export const counterSlice = createSlice({
  name: "counter",
  initialState,
  reducers: {
    increment: (state) => {
      state.counter += 1;
    },
    incrementBy: (state, action) => {
      state.counter += action.payload;
      console.log(action);
    },
    decrement: (state) => {
      state.counter -= 1;
    },
  },
});

export const { increment, incrementBy, decrement } =
  counterSlice.actions;

// export default counterSlice.reducer;
```

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { counterSlice } from "./slices/counter/counterSlice";

export const store = configureStore({
  reducer: {
    counter: counterSlice.reducer,
  },
});
```

### 18.9 Snippet y Gists de Slice

En esta clase se crea un Snippets para crear rápidamente la estructura de un `Slice` de Redux, pero si no quieres usar un Snippet personalizado, una extensión previamente instalada ya lo hace por ti:

- [ES7+ React/Redux/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
- [Atajos para usar los Snippets](https://github.com/r5n-labs/vscode-react-javascript-snippets/blob/HEAD/docs/Snippets.md)

#### Crea tu snippet personalizado

En Visual Studio Code presiona:
- `Ctrl + Shift + P`
- Escribe:
	- Configure User Snippets
	- Configure Snippets 👈👀 Nuevo
	- JavaScript

`~/.config/Code - Insiders/User/snippets/javascript.json`

```json
{
  // Place your snippets for javascript here. Each snippet is defined under a snippet name and has a prefix, body and 
  // description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
  // $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the 
  // same ids are connected.
  // Example:
  // "Print to console": {
  // 	"prefix": "log",
  // 	"body": [
  // 		"console.log('$1');",
  // 		"$2"
  // 	],
  // 	"description": "Log output to console"
  // }

  "Create a Redux slice": {
    "prefix": "redux-slice",
    "body": [
      "import { createSlice } from '@reduxjs/toolkit';",
      "",
      "export const ${1:template}Slice = createSlice({",
      "  name: '${1:template}',",
      "  initialState: {",
      "    counter: 10,",
      "  },",
      "  reducers: {",
      "    increment: (state /* action */) => {",
      "      state.counter += 1;",
      "    },",
      "  },",
      "});",
      "",
      "export const { increment } = ${1:template}Slice.actions;",
    ],
    "description": "Create a Redux slice"
  }
}
```

Ahora al escribir `redux-slice` te genere la estructura.

📌 Recuerda usar espacios en lugar de tabulaciones, cámbialo rápidamente con:

- `Ctrl + Shift + P`
- Indent using spaces

### 18.10 pokemonSlice

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── App.jsx
│   ├── main.jsx
│   ├── PokeApp.jsx 👈👀
│   └── store
│       ├── slices
│       │   ├── counter
│       │   │   └── counterSlice.js
│       │   ├── pokemon 👈👀👇
│       │   │   └── pokeSlice.js
│       │   └── todos
│       └── store.js
├── vite.config.js
└── yarn.lock
```

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import { store } from "./store/store";
import { Provider } from "react-redux";

import { PokeApp } from "./PokeApp.jsx";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <Provider store={store}>
      <PokeApp />
    </Provider>
  </StrictMode>
);
```

`src/PokeApp.jsx`

```jsx
export const PokeApp = () => {
  return (
    <>
      <h1>PokeApp</h1>
      <hr />
      <ul>
        <li>Hi</li>
        <li>Hi</li>
        <li>Hi</li>
      </ul>
    </>
  );
};
```

`src/store/slices/pokemon/pokeSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  page: 0,
  pokemons: [],
  isLoading: false,
};

export const pokeSlice = createSlice({
  name: "poke",
  initialState,
  reducers: {
    startLoadingPokemons: (state) => {
      state.isLoading = true;
    },
    setPokemons: (state, action) => {
      console.log(action);
    },
  },
});

export const { startLoadingPokemons, setPokemons } =
  pokeSlice.actions;
```

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { counterSlice } from "./slices/counter/counterSlice";
import { pokeSlice } from "./slices/pokemon/pokeSlice";

export const store = configureStore({
  reducer: {
    counter: counterSlice.reducer,
    poke: pokeSlice.reducer,
  },
});
```

[Poke Api](https://pokeapi.co/)

### 18.11 Thunks en React Redux

Los thunks son un patrón fundamental en Redux para manejar lógica asincrónica y efectos secundarios.

Un **thunk** es una función que envuelve una expresión para retrasar su evaluación. En Redux, es una función que retrasa la ejecución de una acción o permite ejecutar lógica asincrónica antes de despachar una acción.

Sirven para:

1. **Manejar operaciones asincrónicas** (llamadas API, timeouts, etc.)
2. **Despachar múltiples acciones** en secuencia
3. **Acceder al estado actual** antes de despachar
4. **Encapsular lógica compleja** que no cabe en una acción simple

#### Cómo usar thunks con Redux Toolkit

1. Configuración inicial

Primero, necesitas configurar el middleware en tu store:

```javascript
import { configureStore } from '@reduxjs/toolkit'
import thunkMiddleware from 'redux-thunk'

const store = configureStore({
  reducer: rootReducer,
  middleware: [thunkMiddleware]
})
```

2. Crear un thunk

Un thunk es una función que recibe `dispatch` y `getState` como parámetros:

```javascript
const fetchUserData = (userId) => {
  return async (dispatch, getState) => {
    dispatch(userDataLoading()) // Acción sincrónica para indicar carga
    
    try {
      const response = await fetch(`/api/users/${userId}`)
      const data = await response.json()
      dispatch(userDataSuccess(data)) // Acción con los datos obtenidos
    } catch (error) {
      dispatch(userDataFailure(error)) // Acción si hay error
    }
  }
}
```

3. Despachar el thunk

Desde tus componentes React, lo despachas como cualquier otra acción:

```javascript
import { useDispatch } from 'react-redux'

function UserProfile({ userId }) {
  const dispatch = useDispatch()
  
  useEffect(() => {
    dispatch(fetchUserData(userId))
  }, [dispatch, userId])
  
  // Renderizar el componente...
}
```

#### Ejemplo completo

```javascript
// actions.js
import { createAsyncThunk } from '@reduxjs/toolkit'

export const fetchUser = createAsyncThunk(
  'users/fetchUser',
  async (userId, thunkAPI) => {
    try {
      const response = await fetch(`/api/users/${userId}`)
      return await response.json()
    } catch (error) {
      return thunkAPI.rejectWithValue(error.message)
    }
  }
)

// reducer.js
import { createSlice } from '@reduxjs/toolkit'

const usersSlice = createSlice({
  name: 'users',
  initialState: { data: null, loading: false, error: null },
  reducers: {},
  extraReducers: (builder) => {
    builder
      .addCase(fetchUser.pending, (state) => {
        state.loading = true
      })
      .addCase(fetchUser.fulfilled, (state, action) => {
        state.loading = false
        state.data = action.payload
      })
      .addCase(fetchUser.rejected, (state, action) => {
        state.loading = false
        state.error = action.payload
      })
  }
})

export default usersSlice.reducer
```

#### Ventajas de usar thunks

- **Separación de preocupaciones**: La lógica asincrónica no está en los componentes
- **Reutilización**: Puedes despachar el mismo thunk desde diferentes lugares
- **Testabilidad**: Más fácil de testear que la lógica en componentes
- **Flexibilidad**: Puedes acceder al estado actual con `getState()`

Los thunks son especialmente útiles cuando necesitas:
- Hacer llamadas a APIs
- Despachar acciones en secuencia
- Tomar decisiones basadas en el estado actual

Redux Toolkit simplifica el uso de thunks con `createAsyncThunk`, que maneja automáticamente los estados de pending/fulfilled/rejected.

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── App.jsx
│   ├── main.jsx
│   ├── PokeApp.jsx
│   └── store
│       ├── slices
│       │   ├── counter
│       │   │   └── counterSlice.js
│       │   ├── pokemon
│       │   │   ├── pokeSlice.js
│       │   │   └── thunks.js 👈👀
│       │   └── todos
│       └── store.js
├── vite.config.js
└── yarn.lock
```

`src/store/slices/pokemon/thunks.js`

```js
import {
  setPokemons,
  startLoadingPokemons,
} from "./pokeSlice";

export const getPokemons = (page = 0) => {
  return async (dispatch, getState) => {
    dispatch(startLoadingPokemons());

    // TODO: realizar petición
    // dispatch(setPokemons())
  };
};

// https://pokeapi.co/api/v2/pokemon/limit=10&offset=0
```

`src/PokeApp.jsx`

```jsx
import { useEffect } from "react";
import { useDispatch } from "react-redux";
import { getPokemons } from "./store/slices/pokemon/thunks";

export const PokeApp = () => {
  const dispatch = useDispatch();

  useEffect(() => {
    dispatch(getPokemons());
  }, []);

  return (
    <>
      <h1>PokeApp</h1>
      <hr />
      <ul>
        <li>Hi</li>
        <li>Hi</li>
        <li>Hi</li>
      </ul>
    </>
  );
};
```

### 18.12 Axios

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── api 👀👇
│   │   └── pokeApi.js
│   ├── App.jsx
│   ├── main.jsx
│   ├── PokeApp.jsx
│   └── store
│       ├── slices
│       │   ├── counter
│       │   │   └── counterSlice.js
│       │   ├── pokemon
│       │   │   ├── pokeSlice.js
│       │   │   └── thunks.js
│       │   └── todos
│       └── store.js
├── vite.config.js
└── yarn.lock
```

```bash
yarn add axios
```

`src/store/slices/pokemon/pokeSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  page: 0,
  pokemons: [],
  isLoading: false,
};

export const pokeSlice = createSlice({
  name: "poke",
  initialState,
  reducers: {
    startLoadingPokemons: (state) => {
      state.isLoading = true;
    },
    setPokemons: (state, action) => {
      state.isLoading = false;
      state.page = action.payload.page;
      state.pokemons = action.payload.pokemons;
    },
  },
});

export const { startLoadingPokemons, setPokemons } =
  pokeSlice.actions;
```

`src/store/slices/pokemon/thunks.js`

```js
import { pokeApi } from "../../../api/pokeApi";
import {
  setPokemons,
  startLoadingPokemons,
} from "./pokeSlice";

export const getPokemons = (page = 0) => {
  return async (dispatch, getState) => {
    dispatch(startLoadingPokemons());

    // TODO: realizar petición
    // const response = await fetch(
    //   `https://pokeapi.co/api/v2/pokemon?limit=10&offset=${
    //     page * 10
    //   }`
    // );
    // const data = await response.json();

    const { data } = await pokeApi.get(
      `/pokemon?limit=10&offset=${page * 10}`
    );

    dispatch(
      setPokemons({
        pokemons: data.results,
        page: page + 1,
      })
    );
  };
};

// https://pokeapi.co/api/v2/pokemon/limit=10&offset=0
```

`src/api/pokeApi.js`

```js
import axios from "axios";

export const pokeApi = axios.create({
  baseURL: "https://pokeapi.co/api/v2"
})
```

### 18.13 Mostrar los pokemons paginadamente

`src/PokeApp.jsx`

```jsx
import { useEffect } from "react";
import { useDispatch, useSelector } from "react-redux";
import { getPokemons } from "./store/slices/pokemon/thunks";

export const PokeApp = () => {
  const dispatch = useDispatch();
  const {
    isLoading,
    pokemons = [],
    page,
  } = useSelector((state) => state.poke);

  useEffect(() => {
    dispatch(getPokemons());
  }, []);

  return (
    <>
      <h1>PokeApp</h1>
      <hr />
      <span>Loading: {isLoading ? "True" : "False"}</span>

      <ul>
        {pokemons.map(({ name }) => (
          <li key={name}>{name}</li>
        ))}
      </ul>

      <button
        disabled={isLoading}
        onClick={() => dispatch(getPokemons(page))}
      >
        Next
      </button>
    </>
  );
};
```

Vista general:

![Redux async](https://i.postimg.cc/SK9D8x5x/18-13-redux-async.png)

📌 Nota: En la imagen, en el archivo `main.jsx` en lugar de `<TodoApp />` es `<PokeApp />`.

[Axios Curso](https://www.youtube.com/watch?v=i8sr--1D13Y)

### 18.14 RTK Query

RTK Query es una capa de abstracción sobre **Redux** que automatiza:  
- **Solicitudes API** (GET, POST, PUT, DELETE).  
- **Caching inteligente** (evita peticiones redundantes).  
- **Actualización de datos en tiempo real** (revalidación, pooling, optimistic updates).  
- **Gestión de estados de carga y error**.  

No requiere escribir manualmente acciones, reductores o selectores de Redux, lo que reduce significativamente el código boilerplate.  

#### **Novedades y Actualizaciones en 2025**

1. **Mejor Soporte para GraphQL**:  
   - Aunque RTK Query se enfoca principalmente en REST, en 2025 sigue siendo compatible con GraphQL mediante integraciones como `graphql-request` o Apollo Client, aunque no es su enfoque principal.  

2. **Integración con React Server Components (RSC)**:  
   - Con la adopción masiva de **React Server Components** en Next.js y otros frameworks, RTK Query ha mejorado su compatibilidad para manejar fetching de datos tanto en el cliente como en el servidor.  

3. **Optimizaciones de Rendimiento**:  
   - Se han introducido mejoras en el **cache tagging** y **garbage collection automático** para evitar problemas de memoria en aplicaciones grandes.  

4. **Soporte para Streaming SSR**:  
   - Ahora funciona mejor con renderizado streaming (Suspense) en frameworks como Next.js.  

5. **Alternativas y Competencia**:  
   - Aunque sigue siendo muy usado, herramientas como **TanStack Query (React Query)** y **SWR** mantienen su popularidad, especialmente en proyectos que no usan Redux.  

#### **¿Cuándo Usar RTK Query?**

✅ **Ideal si:**

- Ya usas Redux en tu proyecto.  
- Necesitas un manejo de caché eficiente.  
- Quieres menos código repetitivo en llamadas API.  

❌ **Alternativas si:**

- No usas Redux (considera TanStack Query o SWR).  
- Trabajas principalmente con GraphQL (Apollo Client es mejor opción).  

#### **Ejemplo Básico**

```tsx
import { createApi, fetchBaseQuery } from '@reduxjs/toolkit/query/react';

const api = createApi({
  reducerPath: 'pokemonApi',
  baseQuery: fetchBaseQuery({ baseUrl: 'https://pokeapi.co/api/v2/' }),
  endpoints: (builder) => ({
    getPokemon: builder.query({
      query: (name) => `pokemon/${name}`,
    }),
  }),
});

// Uso en un componente React con hooks generados automáticamente
const { data, isLoading, error } = useGetPokemonQuery('pikachu');
```

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── README.md
├── src
│   ├── api
│   │   └── pokeApi.js
│   ├── App.jsx
│   ├── main.jsx
│   ├── PokeApp.jsx
│   ├── store
│   │   ├── apis 👀👇
│   │   │   └── todosApi.js
│   │   ├── slices
│   │   │   ├── counter
│   │   │   │   └── counterSlice.js
│   │   │   ├── pokemon
│   │   │   │   ├── pokeSlice.js
│   │   │   │   └── thunks.js
│   │   │   └── todos
│   │   └── store.js
│   └── TodoApp.jsx 👈👀
├── vite.config.js
└── yarn.lock
```

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";

import { store } from "./store/store";
import { Provider } from "react-redux";

import { TodoApp } from "./TodoApp.jsx";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <Provider store={store}>
      <TodoApp />
    </Provider>
  </StrictMode>
);
```

`src/TodoApp.jsx`

```jsx
export const TodoApp = () => {
  return (
    <>
      <h1>Todos - RTK Query</h1>
      <hr />
      <h4>isLoading</h4>

      <pre>...</pre>

      <button>Next Todo</button>
    </>
  );
};
```

`src/store/apis/todosApi.js`

```js
import {
  createApi,
  fetchBaseQuery,              👀👇
} from "@reduxjs/toolkit/query/react";

export const todosApi = createApi({
  reducerPath: "todos",
  baseQuery: fetchBaseQuery({
    baseUrl: "https://jsonplaceholder.typicode.com",
  }),
  endpoints: (builder) => ({
   🔥getTodos: builder.query({
      query: () => "/todos",
    }),
  }),
});

export const { 🔥useGetTodosQuery } = todosApi;
```

- [RTK Query](https://redux-toolkit.js.org/rtk-query/overview)
- [Json Placeholder](https://jsonplaceholder.typicode.com/)
- [Create an api slice](https://redux-toolkit.js.org/rtk-query/overview#create-an-api-slice)

### 18.15 Consumir el API mediante el custom hook

#### Propiedad Computada en JavaScript

Una **propiedad computada** (o "computed property" en inglés) es una característica de JavaScript que te permite definir propiedades de un objeto usando una expresión como nombre de la propiedad, en lugar de un identificador fijo.

En tu código:

```javascript
{
  [todosApi.reducerPath]: todosApi.reducer
}
```

La parte `[todosApi.reducerPath]` es una propiedad computada. Lo que hace es:

1. Evalúa la expresión dentro de los corchetes `[]`
2. Usa el resultado de esa expresión como el nombre de la propiedad

¿Cómo funciona?

Supongamos que `todosApi.reducerPath` tiene el valor `'api'`. Entonces el objeto resultante sería:

```javascript
{
  api: todosApi.reducer
}
```

¿Por qué se usa en Redux Toolkit?

En este caso específico de Redux Toolkit:
- `todosApi` es probablemente un API slice creado con RTK Query
- `reducerPath` es una propiedad que contiene el string bajo el cual el reducer debe ser montado en el store
- Usando una propiedad computada, puedes hacer que el nombre del reducer sea dinámico y configurable

Otro ejemplo sencillo

```javascript
const propName = 'color';
const obj = {
  [propName]: 'blue',  // propiedad computada
  size: 'large'       // propiedad normal
};

console.log(obj); // { color: 'blue', size: 'large' }
```

Las propiedades computadas son muy útiles cuando necesitas que el nombre de una propiedad sea dinámico o calculado en tiempo de ejecución.

`src/TodoApp.jsx`

```jsx
import { useGetTodosQuery } from "./store/apis/todosApi";

export const TodoApp = () => {
  const { data: todos = [], isLoading } =
    useGetTodosQuery();

  return (
    <>
      <h1>Todos - RTK Query</h1>
      <hr />
      <h4>isLoading: {isLoading ? "True" : "False"}</h4>

      <pre>...</pre>

      <ul>
        {todos.map((todo) => (
          <li key={todo.id}>
            <strong>
              {todo.completed ? "DONE" : "Pending"}
            </strong>
            {todo.title}
          </li>
        ))}
      </ul>

      <button>Next Todo</button>
    </>
  );
};
```

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { counterSlice } from "./slices/counter/counterSlice";
import { pokeSlice } from "./slices/pokemon/pokeSlice";
import { todosApi } from "./apis/todosApi";

export const store = configureStore({
  reducer: {
    counter: counterSlice.reducer,
    poke: pokeSlice.reducer,

    [todosApi.reducerPath]: todosApi.reducer,
  },
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware().concat(todosApi.middleware),
});
```

Vista general:

![](https://i.postimg.cc/4yBBrvx8/18-15-RTK-Query-data.png)

### 18.16 Obtener un Todo por ID

`src/TodoApp.jsx`

```jsx
import { useState } from "react";
import { useGetTodoQuery } from "./store/apis/todosApi";

export const TodoApp = () => {
  const [todoId, setTodoId] = useState(1);
  const { data: todo } = useGetTodoQuery(todoId);

  const nextTodo = () => {
    setTodoId(todoId + 1);
  };
  const prevTodo = () => {
    if (todoId === 1) return;

    setTodoId(todoId - 1);
  };

  return (
    <>
      <h1>Todos - RTK Query</h1>
      <hr />

      <pre>{JSON.stringify(todo)}</pre>

      <button onClick={prevTodo}>Previous Todo</button>
      <button onClick={nextTodo}>Next Todo</button>
    </>
  );
};
```

`src/store/apis/todosApi.js`

```js
import {
  createApi,
  fetchBaseQuery,
} from "@reduxjs/toolkit/query/react";

export const todosApi = createApi({
  reducerPath: "todos",
  baseQuery: fetchBaseQuery({
    baseUrl: "https://jsonplaceholder.typicode.com",
  }),
  endpoints: (builder) => ({
    getTodos: builder.query({
      query: () => "/todos",
    }),
    getTodo: builder.query({
      query: (todoId) => `/todos/${todoId}`,
    }),
  }),
});

export const { useGetTodosQuery, useGetTodoQuery } =
  todosApi;
```

Vista general:

![](https://i.postimg.cc/RVs8WmLW/18-14-RTK-Query.png)

Desplegamos:

[Proyecto Redux Toolkit](https://redux1toolkit.netlify.app/)

### 18.17 Código fuente de la sección

Aquí les dejo el código fuente de la sección por si lo llegan a necesitar para compararlo contra el mío

[**Fin sección 18 - Introducción a Redux**](https://github.com/Klerith/redux-toolkit-rtk-demo)

## 🟣 19. Introducción a Redux y autenticación en Firebase

### 19.1 Introducción a la sección

### 19.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Redux aplicado en nuestro proyecto
- Firebase
- FireStore
- Redux Devtools
- Thunk
- Formularios
- Google SingIn
- Acciones Asíncronas
- Mantener el estado de la autenticación

En esta sección configuraremos Redux en nuestro proyecto por primera vez, aplicado al inicio en la parte de la autenticación y mantener el estado de la misma a lo largo de toda la aplicación.

### 19.3 Demostración del objetivo final de la sección

### 19.4 Configurando Redux en nuestra aplicación

Instalamos Redux:

```bash
# Un solo comando
yarn add @reduxjs/toolkit react-redux

# Por separado
yarn add @reduxjs/toolkit
yarn add react-redux
```

Estructura:

```bash
.
├── eslint.config.js
├── index.htmlclear
├── package.json
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store 👈👀
│   │   └── store.js 
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";

export const store = configureStore({
  reducer: {}
})
```

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { BrowserRouter } from "react-router-dom";

import { Provider } from "react-redux";
import { store } from "./store/store.js";
import { App } from "./App.jsx";

import "./styles.css";
import "@fontsource/roboto/300.css";
import "@fontsource/roboto/400.css";
import "@fontsource/roboto/500.css";
import "@fontsource/roboto/700.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>  👀👇
    <Provider store={store}>
      <BrowserRouter>
        <App />
      </BrowserRouter>
    </Provider>
  </StrictMode>
);
```

[Redux Toolkit](https://redux-toolkit.js.org/tutorials/quick-start)

### 19.5 Configurar el AuthSlice

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth 👈👀👇
│   │   │   └── authSlice.js
│   │   └── store.js
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/store/auth/authSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  status: "checking",
  uid: null,
  email: null,
  displayName: null,
  photoURL: null,
  errorMessage: null,
};

export const authSlice = createSlice({
  name: "auth",
  initialState,
  reducers: {
    login: (state, action) => {},
    logout: (state, payload) => {},
    checkingCredentials: (state) => {},
  },
});

export const { login, logout, checkingCredentials } =
  authSlice.actions;
// export default authSlice.reducer;
```

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { authSlice } from "./auth/authSlice";

export const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
  },
});
```

### 19.6 Manejo del formulario de login

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── hooks 👈👀👇
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   ├── authSlice.js
│   │   │   └── thunks.js 👈👀
│   │   └── store.js
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/store/auth/authSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  status: "not-authenticated",
  uid: null,
  email: null,
  displayName: null,
  photoURL: null,
  errorMessage: null,
};

export const authSlice = createSlice({
  name: "auth",
  initialState,
  reducers: {
    login: (state, action) => {},
    logout: (state, payload) => {},
    checkingCredentials: (state) => {
      state.status = "checking";
    },
  },
});

export const { login, logout, checkingCredentials } =
  authSlice.actions;
// export default authSlice.reducer;
```

`src/store/auth/thunks.js`

```js
import { checkingCredentials } from "../store/auth/authSlice";

export const checkingAuthentication = (
  email,
  password
) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};

export const startGoogleSignIn = () => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};
```

`src/hooks/useForm.js`

```js
import { useState } from "react";

export const useForm = (initialForm = {}) => {
  const [formState, setFormState] = useState(initialForm);

  // const { value, name, password } = formState;

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  const handleResetForm = () => {
    setFormState(initialForm);
  };

  return {
    ...formState,
    formState,
    handleInputChange,
    handleResetForm,
  };
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
import { useDispatch } from "react-redux";
import { Link as RouterLink } from "react-router";
import {
  TextField,
  Grid2,
  Button,
  Link,
  Box,
} from "@mui/material";
import { Google } from "@mui/icons-material";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import {
  checkingAuthentication,
  startGoogleSignIn,
} from "../../store/auth/thunks";

export const LoginPage = () => {
  const dispatch = useDispatch();

  const { email, password, handleInputChange } = useForm({
    email: "aleghost@google.com",
    password: "12345",
  });

  const handleSubmit = (event) => {
    event.preventDefault();

    console.log({ email, password });
    dispatch(checkingAuthentication());
  };

  const handleGoogleSignIn = () => {
    console.log("handleGoogleSignIn");

    dispatch(startGoogleSignIn());
  };

  return (
    <AuthLayout title="Login">
      <form action="" onSubmit={handleSubmit}>
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>
        {/* New */}
        <Box>
          <Grid2 container spacing={2} sx={{ mt: 2 }}>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                type="submit"
                variant="contained"
                fullWidth
              >
                Login
              </Button>
            </Grid2>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                variant="contained"
                fullWidth
                startIcon={<Google />}
                onClick={handleGoogleSignIn}
              >
                Google
              </Button>
            </Grid2>
          </Grid2>
          <Grid2
            container
            // direction="row"
            justifyContent="end"
            sx={{ mt: 2 }}
          >
            <Link
              component={RouterLink}
              color="inherit"
              to="/auth/register"
            >
              Create an account.
            </Link>
          </Grid2>
        </Box>
      </form>
    </AuthLayout>
  );
};
```

[Custom Hook: useForm](https://github.com/aleroses/custom-hooks/blob/master/useForm/useForm.js)

### 19.7 Configuración inicial de Firebase

Firebase, es una plataforma integral de desarrollo de aplicaciones móviles y web creada por Google. Ofrece una amplia gama de servicios que permiten a los desarrolladores construir, desplegar y escalar aplicaciones de manera eficiente, sin necesidad de gestionar infraestructuras complejas.

#### Características principales de Firebase

- **Bases de datos en tiempo real y escalables**: Incluye Firebase Realtime Database (no relacional) y Cloud Firestore, que permiten almacenar y sincronizar datos en tiempo real entre los clientes y la nube, facilitando experiencias colaborativas y reactivas. ([Firebase Realtime Database - Google](https://firebase.google.com/docs/database?hl=es-419&utm_source=chatgpt.com))
    
- **Data Connect**: Una solución backend como servicio basada en Cloud SQL Postgres, que permite definir modelos de datos mediante esquemas GraphQL. Proporciona endpoints seguros y SDKs tipados automáticamente, simplificando el desarrollo de aplicaciones complejas. ([What's new in Firebase at Cloud Next 2025](https://firebase.blog/posts/2025/04/cloud-next-announcements/?utm_source=chatgpt.com))
    
- **Firebase Studio**: Lanzado en 2025, es un entorno de desarrollo basado en la web que integra la infraestructura de Firebase con modelos de inteligencia artificial de Gemini. Permite a los usuarios diseñar, construir, probar y lanzar aplicaciones directamente desde el navegador, incluso sin conocimientos técnicos. ([Así funciona Firebase Studio, la plataforma de Google que crea ...](https://es.gizmodo.com/asi-funciona-firebase-studio-la-plataforma-de-google-que-crea-apps-con-solo-describirlas-2000159854?utm_source=chatgpt.com))
    
- **Servicios adicionales**: Firebase también ofrece autenticación de usuarios, funciones en la nube (Cloud Functions), mensajería push (Cloud Messaging), análisis de uso (Analytics), pruebas A/B (Remote Config) y monitoreo de rendimiento, entre otros. ([¿Qué es Firebase y Para qué Sirve? Conviértete en un Experto](https://imaginaformacion.com/tutoriales/que-es-firebase?utm_source=chatgpt.com))

#### Crear proyecto en Firebase

- Go to Console
- Crear un nuevo proyecto
- Nombre: **journalApp**
- Continuar
- Quitar Gemini y Google Analytics
- Crear proyecto
- Icono `</>` web
- **journalApp**
- Registrar App
- Instalar Firebase

	```bash
	npm install firebase
	yarn add firebase
	```

- Copiar la configuración

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── firebase 👈👀
│   │   └── config.js
│   ├── hooks
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   ├── authSlice.js
│   │   │   └── thunks.js
│   │   └── store.js
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/firebase/config.js`

```js
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth"; 👈👀
import { getFirestore } from "firebase/firestore/lite";

// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: "AIzaSyClS8Dtp-O686mpBJW6-4EwgwASeKqFLMw",
  authDomain: "journalapp-72f2d.firebaseapp.com",
  projectId: "journalapp-72f2d",
  storageBucket: "journalapp-72f2d.firebasestorage.app",
  messagingSenderId: "339972861287",
  appId: "1:339972861287:web:4ac56da1de5f56a6bc53c2",
};

// Initialize Firebase 👈👀👇
export const FirebaseApp = initializeApp(firebaseConfig);
// Autenticación 👀👇
export const FirebaseAuth = getAuth(FirebaseApp);
// Configuración de la BD
export const FirebaseDB = getFirestore(FirebaseApp);
```

- [Firebase: Go to console](https://firebase.google.com/)
- [Firebase: Docs](https://firebase.google.com/docs/web/modular-upgrade)

### 19.8 Google SignIn - Firebase

Dentro de Firebase:

- Autentication
- Comenzar
- Proveedor: Correo / Contraseña
- Habilitar: Correo electrónico / Contraseña
- Guardar

- Agregar proveedor nuevo
- Google
- Habilitar Google y añadir correo de referencia
- Guardar

En la documentación puedes buscar **Google signin**
- Authenticate Using Google with JavaScript | Firebase Authentication

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── firebase
│   │   ├── config.js
│   │   └── providers.js 👈👀
│   ├── hooks
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   └── authSlice.js
│   │   └── store.js
│   ├── styles.css
│   └── theme
│       ├── purpleTheme.js
│       └── Theme.jsx
├── vite.config.js
└── yarn.lock
```

`src/firebase/providers.js`

```js
import {
  GoogleAuthProvider,
  signInWithPopup,
} from "firebase/auth";
import { FirebaseAuth } from "./config";

const googleProvider = new GoogleAuthProvider();

export const singInWithGoogle = async () => {
  try {
    const result = await signInWithPopup(
      FirebaseAuth,
      googleProvider
    );
    // const credential = GoogleAuthProvider.credentialFromResult(result);

    const { displayName, email, photoURL, uid } =
      result.user;
    // console.log(user);

    // console.log({ credential });

    return {
      ok: true,
      // User info
      displayName,
      email,
      photoURL,
      uid,
    };
  } catch (error) {
    // Handle Errors here.
    const errorCode = error.code;
    const errorMessage = error.message;

    // console.log(e);
    return {
      ok: false,
      errorMessage,
    };
  }
};
```

`src/store/auth/thunks.js`

```js
import { singInWithGoogle } from "../firebase/providers";
import { checkingCredentials } from "../store/auth/authSlice";

export const checkingAuthentication = (
  email,
  password
) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};

export const startGoogleSignIn = () => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await singInWithGoogle();

    console.log({ result });
  };
};
```

Actualmente, aparecen una serie de errores. En este caso no les daré solución, ya que leí un comentario que dice que a pesar de estos errores todo sigue funcionando con normalidad.  
  
![](https://files.cdn.thinkific.com/file_uploads/643563/images/31b/1f0/78a/1745677882761.png)

- [Firebase Docs](https://firebase.google.com/docs)
- [Authenticate Using Google with JavaScript](https://firebase.google.com/docs/auth/web/google-signin)

### 19.9 Disparar acción de autenticación

`src/store/auth/thunks.js`

```js
import { singInWithGoogle } from "../firebase/providers";
import {
  checkingCredentials,
  login,
  logout,
} from "../store/auth/authSlice";

export const checkingAuthentication = (
  email,
  password
) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};

export const startGoogleSignIn = () => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await singInWithGoogle();

    // console.log({ result });

    if (!result.ok)
      return dispatch(logout(result.errorMessage));

    dispatch(login(result));
  };
};
```

`src/store/auth/authSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  status: "not-authenticated",
  uid: null,
  email: null,
  displayName: null,
  photoURL: null,
  errorMessage: null,
};

export const authSlice = createSlice({
  name: "auth",
  initialState,
  reducers: {
    login: (state, { payload }) => {
      state.status = "authenticated";
      state.uid = payload.uid;
      state.email = payload.email;
      state.displayName = payload.displayName;
      state.photoURL = payload.photoURL;
      state.errorMessage = null;
    },
    logout: (state, { payload }) => {
      state.status = "not-authenticated";
      state.uid = null;
      state.email = null;
      state.displayName = null;
      state.photoURL = null;
      state.errorMessage = payload.errorMessage;
    },
    checkingCredentials: (state) => {
      state.status = "checking";
    },
  },
});

export const { login, logout, checkingCredentials } =
  authSlice.actions;
// export default authSlice.reducer;
```

`src/auth/pages/LoginPage.jsx`

```jsx
import { useMemo } from "react";
import { useDispatch, useSelector } from "react-redux";
import { Link as RouterLink } from "react-router";
import {
  TextField,
  Grid2,
  Button,
  Link,
  Box,
} from "@mui/material";
import { Google } from "@mui/icons-material";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import {
  checkingAuthentication,
  startGoogleSignIn,
} from "../../store/auth/thunks";

export const LoginPage = () => {
  const { status } = useSelector((state) => state.auth);

  const dispatch = useDispatch();

  const { email, password, handleInputChange } = useForm({
    email: "aleghost@google.com",
    password: "12345",
  });

  const isAuthenticating = useMemo(
    () => status === "checking",
    [status]
  );

  // const { status } = useSelector((state) => state.auth);

  // console.log(email, password);

  const handleSubmit = (event) => {
    event.preventDefault();

    console.log({ email, password });
    dispatch(checkingAuthentication());
  };

  const handleGoogleSignIn = () => {
    console.log("handleGoogleSignIn");

    dispatch(startGoogleSignIn());
  };

  // useEffect(() => {
  //   dispatch(checkingAuthentication());
  // }, []);

  return (
    <AuthLayout title="Login">
      <form action="" onSubmit={handleSubmit}>
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>
        {/* New */}
        <Box>
          <Grid2 container spacing={2} sx={{ mt: 2 }}>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                type="submit"
                variant="contained"
                fullWidth
              >
                Login
              </Button>
            </Grid2>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                variant="contained"
                fullWidth
                startIcon={<Google />}
                onClick={handleGoogleSignIn}
              >
                Google
              </Button>
            </Grid2>
          </Grid2>
          <Grid2
            container
            // direction="row"
            justifyContent="end"
            sx={{ mt: 2 }}
          >
            <Link
              component={RouterLink}
              color="inherit"
              to="/auth/register"
            >
              Create an account.
            </Link>
          </Grid2>
        </Box>
      </form>
    </AuthLayout>
  );
};
```

Revisa en Authentication debe aparecer el email usado en las pruebas.

### 19.10 Formulario de registro de usuarios

`src/auth/pages/RegisterPage.jsx`

```jsx
import {
  Button,
  Grid2,
  TextField,
  Link,
  Typography,
} from "@mui/material";
import { AuthLayout } from "../layout/AuthLayout";
import { Link as RouterLink } from "react-router";
import { useForm } from "../../hooks/useForm";

const formData = {
  email: "aleghost@google.com",
  password: "123456",
  displayName: "Ale Ghost",
};

export const RegisterPage = () => {
  const {
    displayName,
    email,
    password,
    handleInputChange,
    formState,
  } = useForm(formData);

  const onSubmit = (event) => {
    event.preventDefault();
    console.log(formState);
  };

  return (
    <AuthLayout title="Register">
      <form action="" onSubmit={onSubmit}>
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="fullname"
              label="Full name"
              type="text"
              placeholder="Your full name"
              size="small"
              fullWidth
              name="displayName"
              value={displayName}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>

        {/* New */}
        <Grid2 container spacing={2} sx={{ mt: 2 }}>
          <Grid2 size={{ xs: 12 }}>
            <Button
              type="submit"
              variant="contained"
              fullWidth
            >
              Create account
            </Button>
          </Grid2>
        </Grid2>
        <Grid2
          container
          justifyContent="end"
          sx={{ mt: 2 }}
        >
          <Typography sx={{ mr: 1 }}>
            Already have an account?
          </Typography>
          <Link
            component={RouterLink}
            color="inherit"
            to="/auth/login"
          >
            Login
          </Link>
        </Grid2>
      </form>
    </AuthLayout>
  );
};
```

- [React Hook Form](https://www.react-hook-form.com/)
- [Formik](https://formik.org/)

### 19.11 Manejo de errores del formulario

`src/auth/pages/RegisterPage.jsx`

```jsx
import {
  Button,
  Grid2,
  TextField,
  Link,
  Typography,
} from "@mui/material";
import { AuthLayout } from "../layout/AuthLayout";
import { Link as RouterLink } from "react-router";
import { useForm } from "../../hooks/useForm";

const formData = {
  email: "aleghost@google.com",
  password: "123456",
  displayName: "Ale Ghost",
};

const formValidations = {
  email: [
    (value) => value.includes("@"),
    "The mail must have an @",
  ],
  password: [
    (value) => value.length >= 6,
    "The password must be longer than 6 letters",
  ],
  displayName: [
    (value) => value.length >= 1,
    "The name is mandatory",
  ],
};

export const RegisterPage = () => {
  const {
    formState,
    displayName,
    email,
    password,
    handleInputChange,
    isFormValid,
    displayNameValid,
    emailValid,
    passwordValid,
  } = useForm(formData, formValidations);

  const onSubmit = (event) => {
    event.preventDefault();
    console.log(formState);
  };

  return (
    <AuthLayout title="Register">
      <form action="" onSubmit={onSubmit}>
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="fullname"
              label="Full name"
              type="text"
              placeholder="Your full name"
              size="small"
              fullWidth
              name="displayName"
              value={displayName}
              onChange={handleInputChange}
              error={!displayNameValid}
              helperText={displayNameValid}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>

        {/* New */}
        <Grid2 container spacing={2} sx={{ mt: 2 }}>
          <Grid2 size={{ xs: 12 }}>
            <Button
              type="submit"
              variant="contained"
              fullWidth
            >
              Create account
            </Button>
          </Grid2>
        </Grid2>
        <Grid2
          container
          justifyContent="end"
          sx={{ mt: 2 }}
        >
          <Typography sx={{ mr: 1 }}>
            Already have an account?
          </Typography>
          <Link
            component={RouterLink}
            color="inherit"
            to="/auth/login"
          >
            Login
          </Link>
        </Grid2>
      </form>
    </AuthLayout>
  );
};
```

`src/hooks/useForm.js`

```js
import { useState } from "react";

export const useForm = (
  initialForm = {},
  formValidations = {}
) => {
  const [formState, setFormState] = useState(initialForm);

  // const { value, name, password } = formState;

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  const handleResetForm = () => {
    setFormState(initialForm);
  };

  return {
    ...formState,
    formState,
    handleInputChange,
    handleResetForm,
  };
};
```

[Validator](https://www.npmjs.com/package/validator)

### 19.12 Validar desde nuestro custom hook

`src/auth/pages/RegisterPage.jsx`

```jsx
import {
  Button,
  Grid2,
  TextField,
  Link,
  Typography,
} from "@mui/material";
import { AuthLayout } from "../layout/AuthLayout";
import { Link as RouterLink } from "react-router";
import { useForm } from "../../hooks/useForm";

const formData = {
  email: "aleghost@google.com",
  password: "123456",
  displayName: "Ale Ghost",
};

const formValidations = {
  email: [
    (value) => value.includes("@"),
    "The mail must have an @",
  ],
  password: [
    (value) => value.length >= 6,
    "The password must be longer than 6 letters",
  ],
  displayName: [
    (value) => value.length >= 1,
    "The name is mandatory",
  ],
};

export const RegisterPage = () => {
  const {
    formState,
    displayName,
    email,
    password,
    handleInputChange,
    isFormValid,
    displayNameValid,
    emailValid,
    passwordValid,
  } = useForm(formData, formValidations);

  console.log(displayNameValid);

  const onSubmit = (event) => {
    event.preventDefault();
    console.log(formState);
  };

  return (
    <AuthLayout title="Register">
      <form action="" onSubmit={onSubmit}>
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="fullname"
              label="Full name"
              type="text"
              placeholder="Your full name"
              size="small"
              fullWidth
              name="displayName"
              value={displayName}
              onChange={handleInputChange}
              error={!displayNameValid}
              helperText={displayNameValid}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>

        {/* New */}
        <Grid2 container spacing={2} sx={{ mt: 2 }}>
          <Grid2 size={{ xs: 12 }}>
            <Button
              type="submit"
              variant="contained"
              fullWidth
            >
              Create account
            </Button>
          </Grid2>
        </Grid2>
        <Grid2
          container
          justifyContent="end"
          sx={{ mt: 2 }}
        >
          <Typography sx={{ mr: 1 }}>
            Already have an account?
          </Typography>
          <Link
            component={RouterLink}
            color="inherit"
            to="/auth/login"
          >
            Login
          </Link>
        </Grid2>
      </form>
    </AuthLayout>
  );
};
```

`src/hooks/useForm.js`

```js
import { useEffect, useState } from "react";

export const useForm = (
  initialForm = {},
  formValidations = {}
) => {
  const [formState, setFormState] = useState(initialForm);
  const [formValidation, setFormValidation] = useState(
    {}
  );

  // const { value, name, password } = formState;

  useEffect(() => {
    createValidators();
  }, [formState]);

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  const handleResetForm = () => {
    setFormState(initialForm);
  };

  const createValidators = () => {
    const formCheckedValues = {};

    for (const formField of Object.keys(formValidations)) {
      const [
        fn,
        errorMessage, //= "This field is required",
      ] = formValidations[formField];

      formCheckedValues[`${formField }Valid`] = fn(
        formState[formField]
      )
        ? null
        : errorMessage;
    }

    setFormValidation(formCheckedValues);
  };

  return {
    ...formState,
    formState,
    handleInputChange,
    handleResetForm,
    ...formValidation,
  };
};
```

### 19.13 Mostrar errores en pantalla

`src/auth/pages/RegisterPage.jsx`

```jsx
import { useState } from "react";
import {
  Button,
  Grid2,
  TextField,
  Link,
  Typography,
} from "@mui/material";
import { Link as RouterLink } from "react-router";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";

const formData = {
  email: "aleghost@google.com",
  password: "123456",
  displayName: "Ale Ghost",
};

const formValidations = {
  email: [
    (value) => value.includes("@"),
    "The mail must have an @",
  ],
  password: [
    (value) => value.length >= 6,
    "The password must be longer than 6 letters",
  ],
  displayName: [
    (value) => value.length >= 1,
    "The name is mandatory",
  ],
};

export const RegisterPage = () => {
  const [formSubmitted, setFormSubmitted] =
    useState(false);

  const {
    formState,
    displayName,
    email,
    password,
    handleInputChange,
    isFormValid,
    displayNameValid,
    emailValid,
    passwordValid,
  } = useForm(formData, formValidations);

  const onSubmit = (event) => {
    event.preventDefault();

    setFormSubmitted(true);

    console.log(formState);
  };

  return (
    <AuthLayout title="Register">
      {/* <h1>Form: {isFormValid ? "Valid" : "Incorrect"}</h1> */}
      <form action="" onSubmit={onSubmit}>
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="fullname"
              label="Full name"
              type="text"
              placeholder="Your full name"
              size="small"
              fullWidth
              name="displayName"
              value={displayName}
              error={!!displayNameValid && formSubmitted}
              helperText={displayNameValid}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              error={!!emailValid && formSubmitted}
              helperText={emailValid}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              error={!!passwordValid && formSubmitted}
              helperText={passwordValid}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>

        {/* New */}
        <Grid2 container spacing={2} sx={{ mt: 2 }}>
          <Grid2 size={{ xs: 12 }}>
            <Button
              type="submit"
              variant="contained"
              fullWidth
            >
              Create account
            </Button>
          </Grid2>
        </Grid2>
        <Grid2
          container
          justifyContent="end"
          sx={{ mt: 2 }}
        >
          <Typography sx={{ mr: 1 }}>
            Already have an account?
          </Typography>
          <Link
            component={RouterLink}
            color="inherit"
            to="/auth/login"
          >
            Login
          </Link>
        </Grid2>
      </form>
    </AuthLayout>
  );
};
```

`src/hooks/useForm.js`

```js
import { useEffect, useMemo, useState } from "react";

export const useForm = (
  initialForm = {},
  formValidations = {}
) => {
  const [formState, setFormState] = useState(initialForm);
  const [formValidation, setFormValidation] = useState(
    {}
  );

  // const { value, name, password } = formState;

  useEffect(() => {
    createValidators();
  }, [formState]);

  const isFormValid = useMemo(() => {
    for (const formValue of Object.keys(formValidation)) {
      if (formValidation[formValue] !== null)
        return false;
    }

    return true;
  }, [formValidation]);

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  const handleResetForm = () => {
    setFormState(initialForm);
  };

  const createValidators = () => {
    const formCheckedValues = {};

    for (const formField of Object.keys(
      formValidations
    )) {
      // xd = fn
      const [
        fn,
        errorMessage, //= "This field is required",
      ] = formValidations[formField];

      formCheckedValues[`${formField}Valid`] = fn(
        formState[formField]
      )
        ? null
        : errorMessage;
    }

    setFormValidation(formCheckedValues);
  };

  return {
    ...formState,
    formState,
    handleInputChange,
    handleResetForm,
    ...formValidation,
    isFormValid,
  };
};
```

### 19.14 Crear usuario con email y password

`src/firebase/providers.js`

```js
import {
  createUserWithEmailAndPassword,
  GoogleAuthProvider,
  signInWithPopup,
} from "firebase/auth";
import { FirebaseAuth } from "./config";

const googleProvider = new GoogleAuthProvider();

export const singInWithGoogle = async () => {
  try {
    const result = await signInWithPopup(
      FirebaseAuth,
      googleProvider
    );
    // const credential = GoogleAuthProvider.credentialFromResult(result);

    const { displayName, email, photoURL, uid } =
      result.user;
    // console.log(user);

    // console.log({ credential });

    return {
      ok: true,
      // User info
      displayName,
      email,
      photoURL,
      uid,
    };
  } catch (error) {
    // Handle Errors here.
    const errorCode = error.code;
    const errorMessage = error.message;

    // console.log(e);
    return {
      ok: false,
      errorMessage,
    };
  }
};

export const registerUserWithEmailPassword = async ({
  email,
  password,
  displayName,
}) => {
  try {
    const resp = await createUserWithEmailAndPassword(
      FirebaseAuth,
      email,
      password
    );

    const { uid, photoURL } = resp.user;

    console.log(resp);
    // TODO: update displayName in Firebase

    return {
      ok: true,
      uid,
      photoURL,
      email,
      displayName,
    };
  } catch (error) {
    console.log(error);

    return { ok: false, errorMessage: error.message };
  }
};
```

`src/store/auth/thunks.js`

```js
import {
  singInWithGoogle,
  registerUserWithEmailPassword,
} from "../firebase/providers";
import {
  checkingCredentials,
  login,
  logout,
} from "../store/auth/authSlice";

export const checkingAuthentication = (
  email,
  password
) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};

export const startGoogleSignIn = () => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await singInWithGoogle();

    // console.log({ result });

    if (!result.ok)
      return dispatch(logout(result.errorMessage));

    dispatch(login(result));
  };
};

export const startCreatingUserWithEmailPassword = ({
  email,
  password,
  displayName,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const resp = await registerUserWithEmailPassword({
      email,
      password,
      displayName,
    });

    console.log(resp);
  };
};
```

`src/auth/pages/RegisterPage.jsx`

```jsx
import { useState } from "react";
import {
  Button,
  Grid2,
  TextField,
  Link,
  Typography,
} from "@mui/material";
import { Link as RouterLink } from "react-router";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import { useDispatch } from "react-redux";
import { startCreatingUserWithEmailPassword } from "../thunks";

const formData = {
  email: "aleghost@google.com",
  password: "123456",
  displayName: "Ale Ghost",
};

const formValidations = {
  email: [
    (value) => value.includes("@"),
    "The mail must have an @",
  ],
  password: [
    (value) => value.length >= 6,
    "The password must be longer than 6 letters",
  ],
  displayName: [
    (value) => value.length >= 1,
    "The name is mandatory",
  ],
};

export const RegisterPage = () => {
  const dispatch = useDispatch();

  const [formSubmitted, setFormSubmitted] =
    useState(false);

  const {
    formState,
    displayName,
    email,
    password,
    handleInputChange,
    isFormValid,
    displayNameValid,
    emailValid,
    passwordValid,
  } = useForm(formData, formValidations);

  const onSubmit = (event) => {
    event.preventDefault();

    setFormSubmitted(true);

    if (!isFormValid) return;

    dispatch(
      startCreatingUserWithEmailPassword(formState)
    );
  };

  return (
    <AuthLayout title="Register">
      {/* <h1>Form: {isFormValid ? "Valid" : "Incorrect"}</h1> */}
      <form action="" onSubmit={onSubmit}>
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="fullname"
              label="Full name"
              type="text"
              placeholder="Your full name"
              size="small"
              fullWidth
              name="displayName"
              value={displayName}
              error={!!displayNameValid && formSubmitted}
              helperText={displayNameValid}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              error={!!emailValid && formSubmitted}
              helperText={emailValid}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              error={!!passwordValid && formSubmitted}
              helperText={passwordValid}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>

        {/* New */}
        <Grid2 container spacing={2} sx={{ mt: 2 }}>
          <Grid2 size={{ xs: 12 }}>
            <Button
              type="submit"
              variant="contained"
              fullWidth
            >
              Create account
            </Button>
          </Grid2>
        </Grid2>
        <Grid2
          container
          justifyContent="end"
          sx={{ mt: 2 }}
        >
          <Typography sx={{ mr: 1 }}>
            Already have an account?
          </Typography>
          <Link
            component={RouterLink}
            color="inherit"
            to="/auth/login"
          >
            Login
          </Link>
        </Grid2>
      </form>
    </AuthLayout>
  );
};
```

📌 Borramos los registros de pruebas.

[En Firebase: ver emails registrados](https://console.firebase.google.com/u/0/project/journalapp-72f2d/authentication/users)

### 19.15 Actualizar el displayName y autenticar el usuario

`src/firebase/providers.js`

```js
import {
  createUserWithEmailAndPassword,
  GoogleAuthProvider,
  signInWithPopup,
  updateProfile,
} from "firebase/auth";
import { FirebaseAuth } from "./config";

const googleProvider = new GoogleAuthProvider();

export const singInWithGoogle = async () => {
  try {
    const result = await signInWithPopup(
      FirebaseAuth,
      googleProvider
    );
    // const credential = GoogleAuthProvider.credentialFromResult(result);

    const { displayName, email, photoURL, uid } =
      result.user;
    // console.log(user);

    // console.log({ credential });

    return {
      ok: true,
      // User info
      displayName,
      email,
      photoURL,
      uid,
    };
  } catch (error) {
    // Handle Errors here.
    const errorCode = error.code;
    const errorMessage = error.message;

    // console.log(e);
    return {
      ok: false,
      errorMessage,
    };
  }
};

export const registerUserWithEmailPassword = async ({
  email,
  password,
  displayName,
}) => {
  try {
    const resp = await createUserWithEmailAndPassword(
      FirebaseAuth,
      email,
      password
    );

    const { uid, photoURL } = resp.user;

    // TODO: update displayName in Firebase
    await updateProfile(FirebaseAuth.currentUser, {
      displayName,
    });

    return {
      ok: true,
      uid,
      photoURL,
      email,
      displayName,
    };
  } catch (error) {
    console.log(error);

    return { ok: false, errorMessage: error.message };
  }
};
```

`src/store/auth/thunks.js`

```js
import {
  singInWithGoogle,
  registerUserWithEmailPassword,
} from "../../firebase/providers";
import {
  checkingCredentials,
  login,
  logout,
} from "./authSlice";

export const checkingAuthentication = (
  email,
  password
) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};

export const startGoogleSignIn = () => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await singInWithGoogle();

    // console.log({ result });

    if (!result.ok)
      return dispatch(logout(result.errorMessage));

    dispatch(login(result));
  };
};

export const startCreatingUserWithEmailPassword = ({
  email,
  password,
  displayName,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const { ok, uid, photoURL, errorMessage } =
      await registerUserWithEmailPassword({
        email,
        password,
        displayName,
      });

    if (!ok) return dispatch(logout({ errorMessage }));

    dispatch(
      login({ uid, displayName, email, photoURL })
    );
  };
};
```

### 19.16 Mostrar el mensaje de error de autenticación

`src/auth/pages/RegisterPage.jsx`

```jsx
import { useMemo, useState } from "react";
import {
  Button,
  Grid2,
  TextField,
  Link,
  Typography,
  Alert,
} from "@mui/material";
import { Link as RouterLink } from "react-router";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import { useDispatch, useSelector } from "react-redux";
import { startCreatingUserWithEmailPassword } from "../../store/auth/thunks.js";

const formData = {
  email: "aleghost@google.com",
  password: "123456",
  displayName: "Ale Ghost",
};

const formValidations = {
  email: [
    (value) => value.includes("@"),
    "The mail must have an @",
  ],
  password: [
    (value) => value.length >= 6,
    "The password must be longer than 6 letters",
  ],
  displayName: [
    (value) => value.length >= 1,
    "The name is mandatory",
  ],
};

export const RegisterPage = () => {
  const dispatch = useDispatch();

  const [formSubmitted, setFormSubmitted] =
    useState(false);

  const { status, errorMessage } = useSelector(
    (state) => state.auth
  );

  const isCheckingAuthentication = useMemo(
    () => status === "checking",
    [status]
  );

  const {
    formState,
    displayName,
    email,
    password,
    handleInputChange,
    isFormValid,
    displayNameValid,
    emailValid,
    passwordValid,
  } = useForm(formData, formValidations);

  const onSubmit = (event) => {
    event.preventDefault();

    setFormSubmitted(true);

    if (!isFormValid) return;

    dispatch(
      startCreatingUserWithEmailPassword(formState)
    );
  };

  return (
    <AuthLayout title="Register">
      {/* <h1>Form: {isFormValid ? "Valid" : "Incorrect"}</h1> */}
      <form action="" onSubmit={onSubmit}>
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="fullname"
              label="Full name"
              type="text"
              placeholder="Your full name"
              size="small"
              fullWidth
              name="displayName"
              value={displayName}
              error={!!displayNameValid && formSubmitted}
              helperText={displayNameValid}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              error={!!emailValid && formSubmitted}
              helperText={emailValid}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              error={!!passwordValid && formSubmitted}
              helperText={passwordValid}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>

        {/* New */}
        <Grid2 container spacing={2} sx={{ mt: 2 }}>
          <Grid2
            size={{ xs: 12 }}
            display={!!errorMessage ? "" : "none"}
          >
            <Alert severity="error">{errorMessage}</Alert>
          </Grid2>
          <Grid2 size={{ xs: 12 }}>
            <Button
              disabled={isCheckingAuthentication}
              type="submit"
              variant="contained"
              fullWidth
            >
              Create account
            </Button>
          </Grid2>
        </Grid2>

        <Grid2
          container
          justifyContent="end"
          sx={{ mt: 2 }}
        >
          <Typography sx={{ mr: 1 }}>
            Already have an account?
          </Typography>
          <Link
            component={RouterLink}
            color="inherit"
            to="/auth/login"
          >
            Login
          </Link>
        </Grid2>
      </form>
    </AuthLayout>
  );
};
```

### 19.17 Realizar el login de usuario con correo y contraseña

La solución en la siguiente clase :/

### 19.18 Resolución de la tarea - Login de usuario

`src/auth/pages/LoginPage.jsx`

```jsx
import { useMemo } from "react";
import { useDispatch, useSelector } from "react-redux";
import { Link as RouterLink } from "react-router";
import {
  TextField,
  Grid2,
  Button,
  Link,
  Box,
  Alert,
} from "@mui/material";
import { Google } from "@mui/icons-material";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import {
  startGoogleSignIn,
  startLoginWithEmailPassword,
} from "../../store/auth/thunks";

export const LoginPage = () => {
  const { status, errorMessage } = useSelector(
    (state) => state.auth
  );

  const dispatch = useDispatch();

  const { email, password, handleInputChange } = useForm({
    email: "",
    password: "",
  });

  const isAuthenticating = useMemo(
    () => status === "checking",
    [status]
  );

  // const { status } = useSelector((state) => state.auth);

  // console.log(email, password);

  const handleSubmit = (event) => {
    event.preventDefault();

    // console.log({ email, password });
    //! This isn't the action to be dispatched
    // dispatch(checkingAuthentication());
    dispatch(
      startLoginWithEmailPassword({ email, password })
    );
  };

  const handleGoogleSignIn = () => {
    console.log("handleGoogleSignIn");

    dispatch(startGoogleSignIn());
  };

  // useEffect(() => {
  //   dispatch(checkingAuthentication());
  // }, []);

  return (
    <AuthLayout title="Login">
      <form action="" onSubmit={handleSubmit}>
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>
        {/* New */}
        <Box>
          <Grid2
            size={{ xs: 12 }}
            display={!!errorMessage ? "" : "none"}
            sx={{
              mt: 1,
            }}
          >
            <Alert severity="error">{errorMessage}</Alert>
          </Grid2>
          <Grid2 container spacing={2} sx={{ mt: 2 }}>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                type="submit"
                variant="contained"
                fullWidth
              >
                Login
              </Button>
            </Grid2>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                variant="contained"
                fullWidth
                startIcon={<Google />}
                onClick={handleGoogleSignIn}
              >
                Google
              </Button>
            </Grid2>
          </Grid2>
          <Grid2
            container
            // direction="row"
            justifyContent="end"
            sx={{ mt: 2 }}
          >
            <Link
              component={RouterLink}
              color="inherit"
              to="/auth/register"
            >
              Create an account.
            </Link>
          </Grid2>
        </Box>
      </form>
    </AuthLayout>
  );
};
```

`src/store/auth/thunks.js`

```js
import {
  singInWithGoogle,
  registerUserWithEmailPassword,
  loginWithEmailPassword,
} from "../../firebase/providers";
import {
  checkingCredentials,
  login,
  logout,
} from "./authSlice";

export const checkingAuthentication = (
  email,
  password
) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};

export const startGoogleSignIn = () => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await singInWithGoogle();

    // console.log({ result });

    if (!result.ok)
      return dispatch(logout(result.errorMessage));

    dispatch(login(result));
  };
};

export const startCreatingUserWithEmailPassword = ({
  email,
  password,
  displayName,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const { ok, uid, photoURL, errorMessage } =
      await registerUserWithEmailPassword({
        email,
        password,
        displayName,
      });

    if (!ok) return dispatch(logout({ errorMessage }));

    dispatch(
      login({ uid, displayName, email, photoURL })
    );
  };
};

export const startLoginWithEmailPassword = ({
  email,
  password,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await loginWithEmailPassword({
      email,
      password,
    });

    if (!result.ok) return dispatch(logout(result));

    dispatch(login(result));
  };
};
```

`src/firebase/providers.js`

```js
import {
  createUserWithEmailAndPassword,
  GoogleAuthProvider,
  signInWithEmailAndPassword,
  signInWithPopup,
  updateProfile,
} from "firebase/auth";
import { FirebaseAuth } from "./config";

const googleProvider = new GoogleAuthProvider();

export const singInWithGoogle = async () => {
  try {
    const result = await signInWithPopup(
      FirebaseAuth,
      googleProvider
    );
    // const credential = GoogleAuthProvider.credentialFromResult(result);

    const { displayName, email, photoURL, uid } =
      result.user;
    // console.log(user);

    // console.log({ credential });

    return {
      ok: true,
      // User info
      displayName,
      email,
      photoURL,
      uid,
    };
  } catch (error) {
    // Handle Errors here.
    const errorCode = error.code;
    const errorMessage = error.message;

    // console.log(e);
    return {
      ok: false,
      errorMessage,
    };
  }
};

export const registerUserWithEmailPassword = async ({
  email,
  password,
  displayName,
}) => {
  try {
    const resp = await createUserWithEmailAndPassword(
      FirebaseAuth,
      email,
      password
    );

    const { uid, photoURL } = resp.user;

    // TODO: update displayName in Firebase
    await updateProfile(FirebaseAuth.currentUser, {
      displayName,
    });

    return {
      ok: true,
      uid,
      photoURL,
      email,
      displayName,
    };
  } catch (error) {
    console.log(error);

    return { ok: false, errorMessage: error.message };
  }
};

export const loginWithEmailPassword = async ({
  email,
  password,
}) => {
  try {
    const resp = await signInWithEmailAndPassword(
      FirebaseAuth,
      email,
      password
    );

    const { uid, photoURL, displayName } = resp.user;

    return {
      ok: true,
      uid,
      photoURL,
      displayName,
    };
  } catch (error) {
    return { ok: false, errorMessage: error.message };
  }
};
```

### 19.19 Checking Authentication

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── firebase
│   │   ├── config.js
│   │   └── providers.js
│   ├── hooks
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   ├── authSlice.js
│   │   │   └── thunks.js
│   │   └── store.js
│   ├── styles.css
│   ├── theme
│   │   ├── purpleTheme.js
│   │   └── Theme.jsx
│   └── ui 👈👀👇
│       └── components
│           └── CheckingAuth.jsx
├── vite.config.js
└── yarn.lock
```

`src/ui/components/CheckingAuth.jsx`

```jsx
import { Box, CircularProgress } from "@mui/material";

export const CheckingAuth = () => {
  return (
    <Box
      component="main"
      sx={{
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        minHeight: "100vh",
        bgcolor: "primary.main",
        // padding: 4,
      }}
    >
      <Box
        component="section"
        sx={{
          width: {
            xs: "80%",
            sm: "60%",
            md: "40%",
            lg: "30%",
          },
          display: "flex",
          justifyContent: "center",
          // bgcolor: "white",
          // padding: { xs: 2, sm: 3, md: 4 },
          // borderRadius: 2,
        }}
      >
        <CircularProgress color="warning" />
      </Box>
    </Box>
  );
};
```

`src/store/auth/authSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  status: "checking",
  uid: null,
  email: null,
  displayName: null,
  photoURL: null,
  errorMessage: null,
};

export const authSlice = createSlice({
  name: "auth",
  initialState,
  reducers: {
    login: (state, { payload }) => {
      state.status = "authenticated";
      state.uid = payload.uid;
      state.email = payload.email;
      state.displayName = payload.displayName;
      state.photoURL = payload.photoURL;
      state.errorMessage = null;
    },
    logout: (state, { payload }) => {
      state.status = "not-authenticated";
      state.uid = null;
      state.email = null;
      state.displayName = null;
      state.photoURL = null;
      state.errorMessage = payload.errorMessage;
    },
    checkingCredentials: (state) => {
      state.status = "checking";
    },
  },
});

export const { login, logout, checkingCredentials } =
  authSlice.actions;
// export default authSlice.reducer;
```

`src/router/AppRouter.jsx`

```jsx
import { Route, Routes } from "react-router";
import { AuthRoutes } from "../auth/routes/AuthRoutes";
import { JournalRoutes } from "../journal/routes/JournalRoutes";
import { useSelector } from "react-redux";
import { CheckingAuth } from "../ui/components/CheckingAuth";

export const AppRouter = () => {
  const { status } = useSelector((state) => state.auth);
  if (status === "checking") {
    return <CheckingAuth />;
  }

  return (
    <Routes>
      {/* Login and Registration */}
      <Route path="auth/*" element={<AuthRoutes />} />

      {/* JournalApp */}
      <Route path="/*" element={<JournalRoutes />} />
    </Routes>
  );
};
```

[MUI Progress](https://mui.com/material-ui/react-progress/)

### 19.20 Mantener el estado de la autenticación al recargar

`src/router/AppRouter.jsx`

```jsx
import { useDispatch, useSelector } from "react-redux";
import { Navigate, Route, Routes } from "react-router";
import { FirebaseAuth } from "../firebase/config";

import { AuthRoutes } from "../auth/routes/AuthRoutes";
import { JournalRoutes } from "../journal/routes/JournalRoutes";
import { CheckingAuth } from "../ui/components/CheckingAuth";
import { useEffect } from "react";
import { onAuthStateChanged } from "firebase/auth";
import { login, logout } from "../store/auth/authSlice";

export const AppRouter = () => {
  const { status } = useSelector((state) => state.auth);
  const dispatch = useDispatch();

  useEffect(() => {
    onAuthStateChanged(FirebaseAuth, async (user) => {
      // console.log(user);

      if (!user) return dispatch(logout());

      const { uid, email, displayName, photoURL } = user;

      dispatch(
        login({ uid, email, displayName, photoURL })
      );
    });
  }, []);

  if (status === "checking") {
    return <CheckingAuth />;
  }

  return (
    <Routes>
      {status === "authenticated" ? (
        <Route path="/*" element={<JournalRoutes />} />
      ) : (
        <Route path="auth/*" element={<AuthRoutes />} />
      )}

      <Route
        path="/*"
        element={<Navigate to="/auth/login" />}
      />

      {/* Login and Registration */}
      {/* <Route path="auth/*" element={<AuthRoutes />} /> */}

      {/* JournalApp */}
      {/* <Route path="/*" element={<JournalRoutes />} /> */}
    </Routes>
  );
};
```

### 19.21 Custom Hook para autenticación

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── firebase
│   │   ├── config.js
│   │   └── providers.js
│   ├── hooks
│   │   ├── useCheckAuth.js 👈👀
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   ├── authSlice.js
│   │   │   └── thunks.js
│   │   └── store.js
│   ├── styles.css
│   ├── theme
│   │   ├── purpleTheme.js
│   │   └── Theme.jsx
│   └── ui
│       └── components
│           └── CheckingAuth.jsx
├── vite.config.js
└── yarn.lock
```

`src/router/AppRouter.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";

import { AuthRoutes } from "../auth/routes/AuthRoutes";
import { JournalRoutes } from "../journal/routes/JournalRoutes";
import { CheckingAuth } from "../ui/components/CheckingAuth";
import { useCheckAuth } from "../hooks/useCheckAuth";

export const AppRouter = () => {
  const status = useCheckAuth();

  // const { status } = useSelector((state) => state.auth);
  // const dispatch = useDispatch();

  // useEffect(() => {
  //   onAuthStateChanged(FirebaseAuth, async (user) => {
  //     // console.log(user);

  //     if (!user) return dispatch(logout());

  //     const { uid, email, displayName, photoURL } = user;

  //     dispatch(
  //       login({ uid, email, displayName, photoURL })
  //     );
  //   });
  // }, []);

  if (status === "checking") {
    return <CheckingAuth />;
  }

  return (
    <Routes>
      {status === "authenticated" ? (
        <Route path="/*" element={<JournalRoutes />} />
      ) : (
        <Route path="auth/*" element={<AuthRoutes />} />
      )}

      <Route
        path="/*"
        element={<Navigate to="/auth/login" />}
      />

      {/* Login and Registration */}
      {/* <Route path="auth/*" element={<AuthRoutes />} /> */}

      {/* JournalApp */}
      {/* <Route path="/*" element={<JournalRoutes />} /> */}
    </Routes>
  );
};
```

`src/hooks/useCheckAuth.js`

```js
import { useEffect } from "react";
import { useDispatch, useSelector } from "react-redux";
import { onAuthStateChanged } from "firebase/auth";
import { login, logout } from "../store/auth/authSlice";
import { FirebaseAuth } from "../firebase/config";

export const useCheckAuth = () => {
  const { status } = useSelector((state) => state.auth);
  const dispatch = useDispatch();

  useEffect(() => {
    onAuthStateChanged(FirebaseAuth, async (user) => {
      // console.log(user);

      if (!user) return dispatch(logout());

      const { uid, email, displayName, photoURL } = user;

      dispatch(
        login({ uid, email, displayName, photoURL })
      );
    });
  }, []);

  return status;
};
```

### 19.22 Logout de Firebase

`src/journal/components/NavBar.jsx`

```jsx
import {
  LogoutOutlined,
  MenuOutlined,
} from "@mui/icons-material";
import {
  AppBar,
  Toolbar,
  IconButton,
  Typography,
} from "@mui/material";
import { useState } from "react";
import { useDispatch } from "react-redux";
import { startLogout } from "../../store/auth/thunks";

export const NavBar = ({ drawerWidth = 240 }) => {
  const [open, setOpen] = useState(false);

  const dispatch = useDispatch();

  const onLogout = () => {
    dispatch(startLogout());
  };

  return (
    <>
      <AppBar
        // position="static"
        sx={{
          width: { sm: `calc(100% - ${drawerWidth}px)` },
          ml: { sm: `${drawerWidth}px` },
        }}
      >
        <Toolbar>
          <IconButton
            aria-label=""
            onClick={() => setOpen(true)}
            color="inherit"
            edge="start"
            sx={{
              display: { xs: "flex", sm: "none" },
              mr: 2,
            }}
          >
            <MenuOutlined />
          </IconButton>

          <Typography
            variant="h6"
            // noWrap
            component="span"
            sx={{ flexGrow: 1 }}
          >
            JournalApp
          </Typography>

          <IconButton
            aria-label=""
            color="error"
            onClick={onLogout}
          >
            <LogoutOutlined />
          </IconButton>
        </Toolbar>
      </AppBar>
    </>
  );
};
```

`src/store/auth/thunks.js`

```js
import {
  singInWithGoogle,
  registerUserWithEmailPassword,
  loginWithEmailPassword,
  logoutFirebase,
} from "../../firebase/providers";
import {
  checkingCredentials,
  login,
  logout,
} from "./authSlice";

export const checkingAuthentication = (
  email,
  password
) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};

export const startGoogleSignIn = () => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await singInWithGoogle();

    // console.log({ result });

    if (!result.ok)
      return dispatch(logout(result.errorMessage));

    dispatch(login(result));
  };
};

export const startCreatingUserWithEmailPassword = ({
  email,
  password,
  displayName,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const { ok, uid, photoURL, errorMessage } =
      await registerUserWithEmailPassword({
        email,
        password,
        displayName,
      });

    if (!ok) return dispatch(logout({ errorMessage }));

    dispatch(
      login({ uid, displayName, email, photoURL })
    );
  };
};

export const startLoginWithEmailPassword = ({
  email,
  password,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await loginWithEmailPassword({
      email,
      password,
    });

    if (!result.ok) return dispatch(logout(result));

    dispatch(login(result));
  };
};

export const startLogout = () => {
  return async (dispatch) => {
    await logoutFirebase();

    dispatch(logout());
  };
};
```

`src/store/auth/authSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  status: "checking",
  uid: null,
  email: null,
  displayName: null,
  photoURL: null,
  errorMessage: null,
};

export const authSlice = createSlice({
  name: "auth",
  initialState,
  reducers: {
    login: (state, { payload }) => {
      state.status = "authenticated";
      state.uid = payload.uid;
      state.email = payload.email;
      state.displayName = payload.displayName;
      state.photoURL = payload.photoURL;
      state.errorMessage = null;
    },
    logout: (state, { payload }) => {
      state.status = "not-authenticated";
      state.uid = null;
      state.email = null;
      state.displayName = null;
      state.photoURL = null; // 👀👇
      state.errorMessage = payload?.errorMessage;
    },
    checkingCredentials: (state) => {
      state.status = "checking";
    },
  },
});

export const { login, logout, checkingCredentials } =
  authSlice.actions;
// export default authSlice.reducer;
```

`src/firebase/providers.js`

```js
import {
  createUserWithEmailAndPassword,
  GoogleAuthProvider,
  signInWithEmailAndPassword,
  signInWithPopup,
  updateProfile,
} from "firebase/auth";
import { FirebaseAuth } from "./config";

const googleProvider = new GoogleAuthProvider();

export const singInWithGoogle = async () => {
  try {
    const result = await signInWithPopup(
      FirebaseAuth,
      googleProvider
    );
    // const credential = GoogleAuthProvider.credentialFromResult(result);

    const { displayName, email, photoURL, uid } =
      result.user;
    // console.log(user);

    // console.log({ credential });

    return {
      ok: true,
      // User info
      displayName,
      email,
      photoURL,
      uid,
    };
  } catch (error) {
    // Handle Errors here.
    const errorCode = error.code;
    const errorMessage = error.message;

    // console.log(e);
    return {
      ok: false,
      errorMessage,
    };
  }
};

export const registerUserWithEmailPassword = async ({
  email,
  password,
  displayName,
}) => {
  try {
    const resp = await createUserWithEmailAndPassword(
      FirebaseAuth,
      email,
      password
    );

    const { uid, photoURL } = resp.user;

    // TODO: update displayName in Firebase
    await updateProfile(FirebaseAuth.currentUser, {
      displayName,
    });

    return {
      ok: true,
      uid,
      photoURL,
      email,
      displayName,
    };
  } catch (error) {
    console.log(error);

    return { ok: false, errorMessage: error.message };
  }
};

export const loginWithEmailPassword = async ({
  email,
  password,
}) => {
  try {
    const resp = await signInWithEmailAndPassword(
      FirebaseAuth,
      email,
      password
    );

    const { uid, photoURL, displayName } = resp.user;

    return {
      ok: true,
      uid,
      photoURL,
      displayName,
    };
  } catch (error) {
    return { ok: false, errorMessage: error.message };
  }
};

export const logoutFirebase = async () => {
  return await FirebaseAuth.signOut();
};
```

`src/journal/components/SideBar.jsx`

```jsx
import { TurnedInNot } from "@mui/icons-material";
import {
  Box,
  Drawer,
  Typography,
  Toolbar,
  Divider,
  List,
  ListItem,
  ListItemIcon,
  ListItemButton,
  ListItemText,
  Grid2,
} from "@mui/material";
import { useSelector } from "react-redux";

export const SideBar = ({ drawerWidth = 240 }) => {
  const { displayName } = useSelector(
    (state) => state.auth
  );

  return (
    // <Box
    //   component="nav"
    //   sx={{
    //     width: { sm: drawerWidth },
    //     flexShrink: { sm: 0 },
    //   }}
    // >
    <Drawer
      variant="permanent"
      anchor="left"
      open
      sx={{
        width: { sm: drawerWidth },
        flexShrink: { sm: 0 },
        display: { xs: "block" },
        "& .MuiDrawer-paper": {
          boxSizing: "border-box",
          width: drawerWidth,
        },
      }}
    >
      <Toolbar>
        <Typography variant="h6" noWrap component="div">
          {displayName}
        </Typography>
      </Toolbar>
      <Divider />

      <Box component="nav">
        <List>
          {["January", "February", "March", "April"].map(
            (text) => (
              <ListItem key={text} disablePadding>
                <ListItemButton component="a">
                  <ListItemIcon>
                    <TurnedInNot />
                  </ListItemIcon>
                  <Grid2 container>
                    <ListItemText
                      // primary={text}
                      secondary={"Lorem ipsum......"}
                    >
                      {text}
                    </ListItemText>
                  </Grid2>
                </ListItemButton>
              </ListItem>
            )
          )}
        </List>
      </Box>
    </Drawer>
    //* </Box>
  );
};
```

### 19.23 Animaciones para la aplicación

`index.html`

```html
  <head>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
    />

    <title>Journal App</title>
  </head>
```

`src/journal/views/NoteView.jsx`

```jsx
import { SaveOutlined } from "@mui/icons-material";
import {
  Button,
  Grid2,
  Typography,
  TextField,
} from "@mui/material";
import { ImageGallery } from "../components/ImageGallery";

export const NoteView = () => {
  return (
    <>
      <Grid2
        className="animate__animated animate__fadeIn animate__faster"
        container
        justifyContent="space-between"
        alignItems="center"
        sx={{ mb: 1 }}
      >
      </Grid2>
    </>
  );
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
import { useMemo } from "react";
import { useDispatch, useSelector } from "react-redux";
import { Link as RouterLink } from "react-router";
import {
  TextField,
  Grid2,
  Button,
  Link,
  Box,
  Alert,
} from "@mui/material";
import { Google } from "@mui/icons-material";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import {
  startGoogleSignIn,
  startLoginWithEmailPassword,
} from "../../store/auth/thunks";

export const LoginPage = () => {
  const { status, errorMessage } = useSelector(
    (state) => state.auth
  );

  const dispatch = useDispatch();

  const { email, password, handleInputChange } = useForm({
    email: "",
    password: "",
  });

  const isAuthenticating = useMemo(
    () => status === "checking",
    [status]
  );

  // const { status } = useSelector((state) => state.auth);

  // console.log(email, password);

  const handleSubmit = (event) => {
    event.preventDefault();

    // console.log({ email, password });
    //! This isn't the action to be dispatched
    // dispatch(checkingAuthentication());
    dispatch(
      startLoginWithEmailPassword({ email, password })
    );
  };

  const handleGoogleSignIn = () => {
    console.log("handleGoogleSignIn");

    dispatch(startGoogleSignIn());
  };

  // useEffect(() => {
  //   dispatch(checkingAuthentication());
  // }, []);

  return (
    <AuthLayout title="Login">👈👀
      <form
        action=""
        onSubmit={handleSubmit}
        className="animate__animated animate__fadeIn animate__faster"
      >
      </form>
    </AuthLayout>
  );
};
```

`src/auth/pages/RegisterPage.jsx`

```jsx
import { useMemo, useState } from "react";
import {
  Button,
  Grid2,
  TextField,
  Link,
  Typography,
  Alert,
} from "@mui/material";
import { Link as RouterLink } from "react-router";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import { useDispatch, useSelector } from "react-redux";
import { startCreatingUserWithEmailPassword } from "../../store/auth/thunks.js";

const formData = {
  email: "aleghost@google.com",
  password: "123456",
  displayName: "Ale Ghost",
};

const formValidations = {
  email: [
    (value) => value.includes("@"),
    "The mail must have an @",
  ],
  password: [
    (value) => value.length >= 6,
    "The password must be longer than 6 letters",
  ],
  displayName: [
    (value) => value.length >= 1,
    "The name is mandatory",
  ],
};

export const RegisterPage = () => {
  const dispatch = useDispatch();

  const [formSubmitted, setFormSubmitted] =
    useState(false);

  const { status, errorMessage } = useSelector(
    (state) => state.auth
  );

  const isCheckingAuthentication = useMemo(
    () => status === "checking",
    [status]
  );

  const {
    formState,
    displayName,
    email,
    password,
    handleInputChange,
    isFormValid,
    displayNameValid,
    emailValid,
    passwordValid,
  } = useForm(formData, formValidations);

  const onSubmit = (event) => {
    event.preventDefault();

    setFormSubmitted(true);

    if (!isFormValid) return;

    dispatch(
      startCreatingUserWithEmailPassword(formState)
    );
  };

  return (
    <AuthLayout title="Register">
      {/* <h1>Form: {isFormValid ? "Valid" : "Incorrect"}</h1> */}
      <form
        action=""
        onSubmit={onSubmit}
        className="animate__animated animate__fadeIn animate__faster"
      >
      </form>
    </AuthLayout>
  );
};
```

`src/journal/layout/JournalLayout.jsx`

```jsx
import { Box, Toolbar } from "@mui/material";
import { NavBar } from "../components/NavBar";
import { SideBar } from "../components/SideBar";

const drawerWidth = 280;

export const JournalLayout = ({ children }) => {
  return (
    <Box
      sx={{ display: "flex" }}
      className="animate__animated animate__fadeIn animate__faster"
    >
    </Box>
  );
};
```

`src/journal/views/NothingSelectedView.jsx`

```jsx
import { StarOutline } from "@mui/icons-material";
import { Box, Grid2, Typography } from "@mui/material";

export const NothingSelectedView = () => {
  return (
    <Box
      className="animate__animated animate__fadeIn animate__faster"
      component="main"
      sx={{
        minHeight: "calc(100vh - 110px)",
        display: "flex",
        flexDirection: "column",
        justifyContent: "center",
        alignItems: "center",
        bgcolor: "primary.main",
        borderRadius: 5,
      }}
    >
    </Box>
  );
};
```

[Animate Style](https://animate.style/)

### 19.24 Código fuente de la sección

Aquí les dejo el código fuente de la sección por si les interesa revisarlo o utilizarlo como base.

**IMPORTANTE:**

Recuerden cambiar la configuración de firebase, porque yo lo borraré en cualquier momento

[**GitHub - Fin sección 19**](https://github.com/Klerith/react-journal-material/tree/fin-seccion-19)

## 🟣 20. JournalApp - Redux - CRUD en Firestore y subida de archivos

### 20.1 Introducción a la sección

### 20.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- CRUD hacia Firestore
- Expandiendo nuestro store añadiendo otros reducers
- Seleccionar y subir archivos
- Animaciones adicionales a nuestra aplicación
- Limpieza en el logout

Esta sección está enfocada ahora en las entradas de nuestro diario, asegurándose de que grabe únicamente en el documento del usuario autenticado.

### 20.3 Continuación del proyecto - JournalApp

### 20.4 JournalSlice

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── firebase
│   │   ├── config.js
│   │   └── providers.js
│   ├── hooks
│   │   ├── useCheckAuth.js
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   ├── authSlice.js
│   │   │   └── thunks.js
│   │   ├── journal
│   │   │   ├── journalSlice.js 👈👀
│   │   │   └── thunks.js 👈👀
│   │   └── store.js 👈👀
│   ├── styles.css
│   ├── theme
│   │   ├── purpleTheme.js
│   │   └── Theme.jsx
│   └── ui
│       └── components
│           └── CheckingAuth.jsx
├── vite.config.js
└── yarn.lock
```

`src/store/journal/journalSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const journalSlice = createSlice({
  name: "journal",
  initialState: {
    isSaving: true,
    messageSaved: "",
    notes: [],
    active: null,
    // active: {
    //   id: "ABC123",
    //   title: "",
    //   body: "",
    //   date: 1234567,
    //   imageUrls: [],
    // },
  },
  reducers: {
    addNewEmptyNote: (state, { payload }) => {},
    setActiveNote: (state, action) => {},
    setNotes: (state, { payload }) => {},
    setSaving: () => {},
    updateNote: (state, action) => {},
    deleteNoteById: (state, action) => {},
  },
});

export const {
  addNewEmptyNote,
  setActiveNote,
  setNotes,
  setSaving,
  updateNote,
  deleteNoteById,
} = journalSlice.actions;
```

`src/store/journal/thunks.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { authSlice } from "./auth/authSlice";
import { journalSlice } from "./journal/journalSlice";

export const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
    journal: journalSlice.reducer,
  },
});
```

### 20.5 Preparar la base de datos - CloudFirestore

#### 1. Crear base de datos

- Go to console
- journalApp
- Compilación
- Firestore Database
- Crear base de datos
	- Edición Standard: (Siguiente)
	- ID de la base de datos: (default)
	- Ubicación: Buscar ubicación cercana (Siguiente)
	- Configurar: Iniciar en modo de producción 
	- Crear

#### 2. Crear colección inicial

**id-user-1** representa al usuario por su ID único.

- **Iniciar colección**
- **id-user-1** (Siguiente)
- ID de documento: **journal**
- Guardar

#### 3. Agregar campos al documento `journal`

- **Agregar campo**:
	- Campo: numero-notas
	- Tipo: number
	- Valor: 2
	- Agregar

#### 4. Crear colección de notas dentro de `journal`

- **Iniciar colección**:
	- ID de la colección: notes (Siguiente)
	- ID de documento: **ID automático** 👈👀
	- Guardar
- **Agregar campo**:
	- **Campo**: title
		- Tipo: String
		- Valor: Hi world
		- Agregar
	- **Campo**: body
		- Tipo: String
		- Valor: Hi world again
		- Agregar
	- **Campo**: date
		- Tipo: Number
		- Valor: 123456
		- Agregar
- **Agregar documento**
	- ID de documento: **ID automático** 👈👀
	- **Campo**: title
		- Tipo: String
		- Valor: Hi world
		- Agregar

La ruta para acceder a una nota específica es:

```
/id-user-1/journal/notes/S7oYX9sGYZY1O7CXmqaZ
```

```mermaid
flowchart TD
    A[Firestore DB] --> B[id-user-1 : Colección]
    B --> C[journal : Documento]
    C --> D[n-notas = 2: Campo]
    C --> E[notes : Colección]
    E --> F1[Nota 1 : Documento]
    E --> F2[Nota 2 : Documento]
    
    F1 --> G1[title: Hi world]
    F1 --> G2[body: Hi world again]
    F1 --> G3[date: 123456]
    
    F2 --> H1[title: Hi world]
    F2 --> H2[body: Hi world again]
    F2 --> H3[date: 123456]
```

Donde:
- `id-user-1`: Identificador único del usuario. Tendremos muchos de estos.
- `journal`: Vive dentro de id-user-1, cada usuario tiene uno, este documento contiene datos generales del diario.
- `notes`: Vive dentro de journal y es la colección que almacena todas las notas del usuario.
- `s7oYX9sGYZY107CXm1az`: Vive dentro de `notes`, son los metadatos que iteraremos más adelante. Ejemplo: Body, date y título.

```mermaid
flowchart TD
    subgraph Firestore DB
        subgraph id-user-1 [id-user-1 : Colección]
            subgraph journal [journal : Documento]
                D[numero-notas = 2]
                subgraph notes [notes : Colección]
                    subgraph Nota1 [Nota 1 : Documento]
                        G1[title: Hi world]
                        G2[body: Hi world again]
                        G3[date: 123456]
                    end
                    subgraph Nota2 [Nota 2 : Documento]
                        H1[title: Hi world]
                        H2[body: Hi world again]
                        H3[date: 123456]
                    end
                end
            end
        end
    end
```

`src/store/journal/thunks.js`

```js
export const startNewNote = () => {
  return async (dispatch) => {
    // uid

    const newNote = {
      title: "",
      body: "",
      date: new Date().getTime(),
    };

    // dispatch
    // dispatc(newNote)
    // dispatch(activarNote)
  };
};
```

### 20.6 Crear una nueva nota

`Firestore Database / (default) / Reglas`

Esto sirve para dejar pasar las peticiones.

```js
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {  👀👇
      allow read, write: if request.auth != null;
    }
  }
}
```

Darle en `Publicar`

`src/journal/pages/JournalPage.jsx`

```jsx
import { JournalLayout } from "../layout/JournalLayout";
import IconButton from "@mui/material/IconButton";
import { NothingSelectedView } from "../views/NothingSelectedView";
import { AddOutlined } from "@mui/icons-material";
import { startNewNote } from "../../store/journal/thunks";
import { useDispatch } from "react-redux";

export const JournalPage = () => {
  const dispatch = useDispatch(); 👈👀

  const onClickNewNote = () => { 👈👀
    dispatch(startNewNote());
  };

  return (
    <JournalLayout>
      <NothingSelectedView />

      <IconButton
        aria-label=""
        size="large"
        sx={{
          color: "white",
          bgcolor: "error.main",
          ":hover": {
            bgcolor: "error.main",
            opacity: 0.9,
          },
          position: "fixed",
          right: 50,
          bottom: 50,
        }}
        onClick={onClickNewNote} 👈👀
      >
        <AddOutlined sx={{ fontSize: 30 }} />
      </IconButton>
    </JournalLayout>
  );
};
```

`src/store/journal/thunks.js`

```js
import {
  collection,
  doc,
  setDoc,
} from "firebase/firestore/lite";
import { FirebaseDB } from "../../firebase/config";

export const startNewNote = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;
    // uid

    const newNote = {
      title: "",
      body: "",
      date: new Date().getTime(),
    };

    const newDoc = doc(  👈👀👇
      collection(FirebaseDB, `${uid}/journal/notes`)
    );

    // Para ver la info añadir variable y hacer console.log
    await setDoc(newDoc, newNote); 👈👀

    // dispatch
    // dispatc(newNote)
    // dispatch(activarNote)
  };
};
```

Ahora al hacer clic en el botón añadir nota `➕` debe salir algo como esto:

```js
{
  newDoc: {
    converter: null,
    _key: {
      path: {
        segments: [
          "SwqBKmZo3Gg6m4nNDrOvV6oFgCD2",
          "journal",
          "notes",
          "RhnIlpXk25uiOviGjIfa",
        ],
        offset: 0,
        len: 4,
      },
    },
    type: "document",
    firestore: {
      app: {
        _isDeleted: false,
        _options: {
          apiKey: "AIzaSyClS8Dtp-O686mpBJW6-4EwgwASeKqFLMw",
          authDomain: "journalapp-72f2d.firebaseapp.com",
          projectId: "journalapp-72f2d",
          storageBucket:
            "journalapp-72f2d.firebasestorage.app",
          messagingSenderId: "339972861287",
          appId: "1:339972861287:web:4ac56da1de5f56a6bc53c2",
        },
        _config: {
          name: "[DEFAULT]",
          automaticDataCollectionEnabled: false,
        },
        _name: "[DEFAULT]",
        _automaticDataCollectionEnabled: false,
        _container: {
          name: "[DEFAULT]",
          providers: {},
        },
      },
      databaseId: {
        projectId: "journalapp-72f2d",
        database: "(default)",
      },
      settings: {
        host: "firestore.googleapis.com",
        ssl: true,
        ignoreUndefinedProperties: false,
        cacheSizeBytes: 41943040,
        experimentalForceLongPolling: false,
        experimentalAutoDetectLongPolling: true,
        experimentalLongPollingOptions: {},
        useFetchStreams: false,
      },
    },
  },
};
```

- Verificamos dentro de la extensión `Redux/State/uid` debe coincidir con `"SwqBKmZo3Gg6m4nNDrOvV6oFgCD2"`
- Dentro de la BD también debemos tener lo mismo.

### 20.7 Activar la nota creada

`src/store/journal/thunks.js`

```js
import {
  collection,
  doc,
  setDoc,
} from "firebase/firestore/lite";
import { FirebaseDB } from "../../firebase/config";
import {
  addNewEmptyNote,
  savingNewNote,
  setActiveNote,
} from "./journalSlice";

export const startNewNote = () => {
  return async (dispatch, getState) => {
    dispatch(savingNewNote());

    const { uid } = getState().auth;
    // uid

    const newNote = {
      title: "",
      body: "",
      date: new Date().getTime(),
    };

    const newDoc = doc(
      collection(FirebaseDB, `${uid}/journal/notes`)
    );

    // Para ver la info añadir variable y hacer console.log
    await setDoc(newDoc, newNote);

    newNote.id = newDoc.id;

    // dispatch
    dispatch(addNewEmptyNote(newNote));
    dispatch(setActiveNote(newNote));
  };
};
```

`src/store/journal/journalSlice.js`
```js
import { createSlice } from "@reduxjs/toolkit";

export const journalSlice = createSlice({
  name: "journal",
  initialState: {
    isSaving: false,
    messageSaved: "",
    notes: [],
    active: null,
    // active: {
    //   id: "ABC123",
    //   title: "",
    //   body: "",
    //   date: 1234567,
    //   imageUrls: [],
    // },
  },
  reducers: {
    savingNewNote: (state, { payload }) => {
      state.isSaving = true;
    },
    addNewEmptyNote: (state, { payload }) => {
      state.notes.push(payload);
      state.isSaving = false;
    },
    setActiveNote: (state, { payload }) => {
      state.active = payload;
    },
    setNotes: (state, { payload }) => {},
    setSaving: () => {},
    updateNote: (state, action) => {},
    deleteNoteById: (state, action) => {},
  },
});

export const {
  addNewEmptyNote,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setSaving,
  updateNote,
} = journalSlice.actions;
```

`src/journal/pages/JournalPage.jsx`

```jsx
import { JournalLayout } from "../layout/JournalLayout";
import IconButton from "@mui/material/IconButton";
import { NothingSelectedView } from "../views/NothingSelectedView";
import { AddOutlined } from "@mui/icons-material";
import { startNewNote } from "../../store/journal/thunks";
import { useDispatch, useSelector } from "react-redux";
import { NoteView } from "../views/NoteView";

export const JournalPage = () => {
  const dispatch = useDispatch();
  const { isSaving, active } = useSelector(
    (state) => state.journal
  );

  const onClickNewNote = () => {
    dispatch(startNewNote());
  };

  return (
    <JournalLayout>
      {!!active ? <NoteView /> : <NothingSelectedView />}

      <IconButton
        aria-label=""
        size="large"
        disabled={isSaving}
        sx={{
          color: "white",
          bgcolor: "error.main",
          ":hover": {
            bgcolor: "error.main",
            opacity: 0.9,
          },
          position: "fixed",
          right: 50,
          bottom: 50,
        }}
        onClick={onClickNewNote}
      >
        <AddOutlined sx={{ fontSize: 30 }} />
      </IconButton>
    </JournalLayout>
  );
};
```

### 20.8 Cargar notas de Firestore

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── firebase
│   │   ├── config.js
│   │   └── providers.js
│   ├── helpers 👈👀👇
│   │   └── loadNotes.js
│   ├── hooks
│   │   ├── useCheckAuth.js
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   ├── authSlice.js
│   │   │   └── thunks.js
│   │   ├── journal
│   │   │   ├── journalSlice.js
│   │   │   └── thunks.js
│   │   └── store.js
│   ├── styles.css
│   ├── theme
│   │   ├── purpleTheme.js
│   │   └── Theme.jsx
│   └── ui
│       └── components
│           └── CheckingAuth.jsx
├── vite.config.js
└── yarn.lock
```

`src/store/journal/thunks.js`

```js
import {
  collection,
  doc,
  setDoc,
} from "firebase/firestore/lite";
import { FirebaseDB } from "../../firebase/config";
import {
  addNewEmptyNote,
  savingNewNote,
  setActiveNote,
  setNotes,
} from "./journalSlice";
import { loadNotes } from "../../helpers/loadNotes";

export const startNewNote = () => {
  return async (dispatch, getState) => {
    dispatch(savingNewNote());

    const { uid } = getState().auth;
    // uid

    const newNote = {
      title: "",
      body: "",
      date: new Date().getTime(),
    };

    const newDoc = doc(
      collection(FirebaseDB, `${uid}/journal/notes`)
    );

    // Para ver la info añadir variable y hacer console.log
    await setDoc(newDoc, newNote);

    newNote.id = newDoc.id;

    // dispatch
    dispatch(addNewEmptyNote(newNote));
    dispatch(setActiveNote(newNote));
  };
};

export const startLoadingNotes = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;

    if (!uid) throw new Error("The user uid doesn't exist");

    const notes = await loadNotes(uid);

    dispatch(setNotes(notes));
  };
};
```

`src/hooks/useCheckAuth.js`

```js
import { useEffect } from "react";
import { useDispatch, useSelector } from "react-redux";
import { onAuthStateChanged } from "firebase/auth";
import { login, logout } from "../store/auth/authSlice";
import { FirebaseAuth } from "../firebase/config";
import { startLoadingNotes } from "../store/journal/thunks";

export const useCheckAuth = () => {
  const { status } = useSelector((state) => state.auth);
  const dispatch = useDispatch();

  useEffect(() => {
    onAuthStateChanged(FirebaseAuth, async (user) => {
      // console.log(user);

      if (!user) return dispatch(logout());

      const { uid, email, displayName, photoURL } = user;

      dispatch(login({ uid, email, displayName, photoURL }));
      
      // If you place this before dispatch(login({})) it will fail.
      dispatch(startLoadingNotes());
    });
  }, []);

  return status;
};
```

`src/helpers/loadNotes.js`

```js
import { collection, getDocs } from "firebase/firestore/lite";
import { FirebaseDB } from "../firebase/config";

export const loadNotes = async (uid = "") => {
  if (!uid) throw new Error("The user uid doesn't exist");

  const collectionRef = collection(
    FirebaseDB,
    `${uid}/journal/notes`
  );
  const docs = await getDocs(collectionRef);

  const notes = [];

  docs.forEach((doc) => {
    notes.push({ id: doc.id, ...doc.data() });
  });

  return notes;
};
```

`src/store/journal/journalSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const journalSlice = createSlice({
  name: "journal",
  initialState: {
    isSaving: false,
    messageSaved: "",
    notes: [],
    active: null,
    // active: {
    //   id: "ABC123",
    //   title: "",
    //   body: "",
    //   date: 1234567,
    //   imageUrls: [],
    // },
  },
  reducers: {
    savingNewNote: (state, { payload }) => {
      state.isSaving = true;
    },
    addNewEmptyNote: (state, { payload }) => {
      state.notes.push(payload);
      state.isSaving = false;
    },
    setActiveNote: (state, { payload }) => {
      state.active = payload;
    },
    setNotes: (state, { payload }) => {
      state.notes = payload;
    },
    setSaving: () => {},
    updateNote: (state, action) => {},
    deleteNoteById: (state, action) => {},
  },
});

export const {
  addNewEmptyNote,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setSaving,
  updateNote,
} = journalSlice.actions;
```

### 20.9 Mostrar las notas en el menú lateral

En Firestore Database, dentro de **notas**, seleccionamos un ID y añadimos algo de información:

```json
body: ✏️
  String: "This is something inside the body."
date: 34334342342
title: ✏️ 
  String: "Nota 1"
```

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── firebase
│   │   ├── config.js
│   │   └── providers.js
│   ├── helpers
│   │   └── loadNotes.js
│   ├── hooks
│   │   ├── useCheckAuth.js
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   ├── SideBarItem.jsx 👈👀
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   ├── authSlice.js
│   │   │   └── thunks.js
│   │   ├── journal
│   │   │   ├── journalSlice.js
│   │   │   └── thunks.js
│   │   └── store.js
│   ├── styles.css
│   ├── theme
│   │   ├── purpleTheme.js
│   │   └── Theme.jsx
│   └── ui
│       └── components
│           └── CheckingAuth.jsx
├── vite.config.js
└── yarn.lock
```

`src/journal/components/SideBarItem.jsx`

```jsx
import {
  Grid2,
  ListItem,
  ListItemButton,
  ListItemIcon,
  ListItemText,
} from "@mui/material";
import { TurnedInNot } from "@mui/icons-material";
import { useMemo } from "react";

export const SideBarItem = ({ title = "", body, id }) => {
  const newTitle = useMemo(() => {
    return title.length > 17
      ? title.substring(0, 17) + "..."
      : title;
  }, [title]);

  return (
    <ListItem disablePadding>
      <ListItemButton component="a">
        <ListItemIcon>
          <TurnedInNot />
        </ListItemIcon>
        <Grid2 container>
          <ListItemText
            // primary={text}
            secondary={body}
          >
            {newTitle}
          </ListItemText>
        </Grid2>
      </ListItemButton>
    </ListItem>
  );
};
```

`src/journal/components/SideBar.jsx`

```jsx
import {
  Box,
  Drawer,
  Typography,
  Toolbar,
  Divider,
  List,
} from "@mui/material";
import { useSelector } from "react-redux";
import { SideBarItem } from "./SideBarItem";

export const SideBar = ({ drawerWidth = 240 }) => {
  const { displayName } = useSelector((state) => state.auth);
  const { notes } = useSelector((state) => state.journal);

  return (
    // <Box
    //   component="nav"
    //   sx={{
    //     width: { sm: drawerWidth },
    //     flexShrink: { sm: 0 },
    //   }}
    // >
    <Drawer
      variant="permanent"
      anchor="left"
      open
      sx={{
        width: { sm: drawerWidth },
        flexShrink: { sm: 0 },
        display: { xs: "block" },
        "& .MuiDrawer-paper": {
          boxSizing: "border-box",
          width: drawerWidth,
        },
      }}
    >
      <Toolbar>
        <Typography variant="h6" noWrap component="div">
          {displayName}
        </Typography>
      </Toolbar>
      <Divider />

      <Box component="nav">
        <List>
          {notes.map((note) => (
            <SideBarItem key={note.id} {...note} />
          ))}
        </List>
      </Box>
    </Drawer>
    //* </Box>
  );
};
```

### 20.10 Activar una nota

`src/journal/components/SideBarItem.jsx`

```jsx
import { useMemo } from "react";
import { useDispatch } from "react-redux";
import {
  Grid2,
  ListItem,
  ListItemButton,
  ListItemIcon,
  ListItemText,
} from "@mui/material";
import { TurnedInNot } from "@mui/icons-material";
import { setActiveNote } from "../../store/journal/journalSlice";

export const SideBarItem = ({
  title = "",
  body,
  id,
  date,
  imageUrls = [],
}) => {
  const dispatch = useDispatch();

  const onClickNote = () => {
    dispatch(
      setActiveNote({ title, body, id, date, imageUrls })
    );
  };

  const newTitle = useMemo(() => {
    return title.length > 17
      ? title.substring(0, 17) + "..."
      : title;
  }, [title]);

  return (
    <ListItem disablePadding>
      <ListItemButton component="a" onClick={onClickNote}>
        <ListItemIcon>
          <TurnedInNot />
        </ListItemIcon>
        <Grid2 container>
          <ListItemText
            // primary={text}
            secondary={body}
          >
            {newTitle}
          </ListItemText>
        </Grid2>
      </ListItemButton>
    </ListItem>
  );
};
```

### 20.11 Activar una nota para su edición

`src/auth/pages/LoginPage.jsx`

```jsx
import { useMemo } from "react";
import { useDispatch, useSelector } from "react-redux";
import { Link as RouterLink } from "react-router";
import {
  TextField,
  Grid2,
  Button,
  Link,
  Box,
  Alert,
} from "@mui/material";
import { Google } from "@mui/icons-material";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import {
  startGoogleSignIn,
  startLoginWithEmailPassword,
} from "../../store/auth/thunks";

const formDate = { 👈👀👇
  email: "",
  password: "",
};

export const LoginPage = () => {
  const { status, errorMessage } = useSelector(
    (state) => state.auth
  );

  const dispatch = useDispatch();

  const { email, password, handleInputChange } =
    useForm(formDate); 👈👀

  const isAuthenticating = useMemo(
    () => status === "checking",
    [status]
  );

  // const { status } = useSelector((state) => state.auth);

  // console.log(email, password);

  const handleSubmit = (event) => {
    event.preventDefault();

    // console.log({ email, password });
    //! This isn't the action to be dispatched
    // dispatch(checkingAuthentication());
    dispatch(
      startLoginWithEmailPassword({ email, password })
    );
  };

  const handleGoogleSignIn = () => {
    console.log("handleGoogleSignIn");

    dispatch(startGoogleSignIn());
  };

  // useEffect(() => {
  //   dispatch(checkingAuthentication());
  // }, []);

  return (
    <AuthLayout title="Login">
      <form
        action=""
        onSubmit={handleSubmit}
        className="animate__animated animate__fadeIn animate__faster"
      >
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>
        {/* New */}
        <Box>
          <Grid2
            size={{ xs: 12 }}
            display={!!errorMessage ? "" : "none"}
            sx={{
              mt: 1,
            }}
          >
            <Alert severity="error">{errorMessage}</Alert>
          </Grid2>
          <Grid2 container spacing={2} sx={{ mt: 2 }}>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                type="submit"
                variant="contained"
                fullWidth
              >
                Login
              </Button>
            </Grid2>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                variant="contained"
                fullWidth
                startIcon={<Google />}
                onClick={handleGoogleSignIn}
              >
                Google
              </Button>
            </Grid2>
          </Grid2>
          <Grid2
            container
            // direction="row"
            justifyContent="end"
            sx={{ mt: 2 }}
          >
            <Link
              component={RouterLink}
              color="inherit"
              to="/auth/register"
            >
              Create an account.
            </Link>
          </Grid2>
        </Box>
      </form>
    </AuthLayout>
  );
};
```

`src/hooks/useForm.js`

```js
import { useEffect, useMemo, useState } from "react";

export const useForm = (
  initialForm = {},
  formValidations = {}
) => {
  const [formState, setFormState] = useState(initialForm);
  const [formValidation, setFormValidation] = useState({});

  // const { value, name, password } = formState;

  useEffect(() => {
    createValidators();
  }, [formState]);

  useEffect(() => { 👈👀👇
    setFormState(initialForm);
  }, [initialForm]);

  const isFormValid = useMemo(() => {
    for (const formValue of Object.keys(formValidation)) {
      if (formValidation[formValue] !== null) return false;
    }

    return true;
  }, [formValidation]);

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  const handleResetForm = () => {
    setFormState(initialForm);
  };

  const createValidators = () => {
    const formCheckedValues = {};

    for (const formField of Object.keys(formValidations)) {
      // xd = fn
      const [
        fn,
        errorMessage, //= "This field is required",
      ] = formValidations[formField];

      formCheckedValues[`${formField}Valid`] = fn(
        formState[formField]
      )
        ? null
        : errorMessage;
    }

    setFormValidation(formCheckedValues);
  };

  return {
    ...formState,
    formState,
    handleInputChange,
    handleResetForm,
    ...formValidation,
    isFormValid,
  };
};
```

`src/journal/views/NoteView.jsx`

```jsx
import { useSelector } from "react-redux";
import {
  Button,
  Grid2,
  Typography,
  TextField,
} from "@mui/material";
import { SaveOutlined } from "@mui/icons-material";
import { ImageGallery } from "../components/ImageGallery";
import { useForm } from "../../hooks/useForm";
import { useMemo } from "react";

export const NoteView = () => {
  const { active: note } = useSelector(
    (state) => state.journal
  );
  const { body, title, date, handleInputChange, formState } =
    useForm(note);

  const dateString = useMemo(() => { 👈👀👇
    const newDate = new Date(date);
    return newDate.toUTCString();
  }, [date]);

  return (
    <>
      <Grid2
        className="animate__animated animate__fadeIn animate__faster"
        container
        justifyContent="space-between"
        alignItems="center"
        sx={{ mb: 1 }}
      >
        <Grid2>
          <Typography
            variant="h5"
            fontSize={39}
            fontWeight="light"
          >
            {dateString}
          </Typography>
        </Grid2>

        <Grid2>
          <Button color="primary" sx={{ padding: 2 }}>
            <SaveOutlined sx={{ fontSize: 30, mr: 1 }} />
            Save
          </Button>
        </Grid2>

        <Grid2 container sx={{ flexGrow: 1 }}>
          <TextField
            id=""
            type="text"
            variant="filled"
            label="Title"
            placeholder="Enter a title"
            fullWidth
            sx={{ border: "none", mb: 1 }}
            name="title" 👈👀👇
            value={title}
            onChange={handleInputChange}
          />
          <TextField
            id=""
            type="text"
            variant="filled"
            // label="Title"
            placeholder="What happened today?"
            fullWidth
            multiline
            minRows={5}
            sx={{ border: "none", mb: 1 }}
            name="body" 👈👀👇
            value={body}
            onChange={handleInputChange}
          />
        </Grid2>

        {/* Image gallery */}
        <ImageGallery />
      </Grid2>
    </>
  );
};
```

### 20.12 Actualizar la nota actual

`src/journal/views/NoteView.jsx`

```jsx
import { useDispatch, useSelector } from "react-redux";
import {
  Button,
  Grid2,
  Typography,
  TextField,
} from "@mui/material";
import { SaveOutlined } from "@mui/icons-material";
import { ImageGallery } from "../components/ImageGallery";
import { useForm } from "../../hooks/useForm";
import { useEffect, useMemo } from "react";
import { setActiveNote } from "../../store/journal/journalSlice";
import { startSaveNote } from "../../store/journal/thunks";

export const NoteView = () => {
  const dispatch = useDispatch();
  const { active: note } = useSelector(
    (state) => state.journal
  );
  const { body, title, date, handleInputChange, formState } =
    useForm(note);

  const dateString = useMemo(() => {
    const newDate = new Date(date);
    return newDate.toUTCString();
  }, [date]);

  useEffect(() => {
    dispatch(setActiveNote(formState));
  }, [formState]);

  const onSaveNote = () => {
    dispatch(startSaveNote());
  };

  return (
    <>
      <Grid2
        className="animate__animated animate__fadeIn animate__faster"
        container
        justifyContent="space-between"
        alignItems="center"
        sx={{ mb: 1 }}
      >
        <Grid2>
          <Typography
            variant="h5"
            fontSize={39}
            fontWeight="light"
          >
            {dateString}
          </Typography>
        </Grid2>

        <Grid2>
          <Button
            onClick={onSaveNote}
            color="primary"
            sx={{ padding: 2 }}
          >
            <SaveOutlined sx={{ fontSize: 30, mr: 1 }} />
            Save
          </Button>
        </Grid2>

        <Grid2 container sx={{ flexGrow: 1 }}>
          <TextField
            id=""
            type="text"
            variant="filled"
            label="Title"
            placeholder="Enter a title"
            fullWidth
            sx={{ border: "none", mb: 1 }}
            name="title"
            value={title}
            onChange={handleInputChange}
          />
          <TextField
            id=""
            type="text"
            variant="filled"
            // label="Title"
            placeholder="What happened today?"
            fullWidth
            multiline
            minRows={5}
            sx={{ border: "none", mb: 1 }}
            name="body"
            value={body}
            onChange={handleInputChange}
          />
        </Grid2>

        {/* Image gallery */}
        <ImageGallery />
      </Grid2>
    </>
  );
};
```

`src/store/journal/thunks.js`

```js
import {
  collection,
  doc,
  setDoc,
} from "firebase/firestore/lite";
import { FirebaseDB } from "../../firebase/config";
import {
  addNewEmptyNote,
  savingNewNote,
  setActiveNote,
  setNotes,
  setSaving,
} from "./journalSlice";
import { loadNotes } from "../../helpers/loadNotes";

export const startNewNote = () => {
  return async (dispatch, getState) => {
    dispatch(savingNewNote());

    const { uid } = getState().auth;
    // uid

    const newNote = {
      title: "",
      body: "",
      date: new Date().getTime(),
    };

    const newDoc = doc(
      collection(FirebaseDB, `${uid}/journal/notes`)
    );

    // Para ver la info añadir variable y hacer console.log
    await setDoc(newDoc, newNote);

    newNote.id = newDoc.id;

    // dispatch
    dispatch(addNewEmptyNote(newNote));
    dispatch(setActiveNote(newNote));
  };
};

export const startLoadingNotes = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;

    if (!uid) throw new Error("The user uid doesn't exist");

    const notes = await loadNotes(uid);

    dispatch(setNotes(notes));
  };
};

export const startSaveNote = () => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    const { uid } = getState().auth;
    const { active: note } = getState().journal;

    const noteToFireStore = { ...note };
    delete noteToFireStore.id;

    const docRef = doc(
      FirebaseDB,
      `${uid}/journal/notes/${note.id}`
    );

    // Merge para mantener los campos existentes
    await setDoc(docRef, noteToFireStore, { merge: true });
  };
};
```

`src/store/journal/journalSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const journalSlice = createSlice({
  name: "journal",
  initialState: {
    isSaving: false,
    messageSaved: "",
    notes: [],
    active: null,
    // active: {
    //   id: "ABC123",
    //   title: "",
    //   body: "",
    //   date: 1234567,
    //   imageUrls: [],
    // },
  },
  reducers: {
    savingNewNote: (state, { payload }) => {
      state.isSaving = true;
    },
    addNewEmptyNote: (state, { payload }) => {
      state.notes.push(payload);
      state.isSaving = false;
    },
    setActiveNote: (state, { payload }) => {
      state.active = payload;
    },
    setNotes: (state, { payload }) => {
      state.notes = payload;
    },
    setSaving: (state) => {
      state.isSaving = true;
      // TODO: error message
    },
    updateNote: (state, action) => {
      state.isSaving = false;
      // state.notes = state.notes.map();
    },
    deleteNoteById: (state, action) => {},
  },
});

export const {
  addNewEmptyNote,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setSaving,
  updateNote,
} = journalSlice.actions;
```

### 20.13 Resolución de la tarea

`src/store/journal/journalSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const journalSlice = createSlice({
  name: "journal",
  initialState: {
    isSaving: false,
    messageSaved: "",
    notes: [],
    active: null,
    // active: {
    //   id: "ABC123",
    //   title: "",
    //   body: "",
    //   date: 1234567,
    //   imageUrls: [],
    // },
  },
  reducers: {
    savingNewNote: (state, { payload }) => {
      state.isSaving = true;
    },
    addNewEmptyNote: (state, { payload }) => {
      state.notes.push(payload);
      state.isSaving = false;
    },
    setActiveNote: (state, { payload }) => {
      state.active = payload;
    },
    setNotes: (state, { payload }) => {
      state.notes = payload;
    },
    setSaving: (state) => {
      state.isSaving = true;
      // TODO: error message
    },
    updateNote: (state, { payload }) => {
      state.isSaving = false;
      state.notes = state.notes.map((note) => {
        if (note.id === payload.id) {
          return payload;
        }

        return note;
      });

      // TODO: Mostrar mensaje de actualización
    },
    deleteNoteById: (state, action) => {},
  },
});

export const {
  addNewEmptyNote,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setSaving,
  updateNote,
} = journalSlice.actions;
```

`src/store/journal/thunks.js`

```js
import {
  collection,
  doc,
  setDoc,
} from "firebase/firestore/lite";
import { FirebaseDB } from "../../firebase/config";
import {
  addNewEmptyNote,
  savingNewNote,
  setActiveNote,
  setNotes,
  setSaving,
  updateNote,
} from "./journalSlice";
import { loadNotes } from "../../helpers/loadNotes";

export const startNewNote = () => {
  return async (dispatch, getState) => {
    dispatch(savingNewNote());

    const { uid } = getState().auth;
    // uid

    const newNote = {
      title: "",
      body: "",
      date: new Date().getTime(),
    };

    const newDoc = doc(
      collection(FirebaseDB, `${uid}/journal/notes`)
    );

    // Para ver la info añadir variable y hacer console.log
    await setDoc(newDoc, newNote);

    newNote.id = newDoc.id;

    // dispatch
    dispatch(addNewEmptyNote(newNote));
    dispatch(setActiveNote(newNote));
  };
};

export const startLoadingNotes = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;

    if (!uid) throw new Error("The user uid doesn't exist");

    const notes = await loadNotes(uid);

    dispatch(setNotes(notes));
  };
};

export const startSaveNote = () => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    const { uid } = getState().auth;
    const { active: note } = getState().journal;

    const noteToFireStore = { ...note };
    delete noteToFireStore.id;

    const docRef = doc(
      FirebaseDB,
      `${uid}/journal/notes/${note.id}`
    );

    // Merge para mantener los campos existentes
    await setDoc(docRef, noteToFireStore, { merge: true });

    dispatch(updateNote(note));
  };
};
```

### 20.14 SweetAlert 2

Instalar [Sweetalert2](https://sweetalert2.github.io/)

```bash
npm install sweetalert2
```

`src/store/journal/journalSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const journalSlice = createSlice({
  name: "journal",
  initialState: {
    isSaving: false,
    messageSaved: "",
    notes: [],
    active: null,
    // active: {
    //   id: "ABC123",
    //   title: "",
    //   body: "",
    //   date: 1234567,
    //   imageUrls: [],
    // },
  },
  reducers: {
    savingNewNote: (state, { payload }) => {
      state.isSaving = true;
    },
    addNewEmptyNote: (state, { payload }) => {
      state.notes.push(payload);
      state.isSaving = false;
    },
    setActiveNote: (state, { payload }) => {
      state.active = payload;
      state.messageSaved = "";
    },
    setNotes: (state, { payload }) => {
      state.notes = payload;
    },
    setSaving: (state) => {
      state.isSaving = true;
      state.messageSaved = "";
    },
    updateNote: (state, { payload }) => {
      state.isSaving = false;
      state.notes = state.notes.map((note) => {
        if (note.id === payload.id) {
          return payload;
        }

        return note;
      });

      state.messageSaved = `${payload.title}, updated correctly.`;
    },
    deleteNoteById: (state, action) => {},
  },
});

export const {
  addNewEmptyNote,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setSaving,
  updateNote,
} = journalSlice.actions;
```

`src/journal/views/NoteView.jsx`

```jsx
import { useEffect, useMemo } from "react";
import { useDispatch, useSelector } from "react-redux";
import {
  Button,
  Grid2,
  Typography,
  TextField,
} from "@mui/material";
import { SaveOutlined } from "@mui/icons-material";
import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.css";

import { useForm } from "../../hooks/useForm";
import { ImageGallery } from "../components/ImageGallery";
import { setActiveNote } from "../../store/journal/journalSlice";
import { startSaveNote } from "../../store/journal/thunks";

export const NoteView = () => {
  const dispatch = useDispatch();
  const {
    active: note,
    messageSaved,
    isSaving,
  } = useSelector((state) => state.journal);
  const { body, title, date, handleInputChange, formState } =
    useForm(note);

  const dateString = useMemo(() => {
    const newDate = new Date(date);
    return newDate.toUTCString();
  }, [date]);

  useEffect(() => {
    dispatch(setActiveNote(formState));
  }, [formState]);

  useEffect(() => {
    if (messageSaved.length > 0) {
      Swal.fire("Note updated.", messageSaved, "success");
    }
  }, [messageSaved]);

  const onSaveNote = () => {
    dispatch(startSaveNote());
  };

  return (
    <>
      <Grid2
        className="animate__animated animate__fadeIn animate__faster"
        container
        justifyContent="space-between"
        alignItems="center"
        sx={{ mb: 1 }}
      >
        <Grid2>
          <Typography
            variant="h5"
            fontSize={39}
            fontWeight="light"
          >
            {dateString}
          </Typography>
        </Grid2>

        <Grid2>
          <Button
            disabled={isSaving}
            onClick={onSaveNote}
            color="primary"
            sx={{ padding: 2 }}
          >
            <SaveOutlined sx={{ fontSize: 30, mr: 1 }} />
            Save
          </Button>
        </Grid2>

        <Grid2 container sx={{ flexGrow: 1 }}>
          <TextField
            id=""
            type="text"
            variant="filled"
            label="Title"
            placeholder="Enter a title"
            fullWidth
            sx={{ border: "none", mb: 1 }}
            name="title"
            value={title}
            onChange={handleInputChange}
          />
          <TextField
            id=""
            type="text"
            variant="filled"
            // label="Title"
            placeholder="What happened today?"
            fullWidth
            multiline
            minRows={5}
            sx={{ border: "none", mb: 1 }}
            name="body"
            value={body}
            onChange={handleInputChange}
          />
        </Grid2>

        {/* Image gallery */}
        <ImageGallery />
      </Grid2>
    </>
  );
};
```

### 20.15 Cloudinary.com - Backend para subir imágenes

#### Cloudinary

Crea una cuenta: [Cloudinary](https://cloudinary.com/)

`⚙️/Upload/Upload presets/Add Upload Preset`

- Upload preset name: `journal-app`
- Signing Mode: `Unsigned`
- Folder: `journal`
- Save

Ahora revisa la documentación de Cloudinary en `⭕❓/Documentation` o [aquí](https://cloudinary.com/documentation/)

Busca `Upload API reference` o entra en [Upload API reference](https://cloudinary.com/documentation/image_upload_api_reference#banner)

Esto nos va a servir en Postman:

`POST https://api.cloudinary.com/v1_1/demo/image/upload`

📌 Una vez cargada la imagen de prueba usando Postman podemos revisarlas en `Image/Media Library/Folders`

#### Postman

>  Si tienes problemas con Postman usa la [version web](https://web.postman.co/workspace/My-Workspace~8937cc18-9d43-4a60-8591-492add66379f/request/create?requestId=30bd5742-7613-4cd8-8463-93c7f67858f8) de este.

Añadimos una nueva pestaña para hacer las peticiones `POST`. 

Teniendo esto `POST https://api.cloudinary.com/v1_1/demo/image/upload`, reemplaza `demo` por el nombre de tu Cloud, revísalo en:

`⚙️/API Keys`

Queda algo así:

`POST https://api.cloudinary.com/v1_1/luxxyz26z/upload`

Una vez colocado esto, nos vamos a `Body` dentro de Postman y seleccionamos `form-data`. 

Ahora, dentro de `KEY` escribimos `file` y de tipo `file`, en `VALUE` seleccionamos cualquier imagen que tengamos en nuestra PC.

Nuevamente en `KEY` escribimos `upload_preset`  y en `Value` escribimos `journal-app` nombre que le dimos cuando entramos en `⚙️/Upload/Upload presets/Add Upload Preset`

- Upload preset name: `journal-app`

|Key           | Value        |
|--------------|--------------|
|file (file)   |cyberpunk.jpg |
|upload_preset |journal-app   |

**Send**

Si copias la `secure_url` verás la imagen que cargaste.

### 20.16 Seleccionar archivos desde React

`src/journal/views/NoteView.jsx`

```jsx
import { useEffect, useMemo, useRef } from "react";
import { useDispatch, useSelector } from "react-redux";
import {
  Button,
  Grid2,
  Typography,
  TextField,
  IconButton,
} from "@mui/material";
import {
  SaveOutlined,
  UploadOutlined,
} from "@mui/icons-material";
import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.css";

import { useForm } from "../../hooks/useForm";
import { ImageGallery } from "../components/ImageGallery";
import { setActiveNote } from "../../store/journal/journalSlice";
import { startSaveNote } from "../../store/journal/thunks";

export const NoteView = () => {
  const dispatch = useDispatch();
  const {
    active: note,
    messageSaved,
    isSaving,
  } = useSelector((state) => state.journal);
  const { body, title, date, handleInputChange, formState } =
    useForm(note);

  const dateString = useMemo(() => {
    const newDate = new Date(date);
    return newDate.toUTCString();
  }, [date]);

  const fileInputRef = useRef();

  useEffect(() => {
    dispatch(setActiveNote(formState));
  }, [formState]);

  useEffect(() => {
    if (messageSaved.length > 0) {
      Swal.fire("Note updated.", messageSaved, "success");
    }
  }, [messageSaved]);

  const onSaveNote = () => {
    dispatch(startSaveNote());
  };

  const onFileInputChange = ({ target }) => {
    if (target.files === 0) return;

    console.log("Uploading files");

    // dispatch(startUploadingFiles(target.files));
  };

  return (
    <>
      <Grid2
        className="animate__animated animate__fadeIn animate__faster"
        container
        justifyContent="space-between"
        alignItems="center"
        sx={{ mb: 1 }}
      >
        <Grid2>
          <Typography
            variant="h5"
            fontSize={39}
            fontWeight="light"
          >
            {dateString}
          </Typography>
        </Grid2>

        <Grid2>
          <input
            type="file"
            multiple
            ref={fileInputRef}
            onChange={onFileInputChange}
            style={{
              display: "none",
            }}
          />

          <IconButton
            // aria-label=""
            color="primary"
            disabled={isSaving}
            onClick={() => fileInputRef.current.click()}
          >
            <UploadOutlined />
          </IconButton>

          <Button
            disabled={isSaving}
            onClick={onSaveNote}
            color="primary"
            sx={{ padding: 2 }}
          >
            <SaveOutlined sx={{ fontSize: 30, mr: 1 }} />
            Save
          </Button>
        </Grid2>

        <Grid2 container sx={{ flexGrow: 1 }}>
          <TextField
            id=""
            type="text"
            variant="filled"
            label="Title"
            placeholder="Enter a title"
            fullWidth
            sx={{ border: "none", mb: 1 }}
            name="title"
            value={title}
            onChange={handleInputChange}
          />
          <TextField
            id=""
            type="text"
            variant="filled"
            // label="Title"
            placeholder="What happened today?"
            fullWidth
            multiline
            minRows={5}
            sx={{ border: "none", mb: 1 }}
            name="body"
            value={body}
            onChange={handleInputChange}
          />
        </Grid2>

        {/* Image gallery */}
        <ImageGallery />
      </Grid2>
    </>
  );
};
```

### 20.17 Subir imagen a Cloudinary

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── firebase
│   │   ├── config.js
│   │   └── providers.js
│   ├── helpers
│   │   ├── fileUpload.js 👈👀
│   │   └── loadNotes.js
│   ├── hooks
│   │   ├── useCheckAuth.js
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   ├── SideBarItem.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   ├── authSlice.js
│   │   │   └── thunks.js
│   │   ├── journal
│   │   │   ├── journalSlice.js
│   │   │   └── thunks.js
│   │   └── store.js
│   ├── styles.css
│   ├── theme
│   │   ├── purpleTheme.js
│   │   └── Theme.jsx
│   └── ui
│       └── components
│           └── CheckingAuth.jsx
├── vite.config.js
└── yarn.lock
```

`src/store/journal/thunks.js`

```js
import {
  collection,
  doc,
  setDoc,
} from "firebase/firestore/lite";
import { FirebaseDB } from "../../firebase/config";
import {
  addNewEmptyNote,
  savingNewNote,
  setActiveNote,
  setNotes,
  setSaving,
  updateNote,
} from "./journalSlice";
import { loadNotes } from "../../helpers/loadNotes";
import { fileUpload } from "../../helpers/fileUpload";

export const startNewNote = () => {
  return async (dispatch, getState) => {
    dispatch(savingNewNote());

    const { uid } = getState().auth;
    // uid

    const newNote = {
      title: "",
      body: "",
      date: new Date().getTime(),
    };

    const newDoc = doc(
      collection(FirebaseDB, `${uid}/journal/notes`)
    );

    // Para ver la info añadir variable y hacer console.log
    await setDoc(newDoc, newNote);

    newNote.id = newDoc.id;

    // dispatch
    dispatch(addNewEmptyNote(newNote));
    dispatch(setActiveNote(newNote));
  };
};

export const startLoadingNotes = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;

    if (!uid) throw new Error("The user uid doesn't exist");

    const notes = await loadNotes(uid);

    dispatch(setNotes(notes));
  };
};

export const startSaveNote = () => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    const { uid } = getState().auth;
    const { active: note } = getState().journal;

    const noteToFireStore = { ...note };
    delete noteToFireStore.id;

    const docRef = doc(
      FirebaseDB,
      `${uid}/journal/notes/${note.id}`
    );

    // Merge para mantener los campos existentes
    await setDoc(docRef, noteToFireStore, { merge: true });

    dispatch(updateNote(note));
  };
};

export const startUploadingFiles = (files = []) => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    await fileUpload(files[0]);
  };
};
```

`src/helpers/fileUpload.js`

```js
export const fileUpload = async (file) => {
  if (!file) throw new Error("No files will be uploaded.");
  const cloudUrl =
    "https://api.cloudinary.com/v1_1/delkxyr6z/upload";

  const formData = new FormData();
  formData.append("upload_preset", "journal-app");
  formData.append("file", file);

  try {
    const resp = await fetch(cloudUrl, {
      method: "POST",
      body: formData,
    });

    console.log(resp);
    if (!resp.ok)
      throw new Error("The image could not be uploaded.");

    const cloudResp = await resp.json();

    console.log({ cloudResp });

    return cloudResp.secure_url;
  } catch (error) {
    console.log(error);

    throw new Error(error.message);
  }
};
```

`src/journal/views/NoteView.jsx`

```jsx
import { useEffect, useMemo, useRef } from "react";
import { useDispatch, useSelector } from "react-redux";
import {
  Button,
  Grid2,
  Typography,
  TextField,
  IconButton,
} from "@mui/material";
import {
  SaveOutlined,
  UploadOutlined,
} from "@mui/icons-material";
import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.css";

import { useForm } from "../../hooks/useForm";
import { ImageGallery } from "../components/ImageGallery";
import { setActiveNote } from "../../store/journal/journalSlice";
import {
  startSaveNote,
  startUploadingFiles,
} from "../../store/journal/thunks";

export const NoteView = () => {
  const dispatch = useDispatch();
  const {
    active: note,
    messageSaved,
    isSaving,
  } = useSelector((state) => state.journal);
  const { body, title, date, handleInputChange, formState } =
    useForm(note);

  const dateString = useMemo(() => {
    const newDate = new Date(date);
    return newDate.toUTCString();
  }, [date]);

  const fileInputRef = useRef();

  useEffect(() => {
    dispatch(setActiveNote(formState));
  }, [formState]);

  useEffect(() => {
    if (messageSaved.length > 0) {
      Swal.fire("Note updated.", messageSaved, "success");
    }
  }, [messageSaved]);

  const onSaveNote = () => {
    dispatch(startSaveNote());
  };

  const onFileInputChange = ({ target }) => {
    if (target.files === 0) return;

    dispatch(startUploadingFiles(target.files));
  };

  return (
    <>
      <Grid2
        className="animate__animated animate__fadeIn animate__faster"
        container
        justifyContent="space-between"
        alignItems="center"
        sx={{ mb: 1 }}
      >
        <Grid2>
          <Typography
            variant="h5"
            fontSize={39}
            fontWeight="light"
          >
            {dateString}
          </Typography>
        </Grid2>

        <Grid2>
          <input
            type="file"
            multiple
            ref={fileInputRef}
            onChange={onFileInputChange}
            style={{
              display: "none",
            }}
          />

          <IconButton
            // aria-label=""
            color="primary"
            disabled={isSaving}
            onClick={() => fileInputRef.current.click()}
          >
            <UploadOutlined />
          </IconButton>

          <Button
            disabled={isSaving}
            onClick={onSaveNote}
            color="primary"
            sx={{ padding: 2 }}
          >
            <SaveOutlined sx={{ fontSize: 30, mr: 1 }} />
            Save
          </Button>
        </Grid2>

        <Grid2 container sx={{ flexGrow: 1 }}>
          <TextField
            id=""
            type="text"
            variant="filled"
            label="Title"
            placeholder="Enter a title"
            fullWidth
            sx={{ border: "none", mb: 1 }}
            name="title"
            value={title}
            onChange={handleInputChange}
          />
          <TextField
            id=""
            type="text"
            variant="filled"
            // label="Title"
            placeholder="What happened today?"
            fullWidth
            multiline
            minRows={5}
            sx={{ border: "none", mb: 1 }}
            name="body"
            value={body}
            onChange={handleInputChange}
          />
        </Grid2>

        {/* Image gallery */}
        <ImageGallery />
      </Grid2>
    </>
  );
};
```

Ya podemos ver la imagen subida en Claudinary .

### 20.18 Múltiples peticiones de forma simultánea

`src/store/journal/thunks.js`

```js
import {
  collection,
  doc,
  setDoc,
} from "firebase/firestore/lite";
import { FirebaseDB } from "../../firebase/config";
import {
  addNewEmptyNote,
  savingNewNote,
  setActiveNote,
  setNotes,
  setPhotosToActiveNote,
  setSaving,
  updateNote,
} from "./journalSlice";
import { loadNotes } from "../../helpers/loadNotes";
import { fileUpload } from "../../helpers/fileUpload";

export const startNewNote = () => {
  return async (dispatch, getState) => {
    dispatch(savingNewNote());

    const { uid } = getState().auth;
    // uid

    const newNote = {
      title: "",
      body: "",
      date: new Date().getTime(),
    };

    const newDoc = doc(
      collection(FirebaseDB, `${uid}/journal/notes`)
    );

    // Para ver la info añadir variable y hacer console.log
    await setDoc(newDoc, newNote);

    newNote.id = newDoc.id;

    // dispatch
    dispatch(addNewEmptyNote(newNote));
    dispatch(setActiveNote(newNote));
  };
};

export const startLoadingNotes = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;

    if (!uid) throw new Error("The user uid doesn't exist");

    const notes = await loadNotes(uid);

    dispatch(setNotes(notes));
  };
};

export const startSaveNote = () => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    const { uid } = getState().auth;
    const { active: note } = getState().journal;

    const noteToFireStore = { ...note };
    delete noteToFireStore.id;

    const docRef = doc(
      FirebaseDB,
      `${uid}/journal/notes/${note.id}`
    );

    // Merge para mantener los campos existentes
    await setDoc(docRef, noteToFireStore, { merge: true });

    dispatch(updateNote(note));
  };
};

export const startUploadingFiles = (files = []) => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    // await fileUpload(files[0]);
    const fileUploadPromises = [];
    for (const file of files) {
      fileUploadPromises.push(fileUpload(file));
    }

    const photosUrls = await Promise.all(fileUploadPromises);

    dispatch(setPhotosToActiveNote(photosUrls));
  };
};
```

`src/store/journal/journalSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const journalSlice = createSlice({
  name: "journal",
  initialState: {
    isSaving: false,
    messageSaved: "",
    notes: [],
    active: null,
    // active: {
    //   id: "ABC123",
    //   title: "",
    //   body: "",
    //   date: 1234567,
    //   imageUrls: [],
    // },
  },
  reducers: {
    savingNewNote: (state, { payload }) => {
      state.isSaving = true;
    },
    addNewEmptyNote: (state, { payload }) => {
      state.notes.push(payload);
      state.isSaving = false;
    },
    setActiveNote: (state, { payload }) => {
      state.active = payload;
      state.messageSaved = "";
    },
    setNotes: (state, { payload }) => {
      state.notes = payload;
    },
    setSaving: (state) => {
      state.isSaving = true;
      state.messageSaved = "";
    },
    updateNote: (state, { payload }) => {
      state.isSaving = false;
      state.notes = state.notes.map((note) => {
        if (note.id === payload.id) {
          return payload;
        }

        return note;
      });

      state.messageSaved = `${payload.title}, updated correctly.`;
    },
    setPhotosToActiveNote: (state, action) => {
      state.active.imageUrls = [
        ...state.active.imageUrls,
        ...action.payload,
      ];
      state.isSaving = false;
    },
    deleteNoteById: (state, action) => {},
  },
});

export const {
  addNewEmptyNote,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setPhotosToActiveNote,
  setSaving,
  updateNote,
} = journalSlice.actions;
```

`src/helpers/fileUpload.js`

```js
export const fileUpload = async (file) => {
  if (!file) throw new Error("No files will be uploaded.");
  const cloudUrl =
    "https://api.cloudinary.com/v1_1/delkxyr6z/upload";

  const formData = new FormData();
  formData.append("upload_preset", "journal-app");
  formData.append("file", file);

  try {
    const resp = await fetch(cloudUrl, {
      method: "POST",
      body: formData,
    });

    if (!resp.ok)
      throw new Error("The image could not be uploaded.");

    const cloudResp = await resp.json();

    return cloudResp.secure_url;
  } catch (error) {
    console.log(error);

    throw new Error(error.message);
  }
};
```

### 20.19 Mostrar las imágenes cargadas

`src/journal/views/NoteView.jsx`

```jsx
import { useEffect, useMemo, useRef } from "react";
import { useDispatch, useSelector } from "react-redux";
import {
  Button,
  Grid2,
  Typography,
  TextField,
  IconButton,
} from "@mui/material";
import {
  SaveOutlined,
  UploadOutlined,
} from "@mui/icons-material";
import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.css";

import { useForm } from "../../hooks/useForm";
import { ImageGallery } from "../components/ImageGallery";
import { setActiveNote } from "../../store/journal/journalSlice";
import {
  startSaveNote,
  startUploadingFiles,
} from "../../store/journal/thunks";

export const NoteView = () => {
  const dispatch = useDispatch();
  const {
    active: note,
    messageSaved,
    isSaving,
  } = useSelector((state) => state.journal);
  const { body, title, date, handleInputChange, formState } =
    useForm(note);

  const dateString = useMemo(() => {
    const newDate = new Date(date);
    return newDate.toUTCString();
  }, [date]);

  const fileInputRef = useRef();

  useEffect(() => {
    dispatch(setActiveNote(formState));
  }, [formState]);

  useEffect(() => {
    if (messageSaved.length > 0) {
      Swal.fire("Note updated.", messageSaved, "success");
    }
  }, [messageSaved]);

  const onSaveNote = () => {
    dispatch(startSaveNote());
  };

  const onFileInputChange = ({ target }) => {
    if (target.files === 0) return;

    dispatch(startUploadingFiles(target.files));
  };

  return (
    <>
      <Grid2
        className="animate__animated animate__fadeIn animate__faster"
        container
        justifyContent="space-between"
        alignItems="center"
        sx={{ mb: 1 }}
      >
        <Grid2>
          <Typography
            variant="h5"
            fontSize={39}
            fontWeight="light"
          >
            {dateString}
          </Typography>
        </Grid2>

        <Grid2>
          <input
            type="file"
            multiple
            ref={fileInputRef}
            onChange={onFileInputChange}
            style={{
              display: "none",
            }}
          />

          <IconButton
            // aria-label=""
            color="primary"
            disabled={isSaving}
            onClick={() => fileInputRef.current.click()}
          >
            <UploadOutlined />
          </IconButton>

          <Button
            disabled={isSaving}
            onClick={onSaveNote}
            color="primary"
            sx={{ padding: 2 }}
          >
            <SaveOutlined sx={{ fontSize: 30, mr: 1 }} />
            Save
          </Button>
        </Grid2>

        <Grid2 container sx={{ flexGrow: 1 }}>
          <TextField
            id=""
            type="text"
            variant="filled"
            label="Title"
            placeholder="Enter a title"
            fullWidth
            sx={{ border: "none", mb: 1 }}
            name="title"
            value={title}
            onChange={handleInputChange}
          />
          <TextField
            id=""
            type="text"
            variant="filled"
            // label="Title"
            placeholder="What happened today?"
            fullWidth
            multiline
            minRows={5}
            sx={{ border: "none", mb: 1 }}
            name="body"
            value={body}
            onChange={handleInputChange}
          />
        </Grid2>

        {/* Image gallery */}
        <ImageGallery images={note.imageUrls} />
      </Grid2>
    </>
  );
};
```

`src/journal/components/ImageGallery.jsx`

```jsx
import { ImageListItem, ImageList } from "@mui/material";

export const ImageGallery = ({ images }) => {
  return (
    <ImageList
      sx={{ width: "100%", height: 500 }}
      cols={4}
      rowHeight={200}
    >
      {images?.map((image) => (
        <ImageListItem key={image}>
          <img
            srcSet={`${image}?w=164&h=164&fit=crop&auto=format&dpr=2 2x`}
            src={`${image}?w=164&h=164&fit=crop&auto=format`}
            alt="Image of the note."
            loading="lazy"
          />
        </ImageListItem>
      ))}
    </ImageList>
  );
};
```

### 20.20 Corregir un posible error

Se corrigió el error en la clase [[#20.11 Activar una nota para su edición]]

### 20.21 Limpiar notas al cerrar sesión

`src/store/journal/journalSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const journalSlice = createSlice({
  name: "journal",
  initialState: {
    isSaving: false,
    messageSaved: "",
    notes: [],
    active: null,
    // active: {
    //   id: "ABC123",
    //   title: "",
    //   body: "",
    //   date: 1234567,
    //   imageUrls: [],
    // },
  },
  reducers: {
    savingNewNote: (state, { payload }) => {
      state.isSaving = true;
    },
    addNewEmptyNote: (state, { payload }) => {
      state.notes.push(payload);
      state.isSaving = false;
    },
    setActiveNote: (state, { payload }) => {
      state.active = payload;
      state.messageSaved = "";
    },
    setNotes: (state, { payload }) => {
      state.notes = payload;
    },
    setSaving: (state) => {
      state.isSaving = true;
      state.messageSaved = "";
    },
    updateNote: (state, { payload }) => {
      state.isSaving = false;
      state.notes = state.notes.map((note) => {
        if (note.id === payload.id) {
          return payload;
        }

        return note;
      });

      state.messageSaved = `${payload.title}, updated correctly.`;
    },
    setPhotosToActiveNote: (state, action) => {
      state.active.imageUrls = [
        ...state.active.imageUrls,
        ...action.payload,
      ];
      state.isSaving = false;
    },
    clearNotesLogout: (state) => {
      state.isSaving = false;
      state.messageSaved = "";
      state.notes = [];
      state.active = null;
    },
    deleteNoteById: (state, action) => {},
  },
});

export const {
  addNewEmptyNote,
  clearNotesLogout,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setPhotosToActiveNote,
  setSaving,
  updateNote,
} = journalSlice.actions;
```

`src/store/auth/thunks.js`

```js
import {
  singInWithGoogle,
  registerUserWithEmailPassword,
  loginWithEmailPassword,
  logoutFirebase,
} from "../../firebase/providers";
import { clearNotesLogout } from "../journal/journalSlice";
import {
  checkingCredentials,
  login,
  logout,
} from "./authSlice";

export const checkingAuthentication = (email, password) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};

export const startGoogleSignIn = () => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await singInWithGoogle();

    // console.log({ result });

    if (!result.ok)
      return dispatch(logout(result.errorMessage));

    dispatch(login(result));
  };
};

export const startCreatingUserWithEmailPassword = ({
  email,
  password,
  displayName,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const { ok, uid, photoURL, errorMessage } =
      await registerUserWithEmailPassword({
        email,
        password,
        displayName,
      });

    if (!ok) return dispatch(logout({ errorMessage }));

    dispatch(login({ uid, displayName, email, photoURL }));
  };
};

export const startLoginWithEmailPassword = ({
  email,
  password,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await loginWithEmailPassword({
      email,
      password,
    });

    if (!result.ok) return dispatch(logout(result));

    dispatch(login(result));
  };
};

export const startLogout = () => {
  return async (dispatch) => {
    await logoutFirebase();

    dispatch(clearNotesLogout());

    dispatch(logout());
  };
};
```

### 20.22 Borrar una nota

`src/journal/views/NoteView.jsx`

```jsx
import { useEffect, useMemo, useRef } from "react";
import { useDispatch, useSelector } from "react-redux";
import {
  Button,
  Grid2,
  Typography,
  TextField,
  IconButton,
} from "@mui/material";
import {
  DeleteOutline,
  SaveOutlined,
  UploadOutlined,
} from "@mui/icons-material";
import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.css";

import { useForm } from "../../hooks/useForm";
import { ImageGallery } from "../components/ImageGallery";
import { setActiveNote } from "../../store/journal/journalSlice";
import {
  startDeletingNote,
  startSaveNote,
  startUploadingFiles,
} from "../../store/journal/thunks";

export const NoteView = () => {
  const dispatch = useDispatch();
  const {
    active: note,
    messageSaved,
    isSaving,
  } = useSelector((state) => state.journal);
  const { body, title, date, handleInputChange, formState } =
    useForm(note);

  const dateString = useMemo(() => {
    const newDate = new Date(date);
    return newDate.toUTCString();
  }, [date]);

  const fileInputRef = useRef();

  useEffect(() => {
    dispatch(setActiveNote(formState));
  }, [formState]);

  useEffect(() => {
    if (messageSaved.length > 0) {
      Swal.fire("Note updated.", messageSaved, "success");
    }
  }, [messageSaved]);

  const onSaveNote = () => {
    dispatch(startSaveNote());
  };

  const onFileInputChange = ({ target }) => {
    if (target.files === 0) return;

    dispatch(startUploadingFiles(target.files));
  };

  const onDelete = () => {
    dispatch(startDeletingNote());
  };

  return (
    <>
      <Grid2
        className="animate__animated animate__fadeIn animate__faster"
        container
        justifyContent="space-between"
        alignItems="center"
        sx={{ mb: 1 }}
      >
        <Grid2>
          <Typography
            variant="h5"
            fontSize={39}
            fontWeight="light"
          >
            {dateString}
          </Typography>
        </Grid2>

        <Grid2>
          <input
            type="file"
            multiple
            ref={fileInputRef}
            onChange={onFileInputChange}
            style={{
              display: "none",
            }}
          />

          <IconButton
            // aria-label=""
            color="primary"
            disabled={isSaving}
            onClick={() => fileInputRef.current.click()}
          >
            <UploadOutlined />
          </IconButton>

          <Button
            disabled={isSaving}
            onClick={onSaveNote}
            color="primary"
            sx={{ padding: 2 }}
          >
            <SaveOutlined sx={{ fontSize: 30, mr: 1 }} />
            Save
          </Button>
        </Grid2>

        <Grid2 container sx={{ flexGrow: 1 }}>
          <TextField
            id=""
            type="text"
            variant="filled"
            label="Title"
            placeholder="Enter a title"
            fullWidth
            sx={{ border: "none", mb: 1 }}
            name="title"
            value={title}
            onChange={handleInputChange}
          />
          <TextField
            id=""
            type="text"
            variant="filled"
            // label="Title"
            placeholder="What happened today?"
            fullWidth
            multiline
            minRows={5}
            sx={{ border: "none", mb: 1 }}
            name="body"
            value={body}
            onChange={handleInputChange}
          />
        </Grid2>

        <Grid2 container justifyContent="end">
          <Button
            onClick={onDelete}
            sx={{ mt: 2 }}
            color="error"
          >
            <DeleteOutline />
            Borrar
          </Button>
        </Grid2>
        {/* Image gallery */}
        <ImageGallery images={note.imageUrls} />
      </Grid2>
    </>
  );
};
```

`src/store/journal/thunks.js`

```js
import {
  collection,
  deleteDoc,
  doc,
  setDoc,
} from "firebase/firestore/lite";
import { FirebaseDB } from "../../firebase/config";
import {
  addNewEmptyNote,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setPhotosToActiveNote,
  setSaving,
  updateNote,
} from "./journalSlice";
import { loadNotes } from "../../helpers/loadNotes";
import { fileUpload } from "../../helpers/fileUpload";

export const startNewNote = () => {
  return async (dispatch, getState) => {
    dispatch(savingNewNote());

    const { uid } = getState().auth;
    // uid

    const newNote = {
      title: "",
      body: "",
      date: new Date().getTime(),
    };

    const newDoc = doc(
      collection(FirebaseDB, `${uid}/journal/notes`)
    );

    // Para ver la info añadir variable y hacer console.log
    await setDoc(newDoc, newNote);

    newNote.id = newDoc.id;

    // dispatch
    dispatch(addNewEmptyNote(newNote));
    dispatch(setActiveNote(newNote));
  };
};

export const startLoadingNotes = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;

    if (!uid) throw new Error("The user uid doesn't exist");

    const notes = await loadNotes(uid);

    dispatch(setNotes(notes));
  };
};

export const startSaveNote = () => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    const { uid } = getState().auth;
    const { active: note } = getState().journal;

    const noteToFireStore = { ...note };
    delete noteToFireStore.id;

    const docRef = doc(
      FirebaseDB,
      `${uid}/journal/notes/${note.id}`
    );

    // Merge para mantener los campos existentes
    await setDoc(docRef, noteToFireStore, { merge: true });

    dispatch(updateNote(note));
  };
};

export const startUploadingFiles = (files = []) => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    // await fileUpload(files[0]);
    const fileUploadPromises = [];
    for (const file of files) {
      fileUploadPromises.push(fileUpload(file));
    }

    const photosUrls = await Promise.all(fileUploadPromises);

    dispatch(setPhotosToActiveNote(photosUrls));
  };
};

export const startDeletingNote = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;
    const { active: note } = getState().journal;

    const docRef = doc(
      FirebaseDB,
      `${uid}/journal/notes/${note.id}`
    );
    await deleteDoc(docRef);

    dispatch(deleteNoteById(note.id));
  };
};
```

`src/store/journal/journalSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const journalSlice = createSlice({
  name: "journal",
  initialState: {
    isSaving: false,
    messageSaved: "",
    notes: [],
    active: null,
    // active: {
    //   id: "ABC123",
    //   title: "",
    //   body: "",
    //   date: 1234567,
    //   imageUrls: [],
    // },
  },
  reducers: {
    savingNewNote: (state, { payload }) => {
      state.isSaving = true;
    },
    addNewEmptyNote: (state, { payload }) => {
      state.notes.push(payload);
      state.isSaving = false;
    },
    setActiveNote: (state, { payload }) => {
      state.active = payload;
      state.messageSaved = "";
    },
    setNotes: (state, { payload }) => {
      state.notes = payload;
    },
    setSaving: (state) => {
      state.isSaving = true;
      state.messageSaved = "";
    },
    updateNote: (state, { payload }) => {
      state.isSaving = false;
      state.notes = state.notes.map((note) => {
        if (note.id === payload.id) {
          return payload;
        }

        return note;
      });

      state.messageSaved = `${payload.title}, updated correctly.`;
    },
    setPhotosToActiveNote: (state, action) => {
      state.active.imageUrls = [
        ...state.active.imageUrls,
        ...action.payload,
      ];
      state.isSaving = false;
    },
    clearNotesLogout: (state) => {
      state.isSaving = false;
      state.messageSaved = "";
      state.notes = [];
      state.active = null;
    },
    deleteNoteById: (state, action) => {
      state.active = null;
      state.notes = state.notes.filter(
        (note) => note.id !== action.payload
      );
    },
  },
});

export const {
  addNewEmptyNote,
  clearNotesLogout,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setPhotosToActiveNote,
  setSaving,
  updateNote,
} = journalSlice.actions;
```

`src/journal/components/ImageGallery.jsx`

```jsx
import { ImageListItem, ImageList } from "@mui/material";

export const ImageGallery = ({ images }) => {
  return (
    <ImageList
      sx={{ width: "100%", height: 500 }}
      cols={4}
      rowHeight={200}
    >
      {images?👈👀.map((image) => (
        <ImageListItem key={image}>
          <img
            srcSet={`${image}?w=164&h=164&fit=crop&auto=format&dpr=2 2x`}
            src={`${image}?w=164&h=164&fit=crop&auto=format`}
            alt="Image of the note."
            loading="lazy"
          />
        </ImageListItem>
      ))}
    </ImageList>
  );
};
```

### 20.23 Nota deploy en Vercel

Si suben la app a Vercel y encuentran un problema al crear una nueva nota, pueden probar a solucionarlo agregando `imageUrls: []` en el archivo `store/journal/thunks.js` en la función `startNewNote`:

```jsx
const newNote = {
  title: "",
  body: "",
  imageUrls: [], 👈👀
  date: new Date().getTime(),
};
```

`src/store/journal/thunks.js`

```js
import {
  collection,
  deleteDoc,
  doc,
  setDoc,
} from "firebase/firestore/lite";
import { FirebaseDB } from "../../firebase/config";
import {
  addNewEmptyNote,
  deleteNoteById,
  savingNewNote,
  setActiveNote,
  setNotes,
  setPhotosToActiveNote,
  setSaving,
  updateNote,
} from "./journalSlice";
import { loadNotes } from "../../helpers/loadNotes";
import { fileUpload } from "../../helpers/fileUpload";

export const startNewNote = () => {
  return async (dispatch, getState) => {
    dispatch(savingNewNote());

    const { uid } = getState().auth;
    // uid

    const newNote = {
      title: "",
      body: "",
      imageUrls: [],
      date: new Date().getTime(),
    };

    const newDoc = doc(
      collection(FirebaseDB, `${uid}/journal/notes`)
    );

    // Para ver la info añadir variable y hacer console.log
    await setDoc(newDoc, newNote);

    newNote.id = newDoc.id;

    // dispatch
    dispatch(addNewEmptyNote(newNote));
    dispatch(setActiveNote(newNote));
  };
};

export const startLoadingNotes = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;

    if (!uid) throw new Error("The user uid doesn't exist");

    const notes = await loadNotes(uid);

    dispatch(setNotes(notes));
  };
};

export const startSaveNote = () => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    const { uid } = getState().auth;
    const { active: note } = getState().journal;

    const noteToFireStore = { ...note };
    delete noteToFireStore.id;

    const docRef = doc(
      FirebaseDB,
      `${uid}/journal/notes/${note.id}`
    );

    // Merge para mantener los campos existentes
    await setDoc(docRef, noteToFireStore, { merge: true });

    dispatch(updateNote(note));
  };
};

export const startUploadingFiles = (files = []) => {
  return async (dispatch, getState) => {
    dispatch(setSaving());

    // await fileUpload(files[0]);
    const fileUploadPromises = [];
    for (const file of files) {
      fileUploadPromises.push(fileUpload(file));
    }

    const photosUrls = await Promise.all(fileUploadPromises);

    dispatch(setPhotosToActiveNote(photosUrls));
  };
};

export const startDeletingNote = () => {
  return async (dispatch, getState) => {
    const { uid } = getState().auth;
    const { active: note } = getState().journal;

    const docRef = doc(
      FirebaseDB,
      `${uid}/journal/notes/${note.id}`
    );
    await deleteDoc(docRef);

    dispatch(deleteNoteById(note.id));
  };
};
```

### 20.24 Código fuente de la sección

Aquí les dejo el código fuente de la sección por si lo llegan a necesitar o comparar contra el mío.

[**Github: Fin Sección 20**](https://github.com/Klerith/react-journal-material/tree/fin-seccion-20)

## 🟡 21. Pruebas con Redux, Firebase, Firestore y autenticación

### 21.1 Introducción a la sección

### 21.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Profundizando en pruebas
- Pruebas en Firebase y Firestore
- Pruebas con reducers
- Variables de entorno de desarrollo, test y producción
- Pruebas en tareas asíncronas

Esta sección continúa el tema de las pruebas unitarias y de integración con el objetivo de seguir cubriendo temas nuevos. Las pruebas conforme se van avanzando, efectivamente se van haciendo más complejas pero la idea es darles a ustedes las herramientas para que puedan probar cualquier cosa que ustedes necesiten.

### 21.3 Configuración de Testing en Vite

En la próxima lección empezaré a realizar la configuración del testing, pero si quieren adelantarse, este es el Gist para la configuración inicial:

No olvidar ver: [[#5.7 Nota de Actualización - Extensión de archivos]]

[**Gist - Vite + Testing + Jest**](https://gist.github.com/Klerith/ca7e57fae3c9ab92ad08baadc6c26177)

### 21.4 Continuación de proyecto - JournalTesting

### 21.5 Configuración del testing

Ver [[#8.3 Configurar el ambiente de pruebas]]

```bash
npm install --save-dev
  jest 
  babel-jest 
  @babel/preset-env 
  @babel/preset-react 
  react-test-renderer

npm install --save-dev 
  @testing-library/react
  @testing-library/dom

npm install --save-dev 
  @types/jest
  jest-environment-jsdom
```

Luego de revisar e implementar la configuración:

```
npm test
```

### 21.6 Pruebas de carga de archivos

Estructura:

```bash
.
├── babel.config.cjs
├── eslint.config.js
├── index.html
├── jest.config.cjs
├── jest.setup.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
├── tests 👈👀👇
│   └── helpers
│       └── fileUpload.test.js
└── vite.config.js
```

`src/helpers/fileUpload.js`

```js
export const fileUpload = async (file) => {
  // if (!file) throw new Error("No files will be uploaded.");
  if (!file) return null;

  const cloudUrl =
    "https://api.cloudinary.com/v1_1/delkxyr6z/upload";

  const formData = new FormData();
  formData.append("upload_preset", "journal-app");
  formData.append("file", file);

  try {
    const resp = await fetch(cloudUrl, {
      method: "POST",
      body: formData,
    });

    if (!resp.ok)
      throw new Error("The image could not be uploaded.");

    const cloudResp = await resp.json();

    return cloudResp.secure_url;
  } catch (error) {
    // console.log(error);

    // throw new Error(error.message);

    return null;
  }
};
```

`tests/helpers/fileUpload.test.js`

```js
import { fileUpload } from "../../src/helpers/fileUpload";

describe("Tests in fileUpload", () => {
  test("The file should upload correctly to Cloudinary.", async () => {
    const imageUrl =
      "https://www.online-image-editor.com/styles/2019/images/power_girl.png";
    const resp = await fetch(imageUrl);
    const blob = await resp.blob();
    const file = new File([blob], "photo.jpg");

    const url = await fileUpload(file);

    expect(typeof url).toBe("string");
  });
});
```

### 21.7 Cloudinary SDK - Delete image

Elimina todas las imágenes de Cloudinary.

Revisa: `?/documentation/Node.js`

**Node.js SDK**

```bash
npm install cloudinary

npm install -D cloudinary
yarn add -D cloudinary
```

Busca: `Delete resources by public ID`

Instala: `setInmediate`

```bash
npm i setimmediate
npm i -D setimmediate
npm install -D setimmediate
```

`jest.config.cjs`

```cjs
module.exports = {
  testEnvironment: "jest-environment-jsdom",
  setupFiles: ["./jest.setup.js"],
};
```

`jest.setup.js`

```js
// En caso de necesitar la implementación del FetchAPI
import "whatwg-fetch"; // yarn add whatwg-fetch
import "setimmediate"; // npm i -D setimmediate
```

`tests/helpers/fileUpload.test.js`

```js
import { v2 as cloudinary } from "cloudinary";
import { fileUpload } from "../../src/helpers/fileUpload";

cloudinary.config({
  cloud_name: "delkxyr6z",
  api_key: "423579532613278",
  api_secret: "k-ZUekWF7jbsR1Jm91rIe2P5cd8",
  secure: true,
});

describe("Tests in fileUpload", () => {
  test("The file should upload correctly to Cloudinary.", async () => {
    const imageUrl =
      "https://www.online-image-editor.com/styles/2019/images/power_girl.png";
    const resp = await fetch(imageUrl);
    const blob = await resp.blob();
    const file = new File([blob], "photo.png");

    const url = await fileUpload(file);

    expect(typeof url).toBe("string");

    // console.log(url);
    const segments = url.split("/");
    const imageId = segments[segments.length - 1].replace(
      ".png",
      ""
    );

    // const cloudResp = await cloudinary.api.delete_resources(
    //   ["journal/" + imageId],
    //   {
    //     resource_type: "image",
    //   }
    // );

    const cloudResp = await cloudinary.api.delete_resources([
      imageId,
    ]);

    console.log({ cloudResp });
  });

  test("It must return null.", async () => {
    const file = new File([], "photo.png");
    const url = await fileUpload(file);

    expect(url).toBe(null);
  });
});
```

### 21.8 Pruebas con los Slices de Redux Toolkit

Estructura:

```bash
.
├── babel.config.cjs
├── eslint.config.js
├── index.html
├── jest.config.cjs
├── jest.setup.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
├── tests
│   ├── fixtures 👈👀👇
│   │   └── authFixtures.js
│   ├── helpers
│   │   └── fileUpload.test.js
│   └── store 👈👀👇
│       └── auth
│           └── authSlice.test.js
└── vite.config.js
```

`tests/Fixtures/authFixtures.js`

```js
export const initialState = {
  status: "checking",
  uid: null,
  email: null,
  displayName: null,
  photoURL: null,
  errorMessage: null,
};

export const authenticatedState = {
  status: "authenticated",
  uid: "123ABC",
  email: "demo@google.com",
  displayName: "Demo User",
  photoURL: "https://demo.jpg",
  errorMessage: null,
};

export const notAuthenticatedState = {
  status: "not-authenticated",
  uid: null,
  email: null,
  displayName: null,
  photoURL: null,
  errorMessage: null,
};

export const demoUser = {
  uid: "ABC123",
  email: "demo@google.com",
  displayName: "Demo User",
  photoURL: "https://demo.jpg",
};
```

`tests/store/auth/authSlice.test.js`

```js
import { authSlice } from "../../../src/store/auth/authSlice";
import { initialState } from "../../fixtures/authFixtures";

describe("Tests in authSlice", () => {
  test("It must return to its initial state and be called auth.", () => {
    const state = authSlice.reducer(initialState, {});

    expect(state).toEqual(initialState);
    expect(authSlice.name).toBe("auth");
  });
});
```

### 21.9 Pruebas faltantes con el authSlice

`tests/store/auth/authSlice.test.js`

```js
import {
  authSlice,
  checkingCredentials,
  login,
  logout,
} from "../../../src/store/auth/authSlice";
import {
  authenticatedState,
  demoUser,
  initialState,
} from "../../fixtures/authFixtures";

describe("Tests in authSlice", () => {
  test("It must return to its initial state and be called auth.", () => {
    const state = authSlice.reducer(initialState, {});

    expect(state).toEqual(initialState);
    expect(authSlice.name).toBe("auth");
  });

  test("It must perform authentication.", () => {
    const state = authSlice.reducer(
      initialState,
      login(demoUser)
    );
    // console.log(login(demoUser));

    expect(state).toEqual({
      status: "authenticated",
      uid: demoUser.uid,
      email: demoUser.email,
      displayName: demoUser.displayName,
      photoURL: demoUser.photoURL,
      errorMessage: null,
    });
  });

  test("It must log out without arguments.", () => {
    // authenticatedState // logout without arguments
    const state = authSlice.reducer(
      authenticatedState,
      logout()
    );

    expect(state).toEqual({
      status: "not-authenticated",
      uid: null,
      email: null,
      displayName: null,
      photoURL: null,
      errorMessage: undefined,
    });
  });

  test("It should log it out and display an error message.", () => {
    // authenticatedState // logout without arguments
    const errorMessage = "The credentials are not correct.";

    const state = authSlice.reducer(
      authenticatedState,
      logout({ errorMessage })
    );

    expect(state).toEqual({
      status: "not-authenticated",
      uid: null,
      email: null,
      displayName: null,
      photoURL: null,
      errorMessage: errorMessage,
    });
  });

  test("It must change the status to checking.", () => {
    const state = authSlice.reducer(
      authenticatedState,
      checkingCredentials()
    );

    expect(state.status).toBe("checking");
  });
});
```

### 21.10 Pruebas sobre Thunks

Estructura:

```bash
.
├── babel.config.cjs
├── eslint.config.js
├── index.html
├── jest.config.cjs
├── jest.setup.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
├── tests
│   ├── fixtures
│   │   └── authFixtures.js
│   ├── helpers
│   │   └── fileUpload.test.js
│   └── store
│       └── auth
│           ├── authSlice.test.js
│           └── thunks.test.js 👈👀
└── vite.config.js
```

`jest.config.cjs`

```js
module.exports = {
  testEnvironment: "jest-environment-jsdom",
  setupFiles: ["./jest.setup.js"],
  transformIgnorePatterns: [],
};
```

`tests/store/auth/thunks.test.js`

```js
import { checkingCredentials } from "../../../src/store/auth/authSlice";
import { checkingAuthentication } from "../../../src/store/auth/thunks";

jest.mock("../../../src/firebase/providers");

describe("Tests in AuthThunks.", () => {
  const dispatch = jest.fn();

  beforeEach(() => jest.clearAllMocks());

  test("It must invoke checkingCredentials.", async () => {
    // checkingAuthentication();
    await checkingAuthentication()(dispatch);

    expect(dispatch).toHaveBeenCalledWith(
      checkingCredentials()
    );
  });
});
```

### 21.11 Thunks - checkingCredentials correcto e incorrecto

`src/store/auth/thunks.js`

```js
import {
  singInWithGoogle,
  registerUserWithEmailPassword,
  loginWithEmailPassword,
  logoutFirebase,
} from "../../firebase/providers";
import { clearNotesLogout } from "../journal/journalSlice";
import {
  checkingCredentials,
  login,
  logout,
} from "./authSlice";

export const checkingAuthentication = (email, password) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());
  };
};

export const startGoogleSignIn = () => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await singInWithGoogle();

    // console.log({ result }); 👈👀

    if (!result.ok)
      return dispatch(logout(result.errorMessage));

    dispatch(login(result));
  };
};

export const startCreatingUserWithEmailPassword = ({
  email,
  password,
  displayName,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const { ok, uid, photoURL, errorMessage } =
      await registerUserWithEmailPassword({
        email,
        password,
        displayName,
      });

    if (!ok) return dispatch(logout({ errorMessage }));

    dispatch(login({ uid, displayName, email, photoURL }));
  };
};

export const startLoginWithEmailPassword = ({
  email,
  password,
}) => {
  return async (dispatch) => {
    dispatch(checkingCredentials());

    const result = await loginWithEmailPassword({
      email,
      password,
    });

    if (!result.ok) return dispatch(logout(result));

    dispatch(login(result));
  };
};

export const startLogout = () => {
  return async (dispatch) => {
    await logoutFirebase();

    dispatch(clearNotesLogout());

    dispatch(logout());
  };
};
```

`tests/store/auth/thunks.test.js`

```js
import { singInWithGoogle } from "../../../src/firebase/providers";
import {
  checkingCredentials,
  login,
  logout,
} from "../../../src/store/auth/authSlice";
import {
  checkingAuthentication,
  startGoogleSignIn,
} from "../../../src/store/auth/thunks";
import { demoUser } from "../../fixtures/authFixtures";

jest.mock("../../../src/firebase/providers");

describe("Tests in AuthThunks.", () => {
  const dispatch = jest.fn();

  beforeEach(() => jest.clearAllMocks());

  test("It must invoke checkingCredentials.", async () => {
    // checkingAuthentication();
    await checkingAuthentication()(dispatch);

    expect(dispatch).toHaveBeenCalledWith(
      checkingCredentials()
    );
  });

  test("startGoogleSignIn must call checkingCredentials and login - Success", async () => {
    const loginData = { ok: true, ...demoUser };
    await singInWithGoogle.mockResolvedValue(loginData);

    //  thunk
    await startGoogleSignIn()(dispatch);

    expect(dispatch).toHaveBeenCalledWith(
      checkingCredentials()
    );
    expect(dispatch).toHaveBeenCalledWith(login(loginData));
  });

  test("startGoogleSignIn must call checkingCredentials and logout - Error", async () => {
    const loginData = {
      ok: false,
      errorMessage: "An error in Google",
    };

    await singInWithGoogle.mockResolvedValue(loginData);

    //  thunk
    await startGoogleSignIn()(dispatch);

    expect(dispatch).toHaveBeenCalledWith(
      checkingCredentials()
    );
    expect(dispatch).toHaveBeenCalledWith(
      logout(loginData.errorMessage)
    );
  });
});
```

### 21.12 Thunks - startLoginWithEmailPassword

`tests/store/auth/thunks.test.js`

```jsx
import {
  loginWithEmailPassword,
  logoutFirebase,
  singInWithGoogle,
} from "../../../src/firebase/providers";
import {
  checkingCredentials,
  login,
  logout,
} from "../../../src/store/auth/authSlice";
import {
  checkingAuthentication,
  startGoogleSignIn,
  startLoginWithEmailPassword,
  startLogout,
} from "../../../src/store/auth/thunks";
import { clearNotesLogout } from "../../../src/store/journal/journalSlice";
import { demoUser } from "../../fixtures/authFixtures";

jest.mock("../../../src/firebase/providers");

describe("Tests in AuthThunks.", () => {
  const dispatch = jest.fn();

  beforeEach(() => jest.clearAllMocks());

  test("It must invoke checkingCredentials.", async () => {
    // checkingAuthentication();
    await checkingAuthentication()(dispatch);

    expect(dispatch).toHaveBeenCalledWith(
      checkingCredentials()
    );
  });

  test("startGoogleSignIn must call checkingCredentials and login - Success", async () => {
    const loginData = { ok: true, ...demoUser };
    await singInWithGoogle.mockResolvedValue(loginData);

    //  thunk
    await startGoogleSignIn()(dispatch);

    expect(dispatch).toHaveBeenCalledWith(
      checkingCredentials()
    );
    expect(dispatch).toHaveBeenCalledWith(login(loginData));
  });

  test("startGoogleSignIn must call checkingCredentials and logout - Error", async () => {
    const loginData = {
      ok: false,
      errorMessage: "An error in Google",
    };

    await singInWithGoogle.mockResolvedValue(loginData);

    //  thunk
    await startGoogleSignIn()(dispatch);

    expect(dispatch).toHaveBeenCalledWith(
      checkingCredentials()
    );
    expect(dispatch).toHaveBeenCalledWith(
      logout(loginData.errorMessage)
    );
  });

  test("StartLoginWithEmailPassword must call checkingCredentials and login - Exito", async () => {
    const loginData = { ok: true, ...demoUser };
    const formData = {
      email: demoUser.email,
      password: "123456",
    };

    await loginWithEmailPassword.mockResolvedValue(loginData);
    await startLoginWithEmailPassword(formData)(dispatch);

    expect(dispatch).toHaveBeenCalledWith(
      checkingCredentials()
    );
    expect(dispatch).toHaveBeenCalledWith(login(loginData));
  });

  test("startLogout must call logoutFirebase, clearNotes and logout", async () => {
    await startLogout()(dispatch);

    expect(logoutFirebase).toHaveBeenCalled();
    expect(dispatch).toHaveBeenCalledWith(clearNotesLogout());
    expect(dispatch).toHaveBeenCalledWith(logout());
  });
});
```

### 21.13 Pruebas en Journal Thunks

Estructura:

```bash
.
├── babel.config.cjs
├── eslint.config.js
├── index.html
├── jest.config.cjs
├── jest.setup.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
├── tests
│   ├── fixtures
│   │   └── authFixtures.js
│   ├── helpers
│   │   └── fileUpload.test.js
│   └── store
│       ├── auth
│       │   ├── authSlice.test.js
│       │   └── thunks.test.js
│       └── journal 👈👀👇
│           └── thunks.test.js
└── vite.config.js
```

`tests/store/journal/thunks.test.js`

```js
import { startNewNote } from "../../../src/store/journal/thunks";

describe("Tests in Journal Thunks", () => {
  const dispatch = jest.fn();
  const getState = jest.fn();

  beforeEach(() => jest.clearAllMocks());

  test("startNewNote must create a new blank note", async () => {
    const uid = "TEST-UID";

    getState.mockReturnValue({ auth: { uid } });
    await startNewNote()(dispatch, getState);
  });
});
```

Para esta prueba vamos a Firebase y cambiamos las reglas para que pasen.

`JournalApp/Firestore Database/Reglas`

```js
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null; 👈👀
    }
  }
}

/* Changes: Publicar */
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true; 👈👀
    }
  }
}
```

Ahora, al revisar en Datos, puedes ver la nota `TEST-UID`. Pero como esto no es muy seguro regresamos a las `Reglas`, entramos a la fecha anterior al cambio actual y le damos en `Comparar con las más recientes`. Si no te sale `publicar` edita las reglas más recientes y déjalo con el código anterior.

```js
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null; 👈👀
    }
  }
}
```

### 21.14 Crear base de datos de testing

Ingresa a cualquier proyecto creado en `Firebase` o crea uno desde 0. Sigue estos pasos: [[#20.5 Preparar la base de datos - CloudFirestore#1. Crear base de datos]]

`Firestore Database/Reglas`

```js
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write;
    }
  }
}
```

`⚙️/Configuración del proyecto/General/Tus apps/(</>) web`

Agrega Firebase a tu app web:
- Registrar app: `react-testing`
- [ ] Además, configura Firebase Hosting (no marcar)
- Registrar app

En esta sección solo necesitamos copiar `firebaseConfig`

```js
// Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: "AIzaSdsfHZgelzrA7JRP0rrRtMVMlslgJY9I8jA",
  authDomain: "appcompras-254fb.firebaseapp.com",
  databaseURL: "https://appcompras-254fb-default-rtdb.firebaseio.com",
  projectId: "appcompras-254fb",
  storageBucket: "appcompras-254fb.firebasestorage.app",
  messagingSenderId: "365421874604",
  appId: "1:365432679604:web:49ef886549d7673fc67cc8"
};
```

- Ir a la consola

`src/firebase/config.js`

```js
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";
import { getFirestore } from "firebase/firestore/lite";

// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
// const firebaseConfig = {
//   apiKey: "AIzaSdsfHZgelzrA7JRP0rrRtMVMlslgJY9I8jA",
//   authDomain: "journalapp-254fb.firebaseapp.com",
//   projectId: "journalapp-254fb",
//   storageBucket: "journalapp-254fb.firebasestorage.app",
//   messagingSenderId: "365421874604",
//   appId: "1:365432679604:web:49ef886549d7673fc67cc8",
// };

// Testing
// Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: "AIzaSdsfHZgelzrA7JRP0rrRtMVMlslgJY9I8jA",
  authDomain: "appcompras-254fb.firebaseapp.com",
  databaseURL:
    "https://appcompras-254fb-default-rtdb.firebaseio.com",
  projectId: "appcompras-254fb",
  storageBucket: "appcompras-254fb.firebasestorage.app",
  messagingSenderId: "365421874604",
  appId: "1:365432679604:web:49ef886549d7673fc67cc8",
};

// Initialize Firebase
export const FirebaseApp = initializeApp(firebaseConfig);
export const FirebaseAuth = getAuth(FirebaseApp);
export const FirebaseDB = getFirestore(FirebaseApp);
```

Luego:

```bash
# Ejecutar las pruebas
npm test
```

`Firestore Database/Datos`

Parece `TEST-UID`

📌 Para esta clase usé `appcompras` como sujeto de pruebas.

### 21.15 Prueba completa sobre inserción

`tests/store/journal/thunks.test.js`

```js
import {
  collection,
  deleteDoc,
  getDocs,
} from "firebase/firestore/lite";
import {
  addNewEmptyNote,
  savingNewNote,
  setActiveNote,
} from "../../../src/store/journal/journalSlice";
import { startNewNote } from "../../../src/store/journal/thunks";
import { FirebaseDB } from "../../../src/firebase/config";

describe("Tests in Journal Thunks", () => {
  const dispatch = jest.fn();
  const getState = jest.fn();

  beforeEach(() => jest.clearAllMocks());

  test("startNewNote must create a new blank note", async () => {
    const uid = "TEST-UID";

    getState.mockReturnValue({ auth: { uid } });
    await startNewNote()(dispatch, getState);

    expect(dispatch).toHaveBeenCalledWith(savingNewNote());
    expect(dispatch).toHaveBeenCalledWith(
      addNewEmptyNote({
        body: "",
        title: "",
        imageUrls: [],
        id: expect.any(String),
        date: expect.any(Number),
      })
    );

    expect(dispatch).toHaveBeenCalledWith(
      setActiveNote({
        body: "",
        title: "",
        imageUrls: [], 👈👀 
        id: expect.any(String),
        date: expect.any(Number),
      })
    );

    // Delete from Firebase
    const collectionRef = collection(
      FirebaseDB,
      `${uid}/journal/notes`
    );
    const docs = await getDocs(collectionRef);

    const deletePromises = [];
    docs.forEach((doc) =>
      deletePromises.push(deleteDoc(doc.ref))
    );

    await Promise.all(deletePromises);
  });
});
```

Si revisas `Firestore Database/Datos` se habrán eliminado todas las inserciones.

### 21.16 Variables de entorno

Son **valores configurables** que se definen fuera del código fuente y afectan el comportamiento de una aplicación.  

Ejemplo clásico:

- `NODE_ENV=production` → indica que la app corre en modo producción.
- `API_URL=https://api.midominio.com` → evita poner URLs fijas en el código.

Sirven para **separar configuración del código**, facilitando:

- Cambiar claves, rutas o credenciales sin tocar el código.
- Manejar diferentes entornos (desarrollo, pruebas, producción).
- Mantener secretos fuera del repositorio (aunque lo ideal es usar un gestor seguro como Vault).

Normalmente, se guardan en archivos `.env` o se definen en el sistema operativo.

Estructura:

```bash
.
├── babel.config.cjs
├── .env 👈👀
├── .env.test 👈👀
├── eslint.config.js
├── index.html
├── jest.config.cjs
├── jest.setup.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
├── tests
└── vite.config.js
```

Para esta clase cancela las pruebas y ejecuta:

```bash
npm dev
```

Para acceder a variables de entorno, podemos escribir en cualquier archivo `.js` o `.jsx` que se esté ejecutando:

```js
console.log(import.meta.env);
console.log(import.meta.env.MODE);
```

Si a lo anterior le sumamos esto en el archivo `.env`

`.env/`

```
PROPIEDAD_PRIVADA=I am private

# Para verlo desde Fronted
VITE_HOLA=World in Production!!!
```

Vemos en la consola del navegador:

```js
{
  BASE_URL: "/",
  DEV: true,
  MODE: "development",
  PROD: false,
  SSR: false,
  VITE_HOLA: "World in Production!!!",
  [[Prototype]]: Object,
};

development
```

Ahora si ejecutamos nuestras pruebas con `npm test` nos da algunos errores sin importar cuál prueba sea ejecutada.

#### Errores con mis versiones de React

El error principal es este:

```js
Incompatible React versions: The "react" and "react-dom" packages must have the exact same version.
  - react:      19.1.1
  - react-dom:  19.0.0
```

React y ReactDOM **deben estar siempre en la misma versión exacta**.  
Al ser este un proyecto que empecé hace meses tengo:

- `react` en **19.0.0**
- `react-dom` en **19.0.0**
- `react-test-renderer` en **19.1.1**

```js
{
  name: "08-journal-app",
  private: true,
  version: "0.0.0",
  type: "module",
  scripts: {
    dev: "vite",
    build: "vite build",
    lint: "eslint .",
    preview: "vite preview",
    test: "jest --watchAll",
  },
  dependencies: {
    "react": "^19.0.0", 👈👀
    "react-dom": "^19.0.0", 👈👀
  },
  devDependencies: {
    "react-test-renderer": "^19.1.1", 👈👀
  },
};
```

Para solucionarlo, eliminé la carpeta `node_modules` y el archivo `package-lock.json`:

```bash
rm -rf node_modules package-lock.json
```

Luego:

```bash
npm install react@19.1.1 react-dom@19.1.1
npm install react-test-renderer@19.1.1 --save-dev

npm install
```

### 21.17 Variables de entorno Testing y Development

Estructura:

```bash
.
├── babel.config.cjs
├── .env
├── .env.test
├── eslint.config.js
├── .git
├── .gitignore
├── index.html
├── jest.config.cjs
├── jest.setup.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── App.jsx
│   ├── auth
│   │   ├── layout
│   │   │   └── AuthLayout.jsx
│   │   ├── pages
│   │   │   ├── LoginPage.jsx
│   │   │   └── RegisterPage.jsx
│   │   └── routes
│   │       └── AuthRoutes.jsx
│   ├── firebase
│   │   ├── config.js
│   │   └── providers.js
│   ├── helpers
│   │   ├── fileUpload.js
│   │   ├── getEnvironments.js 👈👀
│   │   └── loadNotes.js
│   ├── hooks
│   │   ├── useCheckAuth.js
│   │   └── useForm.js
│   ├── journal
│   │   ├── components
│   │   │   ├── ImageGallery.jsx
│   │   │   ├── NavBar.jsx
│   │   │   ├── SideBarItem.jsx
│   │   │   └── SideBar.jsx
│   │   ├── layout
│   │   │   └── JournalLayout.jsx
│   │   ├── pages
│   │   │   └── JournalPage.jsx
│   │   ├── routes
│   │   │   └── JournalRoutes.jsx
│   │   └── views
│   │       ├── NoteView.jsx
│   │       └── NothingSelectedView.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   ├── authSlice.js
│   │   │   └── thunks.js
│   │   ├── journal
│   │   │   ├── journalSlice.js
│   │   │   └── thunks.js
│   │   └── store.js
│   ├── styles.css
│   ├── theme
│   │   ├── purpleTheme.js
│   │   └── Theme.jsx
│   └── ui
│       └── components
│           └── CheckingAuth.jsx
├── tests
└── vite.config.js
```

Instalar [`dotenv`](https://www.npmjs.com/package/dotenv)

```bash
npm i dotenv --save-dev
npm i dotenv -D
```

`jest.setup.js`

```js
// En caso de necesitar la implementación del FetchAPI
import "whatwg-fetch"; // yarn add whatwg-fetch
import "setimmediate"; // npm i -D setimmediate

require("dotenv").config({
  path: ".env.test",
});

jest.mock("./src/helpers/getEnvironments", () => ({
  getEnvironments: () => ({ ...process.env }),
}));
```

`.env.test`

```js
VITE_HOLA=Testing in Production!!!
VITE_JWT_SEED=Docs...
```

`src/firebase/config.js`

```js
// Añadimos esto para probar
const env = getEnvironments();
console.log(env);
```

`src/helpers/getEnvironments.js`

```js
export const getEnvironments = () => {
  import.meta.env;

  return {
    ...import.meta.env
  }
};
```

Volvemos a ejecutar las pruebas:

```bash
npm test
```

#### Error al instalar paquetes

Al ejecutar `npm i dotenv --save-dev` para instalar `dotenv` salía este mensaje.

```bash
Did you mean this?
  npm install # Install a package
To see a list of supported npm commands, run:
  npm help
```

Lo que hice fue actualizar `npm` de `11.4.2` a `11.6.0`.

```bash
npm -v
11.4.2

# Actualiza
npm install -g npm@latest

npm -v
11.6.0

# Intenta nuevamente
npm install --save-dev dotenv
```

### 21.18 Configurar variables de entorno de Firebase

Estructura:

```bash
.
├── babel.config.cjs
├── .env
├── .env.template 👈👀
├── .env.test
├── eslint.config.js
├── .git
├── .gitignore
├── index.html
├── jest.config.cjs
├── jest.setup.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
├── tests
└── vite.config.js
```

`.gitignore`

```
# dotenv environment variable files
.env
.env.*
!.env.example
```

`src/firebase/config.js`

```js
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";
import { getFirestore } from "firebase/firestore/lite";
import { getEnvironments } from "../helpers/getEnvironments";

// Use "Uppercase" to convert to uppercase letters 
const {
  VITE_APIKEY,
  VITE_AUTHDOMAIN,
  VITE_DATABASEURL,
  VITE_PROJECTID,
  VITE_STORAGEBUCKET,
  VITE_MESSAGINGSENDERID,
  VITE_APPID,
} = getEnvironments(); 👈👀
// console.log(env);

// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
// const firebaseConfig = {
//   ...
// };

// Testing

// Your web app's Firebase configuration
// const firebaseConfig = {
//   ...
// };

// Copy the keys from the firebaseConfig object
const firebaseConfig = { 
  apiKey: VITE_APIKEY,
  authDomain: VITE_AUTHDOMAIN,
  databaseURL: VITE_DATABASEURL,
  projectId: VITE_PROJECTID,
  storageBucket: VITE_STORAGEBUCKET,
  messagingSenderId: VITE_MESSAGINGSENDERID,
  appId: VITE_APPID,
}; 👈👀☝️

// console.log(firebaseConfig );

// Initialize Firebase
export const FirebaseApp = initializeApp(firebaseConfig);
export const FirebaseAuth = getAuth(FirebaseApp);
export const FirebaseDB = getFirestore(FirebaseApp);
```

`.env`

```
PROPIEDAD_PRIVADA=I am private

# To view it from Fronted
VITE_HOLA=World in Production!!!

# Copy of the main configuration of our project.
VITE_APIKEY="AIzaSylZD4Stp-8992mpBJW6-4EwgwASeKqXnMw"
VITE_AUTHDOMAIN="journalapp-72f2d.firebaseapp.com"
VITE_PROJECTID="journalapp-72f2d"
VITE_STORAGEBUCKET="journalapp-72f2d.firebasestorage.app"
VITE_MESSAGINGSENDERID="33342861287"
VITE_APPID="1:339972861287:web:4ac56da1de5f56a6bc53c2"
```

`.env.test`

```VITE_HOLA=Testing in Production!!!
VITE_JWT_SEED=Docs...

# Copy of firebaseConfig for testing
VITE_APIKEY= "AD1aSyCYxsdfs3A7JRP033RtMVMls4dJY9I8jA"
VITE_AUTHDOMAIN= "appcompras-518fb.firebaseapp.com"
VITE_DATABASEURL= "https://appcompras-518fb-default-rtdb.firebaseio.com",
VITE_PROJECTID= "appcompras-518fb"
VITE_STORAGEBUCKET= "appcompras-518fb.firebasestorage.app"
VITE_MESSAGINGSENDERID= "3654274329609"
VITE_APPID= "1:365427579609:web:49ef88123s7673fc67cc8"
```

`.env.template`

```
PROPIEDAD_PRIVADA=I am private

# To view it from Fronted
VITE_HOLA=World in Production!!!

VITE_APIKEY=""
VITE_AUTHDOMAIN=""
VITE_PROJECTID=""
VITE_STORAGEBUCKET=""
VITE_MESSAGINGSENDERID=""
VITE_APPID=""
```

### 21.19 Pruebas en el LoginPage

Estructura:

```bash
.
├── babel.config.cjs
├── .env
├── .env.template
├── .env.test
├── eslint.config.js
├── .git
├── .gitignore
├── index.html
├── jest.config.cjs
├── jest.setup.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
├── tests
│   ├── auth 👈👀👇
│   │   └── pages
│   │       └── LoginPage.test.jsx
│   ├── fixtures
│   │   └── authFixtures.js
│   ├── helpers
│   │   └── fileUpload.test.js
│   └── store
│       ├── auth
│       │   ├── authSlice.test.js
│       │   └── thunks.test.js
│       └── journal
│           └── thunks.test.js
└── vite.config.js
```

`tests/auth/pages/LoginPage.test.jsx`

```jsx
import { render, screen } from "@testing-library/react";
import { Provider } from "react-redux";
import { configureStore } from "@reduxjs/toolkit";
import { MemoryRouter } from "react-router-dom";

import { LoginPage } from "../../../src/auth/pages/LoginPage";
import { authSlice } from "../../../src/store/auth/authSlice";

const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
    // preloadedState: {},
  },
});

describe("Testing on LoginPage", () => {
  test("It should display the component correctly", () => {
    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );
    // screen.debug();
    expect(
      screen.getAllByText("Login").length
    ).toBeGreaterThanOrEqual(1);
  });
});
```

#### Error TextEncoder is not defined

```bash
 FAIL  tests/auth/pages/LoginPage.test.jsx
  ● Test suite failed to run

    ReferenceError: TextEncoder is not defined
```

Para solucionarlo ver  [[#16.6 Pruebas en el PublicRoute#ReferenceError `TextEncoder` is not defined]]

`jest.setup.js`

```js
// En caso de necesitar la implementación del FetchAPI
import "whatwg-fetch"; // yarn add whatwg-fetch
import "setimmediate"; // npm i -D setimmediate

require("dotenv").config({
  path: ".env.test",
});

jest.mock("./src/helpers/getEnvironments", () => ({
  getEnvironments: () => ({ ...process.env }),
}));

// Solution TextEncoder is not defined 👈👀👇
import { TextDecoder, TextEncoder } from "util";
global.TextEncoder = TextEncoder;
global.TextDecoder = TextDecoder;
```

### 21.20 Botón de Google debe de llamar startGoogleSignIn

`src/auth/pages/LoginPage.jsx`

```jsx
import { useMemo } from "react";
import { useDispatch, useSelector } from "react-redux";
import { Link as RouterLink } from "react-router";
import {
  TextField,
  Grid2,
  Button,
  Link,
  Box,
  Alert,
} from "@mui/material";
import { Google } from "@mui/icons-material";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import {
  startGoogleSignIn,
  startLoginWithEmailPassword,
} from "../../store/auth/thunks";

const formDate = {
  email: "",
  password: "",
};

export const LoginPage = () => {
  const { status, errorMessage } = useSelector(
    (state) => state.auth
  );

  const dispatch = useDispatch();

  const { email, password, handleInputChange } =
    useForm(formDate);

  const isAuthenticating = useMemo(
    () => status === "checking",
    [status]
  );

  // const { status } = useSelector((state) => state.auth);

  // console.log(email, password);

  const handleSubmit = (event) => {
    event.preventDefault();

    //! This isn't the action to be dispatched
    // dispatch(checkingAuthentication());
    dispatch(
      startLoginWithEmailPassword({ email, password })
    );
  };

  const handleGoogleSignIn = () => {
    console.log("handleGoogleSignIn");

    dispatch(startGoogleSignIn());
  };

  // useEffect(() => {
  //   dispatch(checkingAuthentication());
  // }, []);

  return (
    <AuthLayout title="Login">
      <form
        action=""
        onSubmit={handleSubmit}
        className="animate__animated animate__fadeIn animate__faster"
      >
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              name="password"
              value={password}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>
        {/* New */}
        <Box>
          <Grid2
            size={{ xs: 12 }}
            display={!!errorMessage ? "" : "none"}
            sx={{
              mt: 1,
            }}
          >
            <Alert severity="error">{errorMessage}</Alert>
          </Grid2>
          <Grid2 container spacing={2} sx={{ mt: 2 }}>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                type="submit"
                variant="contained"
                fullWidth
              >
                Login
              </Button>
            </Grid2>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                variant="contained"
                fullWidth
                aria-label="google-btn" 👈👀
                startIcon={<Google />}
                onClick={handleGoogleSignIn}
              >
                Google
              </Button>
            </Grid2>
          </Grid2>
          <Grid2
            container
            // direction="row"
            justifyContent="end"
            sx={{ mt: 2 }}
          >
            <Link
              component={RouterLink}
              color="inherit"
              to="/auth/register"
            >
              Create an account.
            </Link>
          </Grid2>
        </Box>
      </form>
    </AuthLayout>
  );
};
```

`tests/auth/pages/LoginPage.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { Provider } from "react-redux";
import { configureStore } from "@reduxjs/toolkit";
import { MemoryRouter } from "react-router-dom";

import { LoginPage } from "../../../src/auth/pages/LoginPage";
import { authSlice } from "../../../src/store/auth/authSlice";
import { notAuthenticatedState } from "../../fixtures/authFixtures";

const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
  },
  preloadedState: {
    auth: notAuthenticatedState,
  },
});

describe("Testing on LoginPage", () => {
  test("It should display the component correctly", () => {
    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );
    // screen.debug();
    expect(
      screen.getAllByText("Login").length
    ).toBeGreaterThanOrEqual(1);
  });

  test("The Google button should call startGoogleSignIn", () => {
    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );

    // screen.debug()

    const googleBtn = screen.getByLabelText("google-btn");

    fireEvent.click(googleBtn);

    // screen.debug();
  });
});
```

### 21.21 Mocks de useDispatch

`tests/auth/pages/LoginPage.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { Provider } from "react-redux";
import { configureStore } from "@reduxjs/toolkit";
import { MemoryRouter } from "react-router-dom";

import { LoginPage } from "../../../src/auth/pages/LoginPage";
import { authSlice } from "../../../src/store/auth/authSlice";
import { notAuthenticatedState } from "../../fixtures/authFixtures";

// It is important to put the word "mock" first.
const mockStartGoogleSignIn = jest.fn();

jest.mock("../../../src/store/auth/thunks", () => ({
  startGoogleSignIn: () => mockStartGoogleSignIn,
}));

const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
  },
  preloadedState: {
    auth: notAuthenticatedState,
  },
});

describe("Testing on LoginPage", () => {
  test("It should display the component correctly", () => {
    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );
    // screen.debug();
    expect(
      screen.getAllByText("Login").length
    ).toBeGreaterThanOrEqual(1);
  });

  test("The Google button should call startGoogleSignIn", () => {
    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );

    // screen.debug()
    // console.log(store.getState());

    const googleBtn = screen.getByLabelText("google-btn");
    fireEvent.click(googleBtn);

    // screen.debug();

    // console.log(store.getState());

    expect(mockStartGoogleSignIn).toHaveBeenCalled();
    // expect(mockStartGoogleSignIn).toHaveBeenCalledWith();
  });
});
```

### 21.22 Disparar el submit del formulario

`src/auth/pages/LoginPage.jsx`

```jsx
import { useMemo } from "react";
import { useDispatch, useSelector } from "react-redux";
import { Link as RouterLink } from "react-router";
import {
  TextField,
  Grid2,
  Button,
  Link,
  Box,
  Alert,
} from "@mui/material";
import { Google } from "@mui/icons-material";
import { AuthLayout } from "../layout/AuthLayout";
import { useForm } from "../../hooks/useForm";
import {
  startGoogleSignIn,
  startLoginWithEmailPassword,
} from "../../store/auth/thunks";

const formDate = {
  email: "",
  password: "",
};

export const LoginPage = () => {
  const { status, errorMessage } = useSelector(
    (state) => state.auth
  );

  const dispatch = useDispatch();

  const { email, password, handleInputChange } =
    useForm(formDate);

  const isAuthenticating = useMemo(
    () => status === "checking",
    [status]
  );

  // const { status } = useSelector((state) => state.auth);

  // console.log(email, password);

  const handleSubmit = (event) => {
    event.preventDefault();

    //! This isn't the action to be dispatched
    // dispatch(checkingAuthentication());

    console.log({ email, password }); 👈👀

    dispatch(
      startLoginWithEmailPassword({ email, password })
    );
  };

  const handleGoogleSignIn = () => {
    console.log("handleGoogleSignIn");

    dispatch(startGoogleSignIn());
  };

  // useEffect(() => {
  //   dispatch(checkingAuthentication());
  // }, []);

  return (
    <AuthLayout title="Login">
      <form
        aria-label="submit-form" 👈👀
        action=""
        onSubmit={handleSubmit}
        className="animate__animated animate__fadeIn animate__faster"
      >
        <Grid2
          container
          // component="form"
          spacing={2}
        >
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="email"
              label="Email"
              type="email"
              placeholder="email@google.com"
              size="small"
              fullWidth
              name="email"
              value={email}
              onChange={handleInputChange}
            />
          </Grid2>
          <Grid2 size={{ xs: 12, md: 6 }}>
            <TextField
              id="password"
              label="Password"
              type="password"
              placeholder="password"
              size="small"
              fullWidth
              slotProps={{ 👈👀👇
                input: { "data-testid": "password" },
              }}
              name="password"
              value={password}
              onChange={handleInputChange}
            />
          </Grid2>
        </Grid2>
        {/* New */}
        <Box>
          <Grid2
            size={{ xs: 12 }}
            display={!!errorMessage ? "" : "none"}
            sx={{
              mt: 1,
            }}
          >
            <Alert severity="error">{errorMessage}</Alert>
          </Grid2>
          <Grid2 container spacing={2} sx={{ mt: 2 }}>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                type="submit"
                variant="contained"
                fullWidth
              >
                Login
              </Button>
            </Grid2>
            <Grid2 size={{ xs: 12, md: 6 }}>
              <Button
                disabled={isAuthenticating}
                variant="contained"
                fullWidth
                aria-label="google-btn" 👈👀
                startIcon={<Google />}
                onClick={handleGoogleSignIn}
              >
                Google
              </Button>
            </Grid2>
          </Grid2>
          <Grid2
            container
            // direction="row"
            justifyContent="end"
            sx={{ mt: 2 }}
          >
            <Link
              component={RouterLink}
              color="inherit"
              to="/auth/register"
            >
              Create an account.
            </Link>
          </Grid2>
        </Box>
      </form>
    </AuthLayout>
  );
};
```

`tests/auth/pages/LoginPage.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { Provider } from "react-redux";
import { configureStore } from "@reduxjs/toolkit";
import { MemoryRouter } from "react-router-dom";

import { LoginPage } from "../../../src/auth/pages/LoginPage";
import { authSlice } from "../../../src/store/auth/authSlice";
import { notAuthenticatedState } from "../../fixtures/authFixtures";

// It is important to put the word "mock" first.
const mockStartGoogleSignIn = jest.fn();

jest.mock("../../../src/store/auth/thunks", () => ({
  startGoogleSignIn: () => mockStartGoogleSignIn,
}));

const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
  },
  preloadedState: {
    auth: notAuthenticatedState,
  },
});

describe("Testing on LoginPage", () => {
  test("It should display the component correctly", () => {
    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );
    // screen.debug();
    expect(
      screen.getAllByText("Login").length
    ).toBeGreaterThanOrEqual(1);
  });

  test("The Google button should call startGoogleSignIn", () => {
    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );

    // screen.debug()
    // console.log(store.getState());

    const googleBtn = screen.getByLabelText("google-btn");
    fireEvent.click(googleBtn);

    // screen.debug();

    // console.log(store.getState());

    expect(mockStartGoogleSignIn).toHaveBeenCalled();
    // expect(mockStartGoogleSignIn).toHaveBeenCalledWith();
  });

  test("Submit must call startLoginWithEmailPassword.", () => {
    const email = "diego.more@gmail.com";
    const password = "123456";

    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );

    const emailField = screen.getByRole("textbox", {
      name: "Email",
    });

    // console.log(emailField);

    // screen.debug();

    fireEvent.change(emailField, {
      target: { name: "email", value: email },
    });

    /* It didn't work for me. 
    const passwordField = screen.getByTestId("password");
    fireEvent.change(passwordField, {
      target: { name: "password", value: password },
    });

    const loginForm = screen.getByLabelText("submit-form");
    fireEvent.submit(loginForm); */

    const passwordWrapper = screen.getByTestId("password");
    const passwordInput =
      passwordWrapper.querySelector("input");
    fireEvent.change(passwordInput, {
      target: { name: "password", value: password },
    });

    const passwordField = screen.getByLabelText("Password");
    fireEvent.change(passwordField, {
      target: { name: "password", value: password },
    });
  });
});
```

### 21.23 Dispatch con valores específicos

`tests/auth/pages/LoginPage.test.jsx`

```jsx
import {
  fireEvent,
  render,
  screen,
} from "@testing-library/react";
import { Provider, useDispatch } from "react-redux";
import { configureStore } from "@reduxjs/toolkit";
import { MemoryRouter } from "react-router-dom";

import { LoginPage } from "../../../src/auth/pages/LoginPage";
import { authSlice } from "../../../src/store/auth/authSlice";
import { notAuthenticatedState } from "../../fixtures/authFixtures";
import { startLoginWithEmailPassword } from "../../../src/store/auth/thunks";

// It is important to put the word "mock" first.
const mockStartGoogleSignIn = jest.fn();
const mockStartLoginWithEmailPassword = jest.fn();

jest.mock("../../../src/store/auth/thunks", () => ({
  startGoogleSignIn: () => mockStartGoogleSignIn,
  startLoginWithEmailPassword: ({ email, password }) => {
    return () =>
      mockStartLoginWithEmailPassword({ email, password });
  },
}));

jest.mock("react-redux", () => ({
  ...jest.requireActual("react-redux"),
  useDispatch: () => (fn) => fn(),
}));

const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
  },
  preloadedState: {
    auth: notAuthenticatedState,
  },
});

describe("Testing on LoginPage", () => {
  beforeEach(() => jest.clearAllMocks());

  test("It should display the component correctly", () => {
    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );
    // screen.debug();
    expect(
      screen.getAllByText("Login").length
    ).toBeGreaterThanOrEqual(1);
  });

  test("The Google button should call startGoogleSignIn", () => {
    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );

    // screen.debug()
    // console.log(store.getState());

    const googleBtn = screen.getByLabelText("google-btn");
    fireEvent.click(googleBtn);

    // screen.debug();

    // console.log(store.getState());

    expect(mockStartGoogleSignIn).toHaveBeenCalled();
    // expect(mockStartGoogleSignIn).toHaveBeenCalledWith();
  });

  test("Submit must call startLoginWithEmailPassword.", () => {
    const email = "diego.more@gmail.com";
    const password = "123456";

    render(
      <Provider store={store}>
        <MemoryRouter>
          <LoginPage />
        </MemoryRouter>
      </Provider>
    );

    const emailField = screen.getByRole("textbox", {
      name: "Email",
    });

    // console.log(emailField);

    // screen.debug();

    fireEvent.change(emailField, {
      target: { name: "email", value: email },
    });

    // It didn't work for me.
    const passwordField = screen.getByTestId("password");
    fireEvent.change(passwordField, {
      target: { name: "password", value: password },
    });

    const loginForm = screen.getByLabelText("submit-form");
    fireEvent.submit(loginForm);

    /* const passwordWrapper = screen.getByTestId("password");
    const passwordInput =
      passwordWrapper.querySelector("input");
    fireEvent.change(passwordInput, {
      target: { name: "password", value: password },
    });

    const passwordField = screen.getByLabelText("Password");
    fireEvent.change(passwordField, {
      target: { name: "password", value: password },
    }); */

    expect(
      mockStartLoginWithEmailPassword
    ).toHaveBeenCalledWith({
      email: email,
      password: password,
    });
  });
});
```

### 21.24 Código fuente de la sección

Aquí les dejo el código fuente de la sección por si lo llegan a necesitar:

[**GitHub - Fin sección 21**](https://github.com/Klerith/react-journal-material/tree/fin-seccion-21)

---

## 🟣 22. MERN Calendar - Estructura y Diseño

### 22.1 Introducción a la sección

### 22.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Estructura y diseño de nuestra aplicación de Calendario
- Uso de componentes de terceros
- Modals
- Configuración de Redux
- CRUD local
- Preparación de pantallas para futuras secciones
- Uso de MomentJS
- Manejo de fechas

Esta sección es el inicio de nuestro MERN, (Mongo Express React Node), luego crearemos nuestro backend y después regresaremos a esta app para conectarla y desplegarla en producción

### 22.3 Demostración del objetivo final de la sección

### 22.4 Inicio de proyecto - MERN-Calendar

```bash
npm create vite@latest
Ok to proceed? (y) y
Project name: 10-calendar
Select a framework: React
Select a variant: JavaScript
```

```bash
cd 10-calendar
npm i
npm run dev
```

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── CalendarApp.jsx
│   ├── main.jsx
│   └── styles.css
└── vite.config.js
```

```bash
# React Router
npm i react-router
```

`index.html`

```html
# https://getbootstrap.com/
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <!-- <link rel="icon" type="image/svg+xml" href="/vite.svg" /> -->
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />
    <title>CalendarApp</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { CalendarApp } from "./CalendarApp.jsx";

import "./styles.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <CalendarApp />
  </StrictMode>
);
```

`src/CalendarApp.jsx`

```jsx
export const CalendarApp = () => {
  return <div>CalendarApp</div>;
};
```

### 22.5 Rutas de la aplicación

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   └── styles.css
└── vite.config.js
```

`src/auth/pages/LoginPage.jsx`

```jsx
export const LoginPage = () => {
  return <div>LoginPage</div>;
};
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
export const CalendarPage = () => {
  return <div>CalendarPage</div>;
};
```

`src/router/AppRouter.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { LoginPage } from "../auth/pages/LoginPage";
import { CalendarPage } from "../calendar/pages/CalendarPage";

export const AppRouter = () => {
  const authStatus = "not-authenticated";

  return (
    <Routes>
      {authStatus === "not-authenticated" ? (
        <Route path="/auth/*" element={<LoginPage />} />
      ) : (
        <Route path="/*" element={<CalendarPage />} />
      )}

      <Route
        path="/*"
        element={<Navigate to="/auth/login" />}
      />
    </Routes>
  );
};
```

`src/CalendarApp.jsx`

```jsx
import { BrowserRouter } from "react-router";
import { AppRouter } from "./router/AppRouter";

export const CalendarApp = () => {
  return (
    <BrowserRouter>
      <AppRouter />
    </BrowserRouter>
  );
};
```

### 22.6 LoginScreen y Navbar

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components 👈👀
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   └── styles.css
└── vite.config.js
```

`index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <!-- <link rel="icon" type="image/svg+xml" href="/vite.svg" /> -->
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />
    <title>CalendarApp</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB"
      crossorigin="anonymous"
    />

    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/all.min.css"
      integrity="sha512-2SwdPD6INVrV/lHTZbO2nodKhrnDdJK9/kg2XD1r9uGqPo1cUbujc+IYdlYdEErWNu69gVcYgdxlmVmzTWnetw=="
      crossorigin="anonymous"
      referrerpolicy="no-referrer"
    />
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

`src/router/AppRouter.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { LoginPage } from "../auth/pages/LoginPage";
import { CalendarPage } from "../calendar/pages/CalendarPage";

export const AppRouter = () => {
  const authStatus = "authenticated"; 👈👀

  return (
    <Routes>
      {authStatus === "not-authenticated" ? (
        <Route path="/auth/*" element={<LoginPage />} />
      ) : (
        <Route path="/*" element={<CalendarPage />} />
      )}

      <Route
        path="/*"
        element={<Navigate to="/auth/login" />}
      />
    </Routes>
  );
};
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
import { Navbar } from "../components/Navbar";

export const CalendarPage = () => {
  return (
    <>
      <Navbar />
    </>
  );
};
```

`src/calendar/components/Navbar.jsx`

```jsx
export const Navbar = () => {
  return (
    <div className="navbar navbar-dark bg-dark mb-4 px-4">
      <span className="navbar-brand">
        <i className="fas fa-calendar-alt"></i> Ale Roses
      </span>
      <button className="btn btn-outline-danger">
        <i className="fas fa-sign-out-alt"></i>
        <span>Exit</span>
      </button>
    </div>
  );
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
import "./LoginPage.css";

export const LoginPage = () => {
  return (
    <div className="container login-container">
      <div className="row">
        <div className="col-md-6 login-form-1">
          <h3>Ingreso</h3>
          <form>
            <div className="form-group mb-2">
              <input
                type="text"
                className="form-control"
                placeholder="Correo"
              />
            </div>
            <div className="form-group mb-2">
              <input
                type="password"
                className="form-control"
                placeholder="Contraseña"
              />
            </div>
            <div className="form-group mb-2">
              <input
                type="submit"
                className="btnSubmit"
                value="Login"
              />
            </div>
          </form>
        </div>

        <div className="col-md-6 login-form-2">
          <h3>Registro</h3>
          <form>
            <div className="form-group mb-2">
              <input
                type="text"
                className="form-control"
                placeholder="Nombre"
              />
            </div>
            <div className="form-group mb-2">
              <input
                type="email"
                className="form-control"
                placeholder="Correo"
              />
            </div>
            <div className="form-group mb-2">
              <input
                type="password"
                className="form-control"
                placeholder="Contraseña"
              />
            </div>

            <div className="form-group mb-2">
              <input
                type="password"
                className="form-control"
                placeholder="Repita la contraseña"
              />
            </div>

            <div className="form-group mb-2">
              <input
                type="submit"
                className="btnSubmit"
                value="Crear cuenta"
              />
            </div>
          </form>
        </div>
      </div>
    </div>
  );
};
```

`src/auth/pages/LoginPage.css`

```css
.login-container {
  margin-top: 15%;
}
.login-form-1 {
  border-radius: 5px;
  box-shadow: 0 5px 8px 0 rgba(0, 0, 0, 0.2),
    0 9px 26px 0 rgba(0, 0, 0, 0.19);
  padding: 5%;
}
.login-form-1 h3 {
  text-align: center;
  color: #333;
}
.login-form-2 {
  border-radius: 5px;
  box-shadow: 0 5px 8px 0 rgba(0, 0, 0, 0.2),
    0 9px 26px 0 rgba(0, 0, 0, 0.19);
  padding: 5%;
  background: #0062cc;
}
.login-form-2 h3 {
  text-align: center;
  color: #fff;
}
.login-container form {
  padding: 10%;
}
.btnSubmit {
  width: 50%;
  border-radius: 1rem;
  padding: 1.5%;
  border: none;
  cursor: pointer;
}
.login-form-1 .btnSubmit {
  color: #fff;
  background-color: #0062cc;
}
.login-form-2 .btnSubmit {
  background-color: #fff;
  color: #0062cc;
}
.login-form-2 .ForgetPwd {
  color: #fff;
  font-weight: 600;
  text-decoration: none;
}
.login-form-1 .ForgetPwd {
  color: #0062cc;
  font-weight: 600;
  text-decoration: none;
}
```

- [CSS LoginScreen.js]
- [CDN font-awesome](https://cdnjs.com/libraries/font-awesome)

### 22.7 React Big Calendar

```bash
# Install
npm i react-big-calendar
npm i date-fns@2.29.0
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
import {
  Calendar,
  dateFnsLocalizer,
} from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import {
  addHours,
  format,
  parse,
  startOfWeek,
  getDay,
} from "date-fns";
import enUS from "date-fns/locale/en-US";
import { Navbar } from "../components/Navbar";

const locales = {
  "en-US": enUS,
};

const localizer = dateFnsLocalizer({
  format,
  parse,
  startOfWeek,
  getDay,
  locales,
});

const events = [
  {
    title: "The boss's birthday.",
    notes: "Buy cake",
    start: new Date(),
    end: addHours(new Date(), 2),
    bgColor: "#fafafa",
    user: {
      _id: "123",
      name: "Ale",
    },
  },
];

export const CalendarPage = () => {
  return (
    <>
      <Navbar />
      <Calendar
        localizer={localizer}
        events={events}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
      />
    </>
  );
};
```

- [React Big Calendar](https://www.npmjs.com/package/react-big-calendar)
- [date-fns](https://www.npmjs.com/package/date-fns/v/2.29.0)

### 22.8 Configuraciones adicionales al calendario

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers 👈👀👇
│   │   ├── calendarLocalizer.js
│   │   └── getMessages.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   └── styles.css
└── vite.config.js
```

Por algún motivo, los botones de `Month` `Week` `Day` y `Agenda` no funcionan con el `StrictMode` de React, así que por esta vez no deberías usarlos.

`src/main.jsx`

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { CalendarApp } from "./CalendarApp.jsx";

import "./styles.css";

createRoot(document.getElementById("root")).render(
  // <StrictMode>
  <CalendarApp />
  // </StrictMode>
);
```

`src/helpers/getMessages.js`

```js
export const getMessagesES = () => {
  return {
    allDay: "Todo el día",
    previous: "<",
    next: ">",
    today: "Hoy",
    month: "Mes",
    week: "Semana",
    day: "Día",
    agenda: "Agenda",
    date: "Fecha",
    time: "Hora",
    event: "Evento",
    noEventsInRange: "No hay eventos en este rango",
    showMore: (total) => `+ Ver más (${total})`,
  };
};
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
import { Calendar } from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import { addHours } from "date-fns";
import { Navbar } from "../components/Navbar";
import { localizer } from "../../helpers/calendarLocalizer";
import { getMessagesES } from "../../helpers/getMessages";

const events = [
  {
    title: "The boss's birthday.",
    notes: "Buy cake",
    start: new Date(),
    end: addHours(new Date(), 2),
    bgColor: "#fafafa",
    user: {
      _id: "123",
      name: "Ale",
    },
  },
];

export const CalendarPage = () => {
  const eventStyleGetter = (
    event,
    start,
    end,
    isSelected
  ) => {
    console.log({ event, start, end, isSelected });

    const style = {
      backgroundColor: "#347CF7",
      borderRadius: "0px",
      opacity: "white",
    };

    return {
      style,
    };
  };

  return (
    <>
      <Navbar />
      <Calendar
        culture="es"
        localizer={localizer}
        events={events}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
        messages={getMessagesES()}
        eventPropGetter={eventStyleGetter}
      />
    </>
  );
};
```

`src/helpers/calendarLocalizer.js`

```js
import { dateFnsLocalizer } from "react-big-calendar";
import { format, parse, startOfWeek, getDay } from "date-fns";
import esES from "date-fns/locale/es";

const locales = {
  es: esES,
};

export const localizer = dateFnsLocalizer({
  format,
  parse,
  startOfWeek,
  getDay,
  locales,
});
```

[Calendar-messages-es.js](https://gist.github.com/Klerith/1658fc368898dd673fc5a9a01ccb12ff)

### 22.9 Personalizar el cuadro de evento

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx 👈👀
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   └── getMessages.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   └── styles.css
└── vite.config.js
```

`src/calendar/components/CalendarEvent.jsx`

```jsx
export const CalendarEvent = ({ event }) => {
  const { title, user } = event;

  return (
    <>
      <strong>{title}</strong>
      <span> - {user.name}</span>
    </>
  );
};
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
import { Calendar } from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import { addHours } from "date-fns";
import { Navbar } from "../components/Navbar";
import { localizer } from "../../helpers/calendarLocalizer";
import { getMessagesES } from "../../helpers/getMessages";
import { CalendarEvent } from "../components/CalendarEvent";

const events = [
  {
    title: "The boss's birthday.",
    notes: "Buy cake",
    start: new Date(),
    end: addHours(new Date(), 2),
    bgColor: "#fafafa",
    user: {
      _id: "123",
      name: "Ale",
    },
  },
];

export const CalendarPage = () => {
  const eventStyleGetter = (
    event,
    start,
    end,
    isSelected
  ) => {
    // console.log({ event, start, end, isSelected });

    const style = {
      backgroundColor: "#347CF7",
      borderRadius: "0px",
      opacity: "white",
    };

    return {
      style,
    };
  };

  return (
    <>
      <Navbar />
      <Calendar
        culture="es"
        localizer={localizer}
        events={events}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
        messages={getMessagesES()}
        eventPropGetter={eventStyleGetter}
        components={{
          event: CalendarEvent,
        }}
      />
    </>
  );
};
```

### 22.10 Escuchar eventos del calendario

`src/calendar/pages/CalendarPage.jsx`

```jsx
import { useState } from "react";
import { Calendar } from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import { addHours } from "date-fns";
import { Navbar } from "../components/Navbar";
import { localizer } from "../../helpers/calendarLocalizer";
import { getMessagesES } from "../../helpers/getMessages";
import { CalendarEvent } from "../components/CalendarEvent";

const events = [
  {
    title: "The boss's birthday.",
    notes: "Buy cake",
    start: new Date(),
    end: addHours(new Date(), 2),
    bgColor: "#fafafa",
    user: {
      _id: "123",
      name: "Ale",
    },
  },
];

export const CalendarPage = () => {
  const [lastView, setLastView] = useState(
    localStorage.getItem("lastView") || "week"
  );

  const eventStyleGetter = (
    event,
    start,
    end,
    isSelected
  ) => {
    // console.log({ event, start, end, isSelected });

    const style = {
      backgroundColor: "#347CF7",
      borderRadius: "0px",
      opacity: "white",
    };

    return {
      style,
    };
  };

  const onDoubleClick = (event) => {
    console.log({ doubleClick: event });
  };

  const onSelect = (event) => {
    console.log({ click: event });
  };

  const onViewChanged = (event) => {
    // console.log({ viewChanged: event });
    localStorage.setItem("lastView", event);

    setLastView(event);
  };

  return (
    <>
      <Navbar />
      <Calendar
        culture="es"
        localizer={localizer}
        events={events}
        defaultView={lastView}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
        messages={getMessagesES()}
        eventPropGetter={eventStyleGetter}
        components={{
          event: CalendarEvent,
        }}
        onDoubleClickEvent={onDoubleClick}
        onSelectEvent={onSelect}
        onView={onViewChanged}
      />
    </>
  );
};
```

📌 Si no te aparece el `console.log` al dar doble clic solo cierra el inspector de elementos y da doble clic. Ahora al abrir el inspector podrás ver los mensajes en consola.

Ver `Application/Local storage/http://localhost...`

### 22.11 Creando un modal sobre el calendario

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx
│   │   │   ├── CalendarModal.jsx 👈👀
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   └── getMessages.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   └── styles.css
└── vite.config.js
```

```bash
# Install
npm i react-modal
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
import { useState } from "react";
import { Calendar } from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import { addHours } from "date-fns";
import { Navbar } from "../components/Navbar";
import { localizer } from "../../helpers/calendarLocalizer";
import { getMessagesES } from "../../helpers/getMessages";
import { CalendarEvent } from "../components/CalendarEvent";
import { CalendarModal } from "../components/CalendarModal";

const events = [
  {
    title: "The boss's birthday.",
    notes: "Buy cake",
    start: new Date(),
    end: addHours(new Date(), 2),
    bgColor: "#fafafa",
    user: {
      _id: "123",
      name: "Ale",
    },
  },
];

export const CalendarPage = () => {
  const [lastView, setLastView] = useState(
    localStorage.getItem("lastView") || "week"
  );

  const eventStyleGetter = (
    event,
    start,
    end,
    isSelected
  ) => {
    // console.log({ event, start, end, isSelected });

    const style = {
      backgroundColor: "#347CF7",
      borderRadius: "0px",
      opacity: "white",
    };

    return {
      style,
    };
  };

  const onDoubleClick = (event) => {
    console.log({ doubleClick: event });
  };

  const onSelect = (event) => {
    console.log({ click: event });
  };

  const onViewChanged = (event) => {
    // console.log({ viewChanged: event });
    localStorage.setItem("lastView", event);

    setLastView(event);
  };

  return (
    <>
      <Navbar />
      <Calendar
        culture="es"
        localizer={localizer}
        events={events}
        defaultView={lastView}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
        messages={getMessagesES()}
        eventPropGetter={eventStyleGetter}
        components={{
          event: CalendarEvent,
        }}
        onDoubleClickEvent={onDoubleClick}
        onSelectEvent={onSelect}
        onView={onViewChanged}
      />
      <CalendarModal />
    </>
  );
};
```

`src/calendar/components/CalendarModal.jsx`

```jsx
import { useState } from "react";
import Modal from "react-modal";

const customStyles = {
  content: {
    top: "50%",
    left: "50%",
    right: "auto",
    bottom: "auto",
    marginRight: "-50%",
    transform: "translate(-50%, -50%)",
  },
};

Modal.setAppElement("#root");

export const CalendarModal = () => {
  const [isOpen, setIsOpen] = useState(true);

  const onCloseModal = () => {
    console.log("Closing modal");
    setIsOpen(false);
  };

  return (
    <Modal
      isOpen={isOpen}
      onRequestClose={onCloseModal}
      style={customStyles}
      contentLabel="Example Modal"
      className="modal"
      overlayClassName="modal-fondo"
      closeTimeoutMS={200}
    >
      <h1>Hi world</h1>
      <hr />
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing
        elit. Possimus, nulla accusantium voluptatem commodi
        quaerat amet est magni alias illo natus! Dolore dolor
        nobis iste! At quidem repudiandae sint eum sunt?
      </p>
    </Modal>
  );
};
```

`src/styles.css`

```css
/* Modal */
.ReactModalPortal > div {
  opacity: 0;
}

.ReactModalPortal .ReactModal__Overlay {
  align-items: center;
  display: flex;
  justify-content: center;
  transition: opacity 0.2s ease-in-out;
  z-index: 999;
}

.modal-fondo {
  background-color: rgba(0, 0, 0, 0.3);
  bottom: 0;
  left: 0;
  right: 0;
  top: 0;
  position: fixed;
}

.ReactModalPortal .ReactModal__Overlay--after-open {
  opacity: 1;
}

.ReactModalPortal .ReactModal__Overlay--before-close {
  opacity: 0;
}

.modal {
  background: white;
  border-radius: 5px;
  color: rgb(51, 51, 51);
  display: inline;
  max-height: 620px;
  max-width: 500px;
  outline: none;
  padding: 10px;
}
```

- [Modal Styles](https://gist.github.com/Klerith/5f490092ce9bd5775cb1d91162be0cea)
- [react-modal](https://www.npmjs.com/package/react-modal)

### 22.12 Contenido del Modal

```bash
# Install
npm i react-datepicker
```

`src/calendar/components/CalendarModal.jsx`

```jsx
import { useState } from "react";
import { addHours } from "date-fns";

import Modal from "react-modal";
import DatePicker from "react-datepicker";
import "react-datepicker/dist/react-datepicker.css";

const customStyles = {
  content: {
    top: "50%",
    left: "50%",
    right: "auto",
    bottom: "auto",
    marginRight: "-50%",
    transform: "translate(-50%, -50%)",
  },
};

Modal.setAppElement("#root");

export const CalendarModal = () => {
  const [isOpen, setIsOpen] = useState(true);

  const [formValues, setFormValues] = useState({
    title: "Ale",
    notes: "Ghost",
    start: new Date(),
    end: addHours(new Date(), 2),
  });

  const onInputChanged = ({ target }) => {
    setFormValues({
      ...formValues,
      [target.name]: target.value,
    });
  };

  const onDateChanged = (event, changing = "") => {
    setFormValues({
      ...formValues,
      [changing]: event,
    });
  };

  const onCloseModal = () => {
    console.log("Closing modal");
    setIsOpen(false);
  };

  return (
    <Modal
      isOpen={isOpen}
      onRequestClose={onCloseModal}
      style={customStyles}
      contentLabel="Example Modal"
      className="modal"
      overlayClassName="modal-fondo"
      closeTimeoutMS={200}
    >
      <h1> Nuevo evento </h1>
      <hr />
      <form className="container">
        <div className="form-group mb-2">
          <label>Fecha y hora inicio</label>
          <DatePicker
            selected={formValues.start}
            onChange={(event) =>
              onDateChanged(event, "start")
            }
            className="form-control"
            dateFormat="Pp"
          />
        </div>

        <div className="form-group mb-2">
          <label>Fecha y hora fin</label>
          <DatePicker
            minDate={formValues.start}
            selected={formValues.end}
            onChange={(event) => onDateChanged(event, "end")}
            className="form-control"
            dateFormat="Pp"
          />
        </div>

        <hr />
        <div className="form-group mb-2">
          <label>Titulo y notas</label>
          <input
            type="text"
            className="form-control"
            placeholder="Título del evento"
            name="title"
            autoComplete="off"
            value={formValues.title}
            onChange={onInputChanged}
          />
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Una descripción corta
          </small>
        </div>

        <div className="form-group mb-2">
          <textarea
            type="text"
            className="form-control"
            placeholder="Notas"
            rows="5"
            name="notes"
            value={formValues.notes}
            onChange={onInputChanged}
          ></textarea>
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Información adicional
          </small>
        </div>

        <button
          type="submit"
          className="btn btn-outline-primary btn-block"
        >
          <i className="far fa-save"></i>
          <span> Guardar</span>
        </button>
      </form>
    </Modal>
  );
};
```

- [react-datepicker](https://www.npmjs.com/package/react-datepicker)
- [EventModal.js](https://gist.github.com/Klerith/8c9b2178830045b3f5126422bd0223e1)

### 22.13 Datepicker en español

`src/calendar/components/CalendarModal.jsx`

```jsx
import { useState } from "react";
import { addHours } from "date-fns";

import Modal from "react-modal";
import DatePicker, { registerLocale } from "react-datepicker";
import "react-datepicker/dist/react-datepicker.css";
import es from "date-fns/locale/es";

registerLocale("es", es);

const customStyles = {
  content: {
    top: "50%",
    left: "50%",
    right: "auto",
    bottom: "auto",
    marginRight: "-50%",
    transform: "translate(-50%, -50%)",
  },
};

Modal.setAppElement("#root");

export const CalendarModal = () => {
  const [isOpen, setIsOpen] = useState(true);

  const [formValues, setFormValues] = useState({
    title: "Ale",
    notes: "Ghost",
    start: new Date(),
    end: addHours(new Date(), 2),
  });

  const onInputChanged = ({ target }) => {
    setFormValues({
      ...formValues,
      [target.name]: target.value,
    });
  };

  const onDateChanged = (event, changing = "") => {
    setFormValues({
      ...formValues,
      [changing]: event,
    });
  };

  const onCloseModal = () => {
    console.log("Closing modal");
    setIsOpen(false);
  };

  return (
    <Modal
      isOpen={isOpen}
      onRequestClose={onCloseModal}
      style={customStyles}
      contentLabel="Example Modal"
      className="modal"
      overlayClassName="modal-fondo"
      closeTimeoutMS={200}
    >
      <h1> Nuevo evento </h1>
      <hr />
      <form className="container">
        <div className="form-group mb-2">
          <label>Fecha y hora inicio</label>
          <DatePicker
            selected={formValues.start}
            onChange={(event) =>
              onDateChanged(event, "start")
            }
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <div className="form-group mb-2">
          <label>Fecha y hora fin</label>
          <DatePicker
            minDate={formValues.start}
            selected={formValues.end}
            onChange={(event) => onDateChanged(event, "end")}
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <hr />
        <div className="form-group mb-2">
          <label>Titulo y notas</label>
          <input
            type="text"
            className="form-control"
            placeholder="Título del evento"
            name="title"
            autoComplete="off"
            value={formValues.title}
            onChange={onInputChanged}
          />
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Una descripción corta
          </small>
        </div>

        <div className="form-group mb-2">
          <textarea
            type="text"
            className="form-control"
            placeholder="Notas"
            rows="5"
            name="notes"
            value={formValues.notes}
            onChange={onInputChanged}
          ></textarea>
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Información adicional
          </small>
        </div>

        <button
          type="submit"
          className="btn btn-outline-primary btn-block"
        >
          <i className="far fa-save"></i>
          <span> Guardar</span>
        </button>
      </form>
    </Modal>
  );
};
```

### 22.14 Obtener la información del formulario del evento

`src/calendar/components/CalendarModal.jsx`

```jsx
import { useState } from "react";
import { addHours, differenceInSeconds } from "date-fns";

import Modal from "react-modal";
import DatePicker, { registerLocale } from "react-datepicker";
import "react-datepicker/dist/react-datepicker.css";
import es from "date-fns/locale/es";

registerLocale("es", es);

const customStyles = {
  content: {
    top: "50%",
    left: "50%",
    right: "auto",
    bottom: "auto",
    marginRight: "-50%",
    transform: "translate(-50%, -50%)",
  },
};

Modal.setAppElement("#root");

export const CalendarModal = () => {
  const [isOpen, setIsOpen] = useState(true);

  const [formValues, setFormValues] = useState({
    title: "Ale",
    notes: "Ghost",
    start: new Date(),
    end: addHours(new Date(), 2),
  });

  const onInputChanged = ({ target }) => {
    setFormValues({
      ...formValues,
      [target.name]: target.value,
    });
  };

  const onDateChanged = (event, changing = "") => {
    setFormValues({
      ...formValues,
      [changing]: event,
    });
  };

  const onCloseModal = () => {
    console.log("Closing modal");
    setIsOpen(false);
  };

  const onSubmit = (event) => {
    event.preventDefault();

    const difference = differenceInSeconds(
      formValues.end,
      formValues.start
    );

    if (isNaN(difference) || difference <= 0) {
      console.log("Error in dates");
      return;
    }

    if (formValues.title.length <= 0) return;

    console.log(formValues);

    // TODO:
    // Close modal
    // Remove errors on screen
  };

  return (
    <Modal
      isOpen={isOpen}
      onRequestClose={onCloseModal}
      style={customStyles}
      contentLabel="Example Modal"
      className="modal"
      overlayClassName="modal-fondo"
      closeTimeoutMS={200}
    >
      <h1> Nuevo evento </h1>
      <hr />
      <form className="container" onSubmit={onSubmit}>
        <div className="form-group mb-2">
          <label>Fecha y hora inicio</label>
          <DatePicker
            selected={formValues.start}
            onChange={(event) =>
              onDateChanged(event, "start")
            }
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <div className="form-group mb-2">
          <label>Fecha y hora fin</label>
          <DatePicker
            minDate={formValues.start}
            selected={formValues.end}
            onChange={(event) => onDateChanged(event, "end")}
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <hr />
        <div className="form-group mb-2">
          <label>Titulo y notas</label>
          <input
            type="text"
            className="form-control"
            placeholder="Título del evento"
            name="title"
            autoComplete="off"
            value={formValues.title}
            onChange={onInputChanged}
          />
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Una descripción corta
          </small>
        </div>

        <div className="form-group mb-2">
          <textarea
            type="text"
            className="form-control"
            placeholder="Notas"
            rows="5"
            name="notes"
            value={formValues.notes}
            onChange={onInputChanged}
          ></textarea>
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Información adicional
          </small>
        </div>

        <button
          type="submit"
          className="btn btn-outline-primary btn-block"
        >
          <i className="far fa-save"></i>
          <span> Guardar</span>
        </button>
      </form>
    </Modal>
  );
};
```

### 22.15 Validaciones del formulario

```bash
npm install sweetalert2
```

`src/calendar/components/CalendarModal.jsx`

```jsx
import { useMemo, useState } from "react";
import { addHours, differenceInSeconds } from "date-fns";

import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.min.css";

import Modal from "react-modal";
import DatePicker, { registerLocale } from "react-datepicker";
import "react-datepicker/dist/react-datepicker.css";
import es from "date-fns/locale/es";

registerLocale("es", es);

const customStyles = {
  content: {
    top: "50%",
    left: "50%",
    right: "auto",
    bottom: "auto",
    marginRight: "-50%",
    transform: "translate(-50%, -50%)",
  },
};

Modal.setAppElement("#root");

export const CalendarModal = () => {
  const [isOpen, setIsOpen] = useState(true);
  const [formSubmitted, setFormSubmitted] = useState(false);

  const [formValues, setFormValues] = useState({
    title: "Ale",
    notes: "Ghost",
    start: new Date(),
    end: addHours(new Date(), 2),
  });

  const titleClass = useMemo(() => {
    if (!formSubmitted) return "";

    return formValues.title.length > 0 ? "" : "is-invalid";
  }, [formValues.title, formSubmitted]);

  const onInputChanged = ({ target }) => {
    setFormValues({
      ...formValues,
      [target.name]: target.value,
    });
  };

  const onDateChanged = (event, changing = "") => {
    setFormValues({
      ...formValues,
      [changing]: event,
    });
  };

  const onCloseModal = () => {
    console.log("Closing modal");
    setIsOpen(false);
  };

  const onSubmit = (event) => {
    event.preventDefault();
    setFormSubmitted(true);

    const difference = differenceInSeconds(
      formValues.end,
      formValues.start
    );

    if (isNaN(difference) || difference <= 0) {
      Swal.fire(
        "Incorrect dates",
        "Review the dates entered",
        "error"
      );
      return;
    }

    if (formValues.title.length <= 0) return;

    console.log(formValues);

    // TODO:
    // Close modal
    // Remove errors on screen
  };

  return (
    <Modal
      isOpen={isOpen}
      onRequestClose={onCloseModal}
      style={customStyles}
      contentLabel="Example Modal"
      className="modal"
      overlayClassName="modal-fondo"
      closeTimeoutMS={200}
    >
      <h1> Nuevo evento </h1>
      <hr />
      <form className="container" onSubmit={onSubmit}>
        <div className="form-group mb-2">
          <label>Fecha y hora inicio</label>
          <DatePicker
            selected={formValues.start}
            onChange={(event) =>
              onDateChanged(event, "start")
            }
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <div className="form-group mb-2">
          <label>Fecha y hora fin</label>
          <DatePicker
            minDate={formValues.start}
            selected={formValues.end}
            onChange={(event) => onDateChanged(event, "end")}
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <hr />
        <div className="form-group mb-2">
          <label>Titulo y notas</label>
          <input
            type="text"
            className={`form-control ${titleClass}`}
            placeholder="Título del evento"
            name="title"
            autoComplete="off"
            value={formValues.title}
            onChange={onInputChanged}
          />
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Una descripción corta
          </small>
        </div>

        <div className="form-group mb-2">
          <textarea
            type="text"
            className="form-control"
            placeholder="Notas"
            rows="5"
            name="notes"
            value={formValues.notes}
            onChange={onInputChanged}
          ></textarea>
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Información adicional
          </small>
        </div>

        <button
          type="submit"
          className="btn btn-outline-primary btn-block"
        >
          <i className="far fa-save"></i>
          <span> Guardar</span>
        </button>
      </form>
    </Modal>
  );
};
```

[Sweetalert2](https://sweetalert2.github.io/)

### 22.16 Instalación y configuración de Redux

```bash
# Install
npm install @reduxjs/toolkit
npm install react-redux
```

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx
│   │   │   ├── CalendarModal.jsx
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   └── getMessages.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store 👈👀👇
│   │   ├── calendar
│   │   ├── store.js
│   │   └── ui
│   │       └── uiSlice.js
│   └── styles.css
└── vite.config.js
```

`src/store/ui/uiSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const uiSlice = createSlice({
  name: "ui",
  initialState: {
    isDateModalOpen: false,
  },
  reducers: {
    onOpenDateModal: (state) => {
      state.isDateModalOpen = true;
    },
    onCloseDateModal: (state) => {
      state.isDateModalOpen = false;
    },
  },
});

export const { onOpenDateModal, onCloseDateModal } =
  uiSlice.actions;
```

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { uiSlice } from "./ui/uiSlice";

export const store = configureStore({
  reducer: {
    ui: uiSlice.reducer,
  },
});
```

`src/CalendarApp.jsx`

```jsx
import { BrowserRouter } from "react-router";
import { AppRouter } from "./router/AppRouter";
import { Provider } from "react-redux";
import { store } from "./store/store";

export const CalendarApp = () => {
  return (
    <Provider store={store}>
      <BrowserRouter>
        <AppRouter />
      </BrowserRouter>
    </Provider>
  );
};
```

Revisa en consola: `Redux/State/Tree` ui `isDateModalOpen: false`

- [Redux Toolkit](https://redux-toolkit.js.org/)
- [React Redux](https://react-redux.js.org/)
- [Redux-thunk](https://www.npmjs.com/package/redux-thunk)
- [Redux](https://es.redux.js.org/)

### 22.17 Mostrar y ocultar modal en base al Store

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx
│   │   │   ├── CalendarModal.jsx
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   └── getMessages.js
│   ├── hooks 👈👀👇
│   │   └── useUiStore.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── calendar
│   │   ├── store.js
│   │   └── ui
│   │       └── uiSlice.js
│   └── styles.css
└── vite.config.js
```

`src/hooks/useUiStore.js`

```js
import { useDispatch, useSelector } from "react-redux";
import {
  onCloseDateModal,
  onOpenDateModal,
} from "../store/ui/uiSlice";

export const useUiStore = () => {
  const dispatch = useDispatch();

  const { isDateModalOpen } = useSelector(
    (state) => state.ui
  );

  const openDateModal = () => {
    dispatch(onOpenDateModal());
  };

  const closeDateModal = () => {
    dispatch(onCloseDateModal());
  };

  // const toggleDateModal = () => {
  //   isDateModalOpen ? openDateModal() : closeDateModal();
  // };

  return {
    // Properties
    isDateModalOpen,

    // Methods
    closeDateModal,
    openDateModal,
    // toggleDateModal,
  };
};
```

`src/calendar/components/CalendarModal.jsx`

```jsx
import { useMemo, useState } from "react";
import { addHours, differenceInSeconds } from "date-fns";

import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.min.css";

import Modal from "react-modal";
import DatePicker, { registerLocale } from "react-datepicker";
import "react-datepicker/dist/react-datepicker.css";
import es from "date-fns/locale/es";
import { useUiStore } from "../../hooks/useUiStore";

registerLocale("es", es);

const customStyles = {
  content: {
    top: "50%",
    left: "50%",
    right: "auto",
    bottom: "auto",
    marginRight: "-50%",
    transform: "translate(-50%, -50%)",
  },
};

Modal.setAppElement("#root");

export const CalendarModal = () => {
  const { isDateModalOpen, closeDateModal } = useUiStore();

  const [isOpen, setIsOpen] = useState(true);
  const [formSubmitted, setFormSubmitted] = useState(false);

  const [formValues, setFormValues] = useState({
    title: "Ale",
    notes: "Ghost",
    start: new Date(),
    end: addHours(new Date(), 2),
  });

  const titleClass = useMemo(() => {
    if (!formSubmitted) return "";

    return formValues.title.length > 0 ? "" : "is-invalid";
  }, [formValues.title, formSubmitted]);

  const onInputChanged = ({ target }) => {
    setFormValues({
      ...formValues,
      [target.name]: target.value,
    });
  };

  const onDateChanged = (event, changing = "") => {
    setFormValues({
      ...formValues,
      [changing]: event,
    });
  };

  const onCloseModal = () => {
    closeDateModal();
  };

  const onSubmit = (event) => {
    event.preventDefault();
    setFormSubmitted(true);

    const difference = differenceInSeconds(
      formValues.end,
      formValues.start
    );

    if (isNaN(difference) || difference <= 0) {
      Swal.fire(
        "Incorrect dates",
        "Review the dates entered",
        "error"
      );
      return;
    }

    if (formValues.title.length <= 0) return;

    console.log(formValues);

    // TODO:
    // Close modal
    // Remove errors on screen
  };

  return (
    <Modal
      isOpen={isDateModalOpen}
      onRequestClose={onCloseModal}
      style={customStyles}
      contentLabel="Example Modal"
      className="modal"
      overlayClassName="modal-fondo"
      closeTimeoutMS={200}
    >
      <h1> Nuevo evento </h1>
      <hr />
      <form className="container" onSubmit={onSubmit}>
        <div className="form-group mb-2">
          <label>Fecha y hora inicio</label>
          <DatePicker
            selected={formValues.start}
            onChange={(event) =>
              onDateChanged(event, "start")
            }
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <div className="form-group mb-2">
          <label>Fecha y hora fin</label>
          <DatePicker
            minDate={formValues.start}
            selected={formValues.end}
            onChange={(event) => onDateChanged(event, "end")}
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <hr />
        <div className="form-group mb-2">
          <label>Titulo y notas</label>
          <input
            type="text"
            className={`form-control ${titleClass}`}
            placeholder="Título del evento"
            name="title"
            autoComplete="off"
            value={formValues.title}
            onChange={onInputChanged}
          />
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Una descripción corta
          </small>
        </div>

        <div className="form-group mb-2">
          <textarea
            type="text"
            className="form-control"
            placeholder="Notas"
            rows="5"
            name="notes"
            value={formValues.notes}
            onChange={onInputChanged}
          ></textarea>
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Información adicional
          </small>
        </div>

        <button
          type="submit"
          className="btn btn-outline-primary btn-block"
        >
          <i className="far fa-save"></i>
          <span> Guardar</span>
        </button>
      </form>
    </Modal>
  );
};
```

`src/store/ui/uiSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const uiSlice = createSlice({
  name: "ui",
  initialState: {
    isDateModalOpen: false,
  },
  reducers: {
    onOpenDateModal: (state) => {
      state.isDateModalOpen = true;
    },
    onCloseDateModal: (state) => {
      state.isDateModalOpen = false;
    },
  },
});

export const { onOpenDateModal, onCloseDateModal } =
  uiSlice.actions;
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
import { useState } from "react";
import { Calendar } from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import { addHours } from "date-fns";
import { Navbar } from "../components/Navbar";
import { localizer } from "../../helpers/calendarLocalizer";
import { getMessagesES } from "../../helpers/getMessages";
import { CalendarEvent } from "../components/CalendarEvent";
import { CalendarModal } from "../components/CalendarModal";
import { useUiStore } from "../../hooks/useUiStore";

const events = [
  {
    title: "The boss's birthday.",
    notes: "Buy cake",
    start: new Date(),
    end: addHours(new Date(), 2),
    bgColor: "#fafafa",
    user: {
      _id: "123",
      name: "Ale",
    },
  },
];

export const CalendarPage = () => {
  const { openDateModal } = useUiStore();

  const [lastView, setLastView] = useState(
    localStorage.getItem("lastView") || "week"
  );

  const eventStyleGetter = (
    event,
    start,
    end,
    isSelected
  ) => {
    // console.log({ event, start, end, isSelected });

    const style = {
      backgroundColor: "#347CF7",
      borderRadius: "0px",
      opacity: "white",
    };

    return {
      style,
    };
  };

  const onDoubleClick = (event) => {
    console.log({ doubleClick: event });

    openDateModal();
  };

  const onSelect = (event) => {
    console.log({ click: event });
  };

  const onViewChanged = (event) => {
    // console.log({ viewChanged: event });
    localStorage.setItem("lastView", event);

    setLastView(event);
  };

  return (
    <>
      <Navbar />
      <Calendar
        culture="es"
        localizer={localizer}
        events={events}
        defaultView={lastView}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
        messages={getMessagesES()}
        eventPropGetter={eventStyleGetter}
        components={{
          event: CalendarEvent,
        }}
        onDoubleClickEvent={onDoubleClick}
        onSelectEvent={onSelect}
        onView={onViewChanged}
      />
      <CalendarModal />
    </>
  );
};
```

### 22.18 CalendarSlice

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx
│   │   │   ├── CalendarModal.jsx
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   └── getMessages.js
│   ├── hooks 👈👀👇
│   │   ├── useCalendarStore.js
│   │   └── useUiStore.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── calendar 👈👀👇
│   │   │   └── calendarSlice.js
│   │   ├── store.js
│   │   └── ui
│   │       └── uiSlice.js
│   └── styles.css
└── vite.config.js
```

`src/store/calendar/calendarSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";
import { addHours } from "date-fns";

const tempEvent = {
  title: "The boss's birthday.",
  notes: "Buy cake",
  start: new Date(),
  end: addHours(new Date(), 2),
  bgColor: "#fafafa",
  user: {
    _id: "123",
    name: "Ale",
  },
};

export const calendarSlice = createSlice({
  name: "calendar",
  initialState: {
    events: [tempEvent],
    activeEvent: null,
  },
  reducers: {
    increment: (state /* action */) => {
      state.counter += 1;
    },
  },
});

export const { increment } = calendarSlice.actions;
```

`src/hooks/useCalendarStore.js`

```js
import { useSelector } from "react-redux";

export const useCalendarStore = () => {
  const { events, activeEvent } = useSelector(
    (state) => state.calendar
  );
  return {
    // Properties
    events,
    activeEvent,

    // Methods
  };
};
```

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { uiSlice } from "./ui/uiSlice";
import { calendarSlice } from "./calendar/calendarSlice";

export const store = configureStore({
  reducer: {
    calendar: calendarSlice.reducer,
    ui: uiSlice.reducer,
  },
});
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
import { useState } from "react";
import { Calendar } from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import { addHours } from "date-fns";
import { Navbar } from "../components/Navbar";
import { localizer } from "../../helpers/calendarLocalizer";
import { getMessagesES } from "../../helpers/getMessages";
import { CalendarEvent } from "../components/CalendarEvent";
import { CalendarModal } from "../components/CalendarModal";
import { useUiStore } from "../../hooks/useUiStore";
import { useCalendarStore } from "../../hooks/useCalendarStore";

/* const events = [
  {
    title: "The boss's birthday.",
    notes: "Buy cake",
    start: new Date(),
    end: addHours(new Date(), 2),
    bgColor: "#fafafa",
    user: {
      _id: "123",
      name: "Ale",
    },
  },
]; */

export const CalendarPage = () => {
  const { openDateModal } = useUiStore();
  const { events } = useCalendarStore();

  const [lastView, setLastView] = useState(
    localStorage.getItem("lastView") || "week"
  );

  const eventStyleGetter = (
    event,
    start,
    end,
    isSelected
  ) => {
    // console.log({ event, start, end, isSelected });

    const style = {
      backgroundColor: "#347CF7",
      borderRadius: "0px",
      opacity: "white",
    };

    return {
      style,
    };
  };

  const onDoubleClick = (event) => {
    console.log({ doubleClick: event });

    openDateModal();
  };

  const onSelect = (event) => {
    console.log({ click: event });
  };

  const onViewChanged = (event) => {
    // console.log({ viewChanged: event });
    localStorage.setItem("lastView", event);

    setLastView(event);
  };

  return (
    <>
      <Navbar />
      <Calendar
        culture="es"
        localizer={localizer}
        events={events}
        defaultView={lastView}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
        messages={getMessagesES()}
        eventPropGetter={eventStyleGetter}
        components={{
          event: CalendarEvent,
        }}
        onDoubleClickEvent={onDoubleClick}
        onSelectEvent={onSelect}
        onView={onViewChanged}
      />
      <CalendarModal />
    </>
  );
};
```

`redux-slice`

#### Valor no serializable en Redux Toolkit

En esta clase aparece este error, pero la aplicación funciona bien. En la siguiente clase se habla más al respecto.

```bash
installHook.js:1 A non-serializable value was detected in the state, in the path: `calendar.events.0.start`. Value: Fri Sep 26 2025 14:37:20 GMT-0500 (Ecuador Time) 
Take a look at the reducer(s) handling this action type: ui/onOpenDateModal.
(See https://redux.js.org/faq/organizing-state#can-i-put-functions-promises-or-other-non-serializable-items-in-my-store-state)
```

- Redux recomienda que **todo el estado sea serializable** (números, strings, booleanos, arrays u objetos planos).
    
- Los objetos `Date` no son serializables de forma segura (al convertirlos en JSON se pierden métodos como `.getFullYear()`).
    
- Por eso aparece el warning cuando intentas guardar `event.start` o `event.end` como `Date`.

Ver Redux - serializableCheck](https://cursos.devtalles.com/courses/take/react-cero-experto/lessons/36252620-redux-serializablecheck)

### 22.19 Cargar un evento en el modal

`src/store/calendar/calendarSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";
import { addHours } from "date-fns";

const tempEvent = {
  _id: new Date().getTime(),
  title: "The boss's birthday.",
  notes: "Buy cake",
  start: new Date(),
  end: addHours(new Date(), 2),
  bgColor: "#fafafa",
  user: {
    _id: "123",
    name: "Ale",
  },
};

export const calendarSlice = createSlice({
  name: "calendar",
  initialState: {
    events: [tempEvent],
    activeEvent: null,
  },
  reducers: {
    onSetActiveEvent: (state, { payload }) => {
      state.activeEvent = payload;
    },
  },
});

export const { onSetActiveEvent } = calendarSlice.actions;
```

`src/hooks/useCalendarStore.js`

```js
import { useDispatch, useSelector } from "react-redux";
import { onSetActiveEvent } from "../store/calendar/calendarSlice";

export const useCalendarStore = () => {
  const dispatch = useDispatch();

  const { events, activeEvent } = useSelector(
    (state) => state.calendar
  );

  const setActiveEvent = (calendarEvent) => {
    dispatch(onSetActiveEvent(calendarEvent));
  };

  return {
    // Properties
    events,
    activeEvent,

    // Methods
    setActiveEvent,
  };
};
```

`src/calendar/pages/Calendarpage.jsx`

```jsx
import { useState } from "react";
import { Calendar } from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import { Navbar } from "../components/Navbar";
import { localizer } from "../../helpers/calendarLocalizer";
import { getMessagesES } from "../../helpers/getMessages";
import { CalendarEvent } from "../components/CalendarEvent";
import { CalendarModal } from "../components/CalendarModal";
import { useUiStore } from "../../hooks/useUiStore";
import { useCalendarStore } from "../../hooks/useCalendarStore";

export const CalendarPage = () => {
  const { openDateModal } = useUiStore();
  const { events, setActiveEvent } = useCalendarStore();

  const [lastView, setLastView] = useState(
    localStorage.getItem("lastView") || "week"
  );

  const eventStyleGetter = (
    event,
    start,
    end,
    isSelected
  ) => {
    const style = {
      backgroundColor: "#347CF7",
      borderRadius: "0px",
      opacity: "white",
    };

    return {
      style,
    };
  };

  const onDoubleClick = (event) => {
    console.log({ doubleClick: event });

    openDateModal();
  };

  const onSelect = (event) => {
    setActiveEvent(event);
  };

  const onViewChanged = (event) => {
    // console.log({ viewChanged: event });
    localStorage.setItem("lastView", event);

    setLastView(event);
  };

  return (
    <>
      <Navbar />
      <Calendar
        culture="es"
        localizer={localizer}
        events={events}
        defaultView={lastView}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
        messages={getMessagesES()}
        eventPropGetter={eventStyleGetter}
        components={{
          event: CalendarEvent,
        }}
        onDoubleClickEvent={onDoubleClick}
        onSelectEvent={onSelect}
        onView={onViewChanged}
      />
      <CalendarModal />
    </>
  );
};
```

`src/calendar/components/CalendarModal.jsx`

```jsx
import { useEffect, useMemo, useState } from "react";
import { addHours, differenceInSeconds } from "date-fns";

import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.min.css";

import Modal from "react-modal";
import DatePicker, { registerLocale } from "react-datepicker";
import "react-datepicker/dist/react-datepicker.css";
import es from "date-fns/locale/es";
import { useUiStore } from "../../hooks/useUiStore";
import { useCalendarStore } from "../../hooks/useCalendarStore";

registerLocale("es", es);

const customStyles = {
  content: {
    top: "50%",
    left: "50%",
    right: "auto",
    bottom: "auto",
    marginRight: "-50%",
    transform: "translate(-50%, -50%)",
  },
};

Modal.setAppElement("#root");

export const CalendarModal = () => {
  const { isDateModalOpen, closeDateModal } = useUiStore();
  const { activeEvent } = useCalendarStore();

  // const [isOpen, setIsOpen] = useState(true);
  const [formSubmitted, setFormSubmitted] = useState(false);

  const [formValues, setFormValues] = useState({
    title: "",
    notes: "",
    start: new Date(),
    end: addHours(new Date(), 2),
  });

  const titleClass = useMemo(() => {
    if (!formSubmitted) return "";

    return formValues.title.length > 0 ? "" : "is-invalid";
  }, [formValues.title, formSubmitted]);

  useEffect(() => {
    if (activeEvent !== null) {
      setFormValues({ ...activeEvent });
    }
  }, [activeEvent]);

  const onInputChanged = ({ target }) => {
    setFormValues({
      ...formValues,
      [target.name]: target.value,
    });
  };

  const onDateChanged = (event, changing = "") => {
    setFormValues({
      ...formValues,
      [changing]: event,
    });
  };

  const onCloseModal = () => {
    closeDateModal();
  };

  const onSubmit = (event) => {
    event.preventDefault();
    setFormSubmitted(true);

    const difference = differenceInSeconds(
      formValues.end,
      formValues.start
    );

    if (isNaN(difference) || difference <= 0) {
      Swal.fire(
        "Incorrect dates",
        "Review the dates entered",
        "error"
      );
      return;
    }

    if (formValues.title.length <= 0) return;

    console.log(formValues);

    // TODO:
    // Close modal
    // Remove errors on screen
  };

  return (
    <Modal
      isOpen={isDateModalOpen}
      onRequestClose={onCloseModal}
      style={customStyles}
      contentLabel="Example Modal"
      className="modal"
      overlayClassName="modal-fondo"
      closeTimeoutMS={200}
    >
      <h1> Nuevo evento </h1>
      <hr />
      <form className="container" onSubmit={onSubmit}>
        <div className="form-group mb-2">
          <label>Fecha y hora inicio</label>
          <DatePicker
            selected={formValues.start}
            onChange={(event) =>
              onDateChanged(event, "start")
            }
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <div className="form-group mb-2">
          <label>Fecha y hora fin</label>
          <DatePicker
            minDate={formValues.start}
            selected={formValues.end}
            onChange={(event) => onDateChanged(event, "end")}
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <hr />
        <div className="form-group mb-2">
          <label>Titulo y notas</label>
          <input
            type="text"
            className={`form-control ${titleClass}`}
            placeholder="Título del evento"
            name="title"
            autoComplete="off"
            value={formValues.title}
            onChange={onInputChanged}
          />
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Una descripción corta
          </small>
        </div>

        <div className="form-group mb-2">
          <textarea
            type="text"
            className="form-control"
            placeholder="Notas"
            rows="5"
            name="notes"
            value={formValues.notes}
            onChange={onInputChanged}
          ></textarea>
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Información adicional
          </small>
        </div>

        <button
          type="submit"
          className="btn btn-outline-primary btn-block"
        >
          <i className="far fa-save"></i>
          <span> Guardar</span>
        </button>
      </form>
    </Modal>
  );
};
```

### 22.20 Preparar la creación de un nuevo evento

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx
│   │   │   ├── CalendarModal.jsx
│   │   │   ├── FabAddNew.jsx 👈👀
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   └── getMessages.js
│   ├── hooks
│   │   ├── useCalendarStore.js
│   │   └── useUiStore.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── calendar
│   │   │   └── calendarSlice.js
│   │   ├── store.js
│   │   └── ui
│   │       └── uiSlice.js
│   └── styles.css
└── vite.config.js
```

`src/calendar/components/FabAddNew.jsx`

```jsx
import { addHours } from "date-fns";
import { useCalendarStore } from "../../hooks/useCalendarStore";
import { useUiStore } from "../../hooks/useUiStore";

export const FabAddNew = () => {
  const { openDateModal } = useUiStore();
  const { setActiveEvent } = useCalendarStore();

  const handleClickNew = () => {
    setActiveEvent({
      title: "",
      notes: "",
      start: new Date(),
      end: addHours(new Date(), 2),
      bgColor: "#fafafa",
      user: {
        _id: "123",
        name: "Ale",
      },
    });
    openDateModal();
  };

  return (
    <button
      className="btn btn-primary fab"
      onClick={handleClickNew}
    >
      <i className="fas fa-plus"></i>
    </button>
  );
};
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
import { useState } from "react";
import { Calendar } from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import { Navbar } from "../components/Navbar";
import { localizer } from "../../helpers/calendarLocalizer";
import { getMessagesES } from "../../helpers/getMessages";
import { CalendarEvent } from "../components/CalendarEvent";
import { CalendarModal } from "../components/CalendarModal";
import { useUiStore } from "../../hooks/useUiStore";
import { useCalendarStore } from "../../hooks/useCalendarStore";
import { FabAddNew } from "../components/FabAddNew";

export const CalendarPage = () => {
  const { openDateModal } = useUiStore();
  const { events, setActiveEvent } = useCalendarStore();

  const [lastView, setLastView] = useState(
    localStorage.getItem("lastView") || "week"
  );

  const eventStyleGetter = (
    event,
    start,
    end,
    isSelected
  ) => {
    const style = {
      backgroundColor: "#347CF7",
      borderRadius: "0px",
      opacity: "white",
    };

    return {
      style,
    };
  };

  const onDoubleClick = (event) => {
    console.log({ doubleClick: event });

    openDateModal();
  };

  const onSelect = (event) => {
    setActiveEvent(event);
  };

  const onViewChanged = (event) => {
    // console.log({ viewChanged: event });
    localStorage.setItem("lastView", event);

    setLastView(event);
  };

  return (
    <>
      <Navbar />
      <Calendar
        culture="es"
        localizer={localizer}
        events={events}
        defaultView={lastView}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
        messages={getMessagesES()}
        eventPropGetter={eventStyleGetter}
        components={{
          event: CalendarEvent,
        }}
        onDoubleClickEvent={onDoubleClick}
        onSelectEvent={onSelect}
        onView={onViewChanged}
      />
      <CalendarModal />
      <FabAddNew />
    </>
  );
};
```

`src/styles.css`

```css
/* Modal */
.ReactModalPortal > div {
  opacity: 0;
}

.ReactModalPortal .ReactModal__Overlay {
  align-items: center;
  display: flex;
  justify-content: center;
  transition: opacity 0.2s ease-in-out;
  z-index: 999;
}

.modal-fondo {
  background-color: rgba(0, 0, 0, 0.3);
  bottom: 0;
  left: 0;
  right: 0;
  top: 0;
  position: fixed;
}

.ReactModalPortal .ReactModal__Overlay--after-open {
  opacity: 1;
}

.ReactModalPortal .ReactModal__Overlay--before-close {
  opacity: 0;
}

.modal {
  background: white;
  border-radius: 5px;
  color: rgb(51, 51, 51);
  display: inline;
  max-height: 620px;
  max-width: 500px;
  outline: none;
  padding: 10px;
}

/* FABS */
.fab {
  width: 40px;
  height: 40px;

  display: flex;
  justify-content: center;
  align-items: center;

  border-radius: 100%;
  bottom: 25px;
  font-size: 30px;
  padding: 25px;
  position: fixed;
  right: 25px;
}
```

Revisa: `Redux/calendar/events/0/_id`

### 22.21 Añadir un nuevo evento

`src/store/calendar/calendarSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";
import { addHours } from "date-fns";

const tempEvent = {
  _id: new Date().getTime(),
  title: "The boss's birthday.",
  notes: "Buy cake",
  start: new Date(),
  end: addHours(new Date(), 2),
  bgColor: "#fafafa",
  user: {
    _id: "123",
    name: "Ale",
  },
};

export const calendarSlice = createSlice({
  name: "calendar",
  initialState: {
    events: [tempEvent],
    activeEvent: null,
  },
  reducers: {
    onSetActiveEvent: (state, { payload }) => {
      state.activeEvent = payload;
    },
    onAddNewEvent: (state, { payload }) => {
      state.events.push(payload);
      state.activeEvent = null;
    },
  },
});

export const { onSetActiveEvent, onAddNewEvent } =
  calendarSlice.actions;
```

`src/hooks/useCalendarStore.js`

```js
import { useDispatch, useSelector } from "react-redux";
import {
  onAddNewEvent,
  onSetActiveEvent,
} from "../store/calendar/calendarSlice";

export const useCalendarStore = () => {
  const dispatch = useDispatch();

  const { events, activeEvent } = useSelector(
    (state) => state.calendar
  );

  const setActiveEvent = (calendarEvent) => {
    dispatch(onSetActiveEvent(calendarEvent));
  };

  const startSavingEvent = async (calendarEvent) => {
    // TODO: Access the backend
    // TODO: OK
    if (calendarEvent._id) {
      // Uppdating
    } else {
      // Creating
      dispatch(
        onAddNewEvent({
          ...calendarEvent,
          _id: new Date().getTime(),
        })
      );
    }
  };

  return {
    // Properties
    events,
    activeEvent,

    // Methods
    setActiveEvent,
    startSavingEvent,
  };
};
```

`src/calendar/components/CalendarModal.jsx`

```jsx
import { useEffect, useMemo, useState } from "react";
import { addHours, differenceInSeconds } from "date-fns";

import Swal from "sweetalert2";
import "sweetalert2/dist/sweetalert2.min.css";

import Modal from "react-modal";
import DatePicker, { registerLocale } from "react-datepicker";
import "react-datepicker/dist/react-datepicker.css";
import es from "date-fns/locale/es";
import { useUiStore } from "../../hooks/useUiStore";
import { useCalendarStore } from "../../hooks/useCalendarStore";

registerLocale("es", es);

const customStyles = {
  content: {
    top: "50%",
    left: "50%",
    right: "auto",
    bottom: "auto",
    marginRight: "-50%",
    transform: "translate(-50%, -50%)",
  },
};

Modal.setAppElement("#root");

export const CalendarModal = () => {
  const { isDateModalOpen, closeDateModal } = useUiStore();
  const { activeEvent, startSavingEvent } =
    useCalendarStore();

  // const [isOpen, setIsOpen] = useState(true);
  const [formSubmitted, setFormSubmitted] = useState(false);

  const [formValues, setFormValues] = useState({
    title: "",
    notes: "",
    start: new Date(),
    end: addHours(new Date(), 2),
  });

  const titleClass = useMemo(() => {
    if (!formSubmitted) return "";

    return formValues.title.length > 0 ? "" : "is-invalid";
  }, [formValues.title, formSubmitted]);

  useEffect(() => {
    if (activeEvent !== null) {
      setFormValues({ ...activeEvent });
    }
  }, [activeEvent]);

  const onInputChanged = ({ target }) => {
    setFormValues({
      ...formValues,
      [target.name]: target.value,
    });
  };

  const onDateChanged = (event, changing = "") => {
    setFormValues({
      ...formValues,
      [changing]: event,
    });
  };

  const onCloseModal = () => {
    closeDateModal();
  };

  const onSubmit = async (event) => {
    event.preventDefault();
    setFormSubmitted(true);

    const difference = differenceInSeconds(
      formValues.end,
      formValues.start
    );

    if (isNaN(difference) || difference <= 0) {
      Swal.fire(
        "Incorrect dates",
        "Review the dates entered",
        "error"
      );
      return;
    }

    if (formValues.title.length <= 0) return;

    console.log(formValues);

    // TODO:
    await startSavingEvent(formValues);
    closeDateModal();
    setFormSubmitted(false);
  };

  return (
    <Modal
      isOpen={isDateModalOpen}
      onRequestClose={onCloseModal}
      style={customStyles}
      contentLabel="Example Modal"
      className="modal"
      overlayClassName="modal-fondo"
      closeTimeoutMS={200}
    >
      <h1> Nuevo evento </h1>
      <hr />
      <form className="container" onSubmit={onSubmit}>
        <div className="form-group mb-2">
          <label>Fecha y hora inicio</label>
          <DatePicker
            selected={formValues.start}
            onChange={(event) =>
              onDateChanged(event, "start")
            }
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <div className="form-group mb-2">
          <label>Fecha y hora fin</label>
          <DatePicker
            minDate={formValues.start}
            selected={formValues.end}
            onChange={(event) => onDateChanged(event, "end")}
            className="form-control"
            dateFormat="Pp"
            showTimeSelect
            locale="es"
            timeCaption="Hora"
          />
        </div>

        <hr />
        <div className="form-group mb-2">
          <label>Titulo y notas</label>
          <input
            type="text"
            className={`form-control ${titleClass}`}
            placeholder="Título del evento"
            name="title"
            autoComplete="off"
            value={formValues.title}
            onChange={onInputChanged}
          />
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Una descripción corta
          </small>
        </div>

        <div className="form-group mb-2">
          <textarea
            type="text"
            className="form-control"
            placeholder="Notas"
            rows="5"
            name="notes"
            value={formValues.notes}
            onChange={onInputChanged}
          ></textarea>
          <small
            id="emailHelp"
            className="form-text text-muted"
          >
            Información adicional
          </small>
        </div>

        <button
          type="submit"
          className="btn btn-outline-primary btn-block"
        >
          <i className="far fa-save"></i>
          <span> Guardar</span>
        </button>
      </form>
    </Modal>
  );
};
```

Revisa: `Redux/calendar/events/1/`

### 22.22 Editar el evento activo

`src/store/calendar/calendarSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";
import { addHours } from "date-fns";

const tempEvent = {
  _id: new Date().getTime(),
  title: "The boss's birthday.",
  notes: "Buy cake",
  start: new Date(),
  end: addHours(new Date(), 2),
  bgColor: "#fafafa",
  user: {
    _id: "123",
    name: "Ale",
  },
};

export const calendarSlice = createSlice({
  name: "calendar",
  initialState: {
    events: [tempEvent],
    activeEvent: null,
  },
  reducers: {
    onSetActiveEvent: (state, { payload }) => {
      state.activeEvent = payload;
    },
    onAddNewEvent: (state, { payload }) => {
      state.events.push(payload);
      state.activeEvent = null;
    },
    onUpdateEvent: (state, { payload }) => {
      state.events = state.events.map((event) => {
        if (event._id === payload._id) {
          return payload;
        }

        return event;
      });
    },
  },
});

export const {
  onSetActiveEvent,
  onAddNewEvent,
  onUpdateEvent,
} = calendarSlice.actions;
```

`src/hooks/useCalendarStore.js`

```js
import { useDispatch, useSelector } from "react-redux";
import {
  onAddNewEvent,
  onSetActiveEvent,
  onUpdateEvent,
} from "../store/calendar/calendarSlice";

export const useCalendarStore = () => {
  const dispatch = useDispatch();

  const { events, activeEvent } = useSelector(
    (state) => state.calendar
  );

  const setActiveEvent = (calendarEvent) => {
    dispatch(onSetActiveEvent(calendarEvent));
  };

  const startSavingEvent = async (calendarEvent) => {
    // TODO: Access the backend
    // TODO: OK
    if (calendarEvent._id) {
      // Uppdating
      dispatch(onUpdateEvent({ ...calendarEvent }));
    } else {
      // Creating
      dispatch(
        onAddNewEvent({
          ...calendarEvent,
          _id: new Date().getTime(),
        })
      );
    }
  };

  return {
    // Properties
    events,
    activeEvent,

    // Methods
    setActiveEvent,
    startSavingEvent,
  };
};
```

Revisa: `Redux/calendar/events/1/`

### 22.23 Eliminar evento

Estructura:

```bash
.
├── eslint.config.js
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx
│   │   │   ├── CalendarModal.jsx
│   │   │   ├── FabAddNew.jsx
│   │   │   ├── FabDelete.jsx 👈👀
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   └── getMessages.js
│   ├── hooks
│   │   ├── useCalendarStore.js
│   │   └── useUiStore.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── calendar
│   │   │   └── calendarSlice.js
│   │   ├── store.js
│   │   └── ui
│   │       └── uiSlice.js
│   └── styles.css
└── vite.config.js
```

`src/calendar/components/FabDelete.jsx`

```jsx
import { useCalendarStore } from "../../hooks/useCalendarStore";

export const FabDelete = () => {
  const { startDeletingEvent, hasEventSelected } =
    useCalendarStore();

  const handleDelete = () => {
    startDeletingEvent();
  };

  return (
    <button
      className="btn btn-danger fab-danger"
      onClick={handleDelete}
      style={{
        display: hasEventSelected ? "" : "none",
      }}
    >
      <i className="fas fa-trash-alt"></i>
    </button>
  );
};
```

`src/calendar/pages/CalendarPage.jsx`

```jsx
import { useState } from "react";
import { Calendar } from "react-big-calendar";
import "react-big-calendar/lib/css/react-big-calendar.css";
import { Navbar } from "../components/Navbar";
import { localizer } from "../../helpers/calendarLocalizer";
import { getMessagesES } from "../../helpers/getMessages";
import { CalendarEvent } from "../components/CalendarEvent";
import { CalendarModal } from "../components/CalendarModal";
import { useUiStore } from "../../hooks/useUiStore";
import { useCalendarStore } from "../../hooks/useCalendarStore";
import { FabAddNew } from "../components/FabAddNew";
import { FabDelete } from "../components/FabDelete";

export const CalendarPage = () => {
  const { openDateModal } = useUiStore();
  const { events, setActiveEvent } = useCalendarStore();

  const [lastView, setLastView] = useState(
    localStorage.getItem("lastView") || "week"
  );

  const eventStyleGetter = (
    event,
    start,
    end,
    isSelected
  ) => {
    const style = {
      backgroundColor: "#347CF7",
      borderRadius: "0px",
      opacity: "white",
    };

    return {
      style,
    };
  };

  const onDoubleClick = (event) => {
    console.log({ doubleClick: event });

    openDateModal();
  };

  const onSelect = (event) => {
    setActiveEvent(event);
  };

  const onViewChanged = (event) => {
    // console.log({ viewChanged: event });
    localStorage.setItem("lastView", event);

    setLastView(event);
  };

  return (
    <>
      <Navbar />
      <Calendar
        culture="es"
        localizer={localizer}
        events={events}
        defaultView={lastView}
        startAccessor="start"
        endAccessor="end"
        style={{ height: "calc(100vh - 80px)" }}
        messages={getMessagesES()}
        eventPropGetter={eventStyleGetter}
        components={{
          event: CalendarEvent,
        }}
        onDoubleClickEvent={onDoubleClick}
        onSelectEvent={onSelect}
        onView={onViewChanged}
      />
      <CalendarModal />
      <FabAddNew />
      <FabDelete />
    </>
  );
};
```

`src/store/calendar/calendarSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";
import { addHours } from "date-fns";

const tempEvent = {
  _id: new Date().getTime(),
  title: "The boss's birthday.",
  notes: "Buy cake",
  start: new Date(),
  end: addHours(new Date(), 2),
  bgColor: "#fafafa",
  user: {
    _id: "123",
    name: "Ale",
  },
};

export const calendarSlice = createSlice({
  name: "calendar",
  initialState: {
    events: [tempEvent],
    activeEvent: null,
  },
  reducers: {
    onSetActiveEvent: (state, { payload }) => {
      state.activeEvent = payload;
    },
    onAddNewEvent: (state, { payload }) => {
      state.events.push(payload);
      state.activeEvent = null;
    },
    onUpdateEvent: (state, { payload }) => {
      state.events = state.events.map((event) => {
        if (event._id === payload._id) {
          return payload;
        }

        return event;
      });
    },
    onDeleteEvent: (state) => {
      if (state.activeEvent) {
        state.events = state.events.filter(
          (event) => event._id !== state.activeEvent._id
        );
        state.activeEvent = null;
      }
    },
  },
});

export const {
  onSetActiveEvent,
  onAddNewEvent,
  onUpdateEvent,
  onDeleteEvent,
} = calendarSlice.actions;
```

`src/hooks/useCalendarStore.js`

```js
import { useDispatch, useSelector } from "react-redux";
import {
  onAddNewEvent,
  onDeleteEvent,
  onSetActiveEvent,
  onUpdateEvent,
} from "../store/calendar/calendarSlice";

export const useCalendarStore = () => {
  const dispatch = useDispatch();

  const { events, activeEvent } = useSelector(
    (state) => state.calendar
  );

  const setActiveEvent = (calendarEvent) => {
    dispatch(onSetActiveEvent(calendarEvent));
  };

  const startSavingEvent = async (calendarEvent) => {
    // TODO: Access the backend
    // TODO: OK
    if (calendarEvent._id) {
      // Uppdating
      dispatch(onUpdateEvent({ ...calendarEvent }));
    } else {
      // Creating
      dispatch(
        onAddNewEvent({
          ...calendarEvent,
          _id: new Date().getTime(),
        })
      );
    }
  };

  const startDeletingEvent = () => {
    // TODO: Access the backend
    dispatch(onDeleteEvent());
  };

  return {
    // Properties
    events,
    activeEvent,
    hasEventSelected: !!activeEvent,

    // Methods
    startDeletingEvent,
    setActiveEvent,
    startSavingEvent,
  };
};
```

`src/styles.css`

```css
/* Modal */
.ReactModalPortal > div {
  opacity: 0;
}

.ReactModalPortal .ReactModal__Overlay {
  align-items: center;
  display: flex;
  justify-content: center;
  transition: opacity 0.2s ease-in-out;
  z-index: 999;
}

.modal-fondo {
  background-color: rgba(0, 0, 0, 0.3);
  bottom: 0;
  left: 0;
  right: 0;
  top: 0;
  position: fixed;
}

.ReactModalPortal .ReactModal__Overlay--after-open {
  opacity: 1;
}

.ReactModalPortal .ReactModal__Overlay--before-close {
  opacity: 0;
}

.modal {
  background: white;
  border-radius: 5px;
  color: rgb(51, 51, 51);
  display: inline;
  max-height: 620px;
  max-width: 500px;
  outline: none;
  padding: 10px;
}

/* FABS */
.fab {
  width: 40px;
  height: 40px;

  display: flex;
  justify-content: center;
  align-items: center;

  border-radius: 100%;
  bottom: 25px;
  font-size: 20px;
  padding: 25px;
  position: fixed;
  right: 25px;
}

.fab-danger {
  width: 40px;
  height: 40px;

  display: flex;
  justify-content: center;
  align-items: center;

  border-radius: 100%;
  bottom: 25px;
  font-size: 20px;
  padding: 25px;
  position: fixed;
  left: 25px;
}
```

### 22.24 Redux - serializableCheck

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { uiSlice } from "./ui/uiSlice";
import { calendarSlice } from "./calendar/calendarSlice";

export const store = configureStore({
  reducer: {
    calendar: calendarSlice.reducer,
    ui: uiSlice.reducer,
  },
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware({
      serializableCheck: false,
    }),
});
```

### 22.25 Código fuente de la sección

Aquí les dejo el repositorio por si lo necesitan comparar contra el mío o por si necesitan tenerlo en Github.

[**Fin de la sección 22 - CalendarApp - Github**](https://github.com/Klerith/react-mern-calendar/tree/fin-seccion-22)

## 🟣 23. CalendarApp - Backend - Node, Express, Mongo

### 23.1 Introducción a la sección

### 23.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Node
- Express
- Mongoose
- Modelos
- Controllers
- Middlewares de Express
- JWT
- Autenticación pasiva
- Payloas
- Encriptación
- Rutas
- CORS
- Revalidar tokens
- MongoDB
- MongoAtlas
- MongoCompass

Es una sección bastante pesada en el aspecto de que no es React lo que veremos, pero todo lo haremos con JavaScript, y ya debemos de estar familiarizados con él.

El backend que haremos aquí es robusto y lo podrían utilizar en proyectos reales, espero que lo aprovechen y sobre todo aprendan bastante.

Si quieren saber más sobre Node, recuerden que tengo un curso especializado en ese tema.

### 23.3 Objetivo al final de la sección

### 23.4 Inicio de proyecto - CalendarApp Node Backend

```bash
10-calendar-frontend # Old
10-calendar-backend  # New

cd 10-calendar-backend
npm init -y
```

Estructura:

```bash
.
├── index.js
└── package.json
```

`index.js`

```js
console.log("Hi world!!");
console.log("Other message!!");
```

```bash
node index.js
node --watch index.js
```

`package.json`

```js
{
  "name": "10-calendar-backend",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "node --watch index.js", 👈👀
    "start": "node index.js" 👈👀
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "type": "commonjs"
}
```

Luego:

```bash
# Modo producción
npm start
# Modo desarrollo
npm run dev
```

> 📌 Nota: Actualmente, ya no es necesario instalar `sudo npm i nodemon -g`, ya que existe una forma nativa de ver los cambios sin instalar dependencias 👉 `node --watch index.js`

### 23.5 Configurando Express

Para esta clase Postman web no me funcionó así que lo instalaré.

```bash
# Install Postman
## Download Postman
https://www.postman.com/downloads/

## Remove trash
sudo rm -rf "/opt/Postman Agent"
sudo rm -rf /opt/Postman

## Unzip the entire Postman file
cd ~/Downloads
tar -xvzf postman-linux-x64.tar.gz

## Move
sudo mv Postman /opt/
sudo mv ~/Downloads/Postman /opt/ 👈👀

## Create a symbolic link to open it from anywhere
sudo ln -s /opt/Postman/Postman /usr/bin/postman

## Try running it
postman
```

```bash
# Create the .desktop file
vim ~/.local/share/applications/postman.desktop

# Paste: i
[Desktop Entry]
Encoding=UTF-8
Name=Postman
Exec=/opt/Postman/Postman
Icon=/opt/Postman/app/resources/app/assets/icon.png
Terminal=false
Type=Application
Categories=Development;

# Save: :wq

# Refresh the shortcut cache
update-desktop-database ~/.local/share/applications/
```

```bash
# Install
npm i express
```

Para poder usar importaciones modernas debes cambiar el `"type": "module"` en el archivo `package.json` con esto podrás usar `import` sin problemas.

`package.json`

```js
{
  "name": "10-calendar-backend",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "node --watch index.js",
    "start": "node index.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  // "type": "commonjs",
  "type": "module", 👈👀
  "dependencies": {
    "express": "^5.1.0"
  }
}
```

`index.js`

```js
// const express = require("express");
import express from "express";

// Create the Express server
const app = express();

// Rutes
app.get("/", (req, res) => { 👈👀👇
  console.log("The / is required.");

  res.json({
    ok: true,
  });
});

// Listen to requests
app.listen(4000, () => {
  console.log("Server running on port");
});
```

Para hacer pruebas comenta `res.json({ ok: true, })`, ahora ingresa a `Postman/workspace/My-Workspace` y abre una pestaña nueva:

`Get: localhost:4000/` **Send** En `Body` verás:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Error</title>
  </head>

  <body>
    <pre>Cannot GET /</pre> 👈👀
  </body>
</html>
```

Esto también aparece en la web, si buscas `localhost:4000/` obtendrás `Cannot GET /`

Si recargas la web o usas `Send`  de Postman, en consola obtenemos el mensaje:

```bash
Restarting 'index.js'
Server running on port
The / is required.
```

Ahora descomenta `res.json({ ok: true, })` verás en la web, también aparece en Postman:

```bash
{
"ok": true
}
```

### 23.6 Variables de entorno y carpeta pública

Estructura:

```bash
.
├── .env 👈👀
├── .git
├── .gitignore
├── index.html
├── index.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
└── public 👈👀👇
    ├── index.html
    └── styles.css
```

```bash
npm i dotenv
```

`public/index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />
    <link rel="stylesheet" href="./styles.css" />
    <title>Demo App</title>
  </head>
  <body>
    <h1>Blocked</h1>
  </body>
</html>
```

`public/styles.css`

```css
html,
body {
  background-color: grey;
}
```

`.env`

```
PORT=4000
```

`index.js`

```js
import express from "express";
import "dotenv/config";
// import dotenv from "dotenv";

// dotenv.config({ path: ".env" });

console.log(process.env);

// Create the Express server
const app = express();

// Rutes
// Public directory
app.use(express.static("public"));

// app.get("/", (req, res) => {
//   console.log("The / is required.");

//   res.json({
//     ok: true,
//   });
// });

// Listen to requests
app.listen(process.env.PORT, () => {
  console.log(`Server running on port ${process.env.PORT}`);
});
```

En la web `http://localhost:4000/` verás la web y en consola verás `PORT: '4000'`.

### 23.7 Creando las rutas relacionadas a usuarios

Estructura:

```bash
.
├── .env
├── .git
├── .gitignore
├── index.html
├── index.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes 👈👀👇
    └── auth.js
```

`routes/auth.js`

```js
/* 
  User paths / Auth
  host + /api/auth
*/

import { Router } from "express";

const router = Router();

router.get("/", (req, res) => {
  console.log("The / is required.");

  res.json({
    ok: true,
  });
});

// module.exports = router;
export { router };
```

`index.js`

```js
import express from "express";
import "dotenv/config";
import { router as authRoutes } from "./routes/auth.js";

// Create the Express server
const app = express();

// Public directory
app.use(express.static("public"));

// Rutes
app.use("/api/auth", authRoutes);
// TODO: CRUD: Events

// Listen to requests
app.listen(process.env.PORT, () => {
  console.log(`Server running on port ${process.env.PORT}`);
});
```

En consola seguimos viendo:

```bash
Restarting 'index.js'
Server running on port 4000
```

Probamos `GET: localhost:4000/` y luego `GET: localhost:4000/api/auth` en Postman. Primero veremos el código de la web simple que implementamos, luego veremos esto: 

```js
{
  "ok": true
}
```

### 23.8 Endpoints de remover, crear y login

Estructura:

```bash
.
├── controllers 👈👀
│   └── auth.js
├── .env
├── .git
├── .gitignore
├── index.html
├── index.js
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes
    └── auth.js
```

`routes/auth.js`

```js
/* 
  User paths / Auth
  host + /api/auth
*/

import { Router } from "express";
import {
  createUser,
  loginUser,
  revalidateToken,
} from "../controllers/auth.js";

const router = Router();

router.post("/new", createUser);
router.post("/", loginUser);
router.get("/renew", revalidateToken);

export { router };
```

`controllers/auth.js`

```js
import { response } from "express";

export const createUser = (req, res = response) => {
  res.json({
    ok: true,
    msg: "register",
  });
};

export const loginUser = (req, res) => {
  res.json({
    ok: true,
    msg: "login",
  });
};

export const revalidateToken = (req, res) => {
  res.json({
    ok: true,
    msg: "renew",
  });
};

// module.exports = { createUser };
```

Probamos: `POST: localhost:4000/api/auth/new` `POST: localhost:4000/api/auth/` y `GET: localhost:4000/api/auth/new`.

### 23.9 Recuperar información de un posteo

En Postman `POST: localhost:4000/api/auth/new` `Body/raw` y `Text/JSON`

```json
{
  "name": "Ale Roses",
  "email": "aleroses@gmail.com",
  "password": "123456"
}
```

Como es `json` debe ir entre comillas. Dale a `Send` y revisa la consola:

```bash
  params: [Object: null prototype] {},
  body: { 👈👀👇
    name: 'Ale Roses',
    email: 'aleroses@gmail.com',
    password: '123456'
  },
  length: undefined,
  _eventsCount: 0,
  route: Route {
    path: '/new',
    stack: [ [Layer] ],
    methods: [Object: null prototype] { post: true }
  },
  Symbol(shapeMode): true,
  Symbol(kCapture): false,
  Symbol(kHeaders): {
    'content-type': 'application/json',
    'user-agent': 'PostmanRuntime/7.48.0',
    accept: '*/*',
    'postman-token': 'df7759a2-d012-4660-80ad-f94d7ca816cd',
    host: 'localhost:4000',
    'accept-encoding': 'gzip, deflate, br',
    connection: 'keep-alive',
    'content-length': '82'
  },
  Symbol(kHeadersCount): 16,
  Symbol(kTrailers): null,
  Symbol(kTrailersCount): 0
}
```

`controllers/auth.js`

```js
import { response } from "express";

export const createUser = (req, res = response) => {
  // console.log(req.body);
  const { name, email, password } = req.body;

  if (name.length < 5) {
    return res.status(400).json({
      ok: false,
      msg: "The name must be 5 letters long.",
    });
  }

  res.json({
    ok: true,
    msg: "register",
    name,
    email,
    password,
  });
};

export const loginUser = (req, res = response) => {
  const { email, password } = req.body;

  res.json({
    ok: true,
    msg: "login",
    email,
    password,
  });
};

export const revalidateToken = (req, res = response) => {
  res.json({
    ok: true,
    msg: "renew",
  });
};

// module.exports = { createUser };
```

`index.js`

```js
import express from "express";
import "dotenv/config";
import { router as authRoutes } from "./routes/auth.js";

// Create the Express server
const app = express();

// Public directory
app.use(express.static("public"));

// Reading and parsing the body
app.use(express.json()); 👈👀

// Rutes
app.use("/api/auth", authRoutes);
// TODO: CRUD: Events

// Listen to requests
app.listen(process.env.PORT, () => {
  console.log(`Server running on port ${process.env.PORT}`);
});
```

[Estándar Códigos de Error](https://www.restapitutorial.com/httpstatuscodes)

### 23.10 Express Validator

Instalar [Express validator](https://www.npmjs.com/package/express-validator)

```bash
npm i express-validator
```

`routes/auth.js`

```js
/* 
  User paths / Auth
  host + /api/auth
*/

import { Router } from "express";
import { check } from "express-validator";
import {
  createUser,
  loginUser,
  revalidateToken,
} from "../controllers/auth.js";

const router = Router();

router.post(
  "/new",
  [
    // Middlewares
    check("name", "The name is mandatory.").not().isEmpty(),
    check("email", "The email is mandatory.").isEmail(),
    check(
      "password",
      "The password must be 6 characters long."
    ).isLength({ min: 6 }),
  ],
  createUser
);
router.post(
  "/",
  [
    check("email", "The email is mandatory.").isEmail(),
    check(
      "password",
      "The password must be 6 characterslong."
    ).isLength({ min: 6 }),
  ],
  loginUser
);
router.get("/renew", revalidateToken);

// module.exports = router;
export { router };
```

`controllers/auth.js`

```js
import { response } from "express";
import { validationResult } from "express-validator";

export const createUser = (req, res = response) => {
  // console.log(req.body);
  const { name, email, password } = req.body;

  // Error handling
  const errors = validationResult(req);

  if (!errors.isEmpty()) {
    return res.status(400).json({
      ok: false,
      errors: errors.mapped(),
    });
  }

  res.status(201).json({
    ok: true,
    msg: "register",
    name,
    email,
    password,
  });
};

export const loginUser = (req, res = response) => {
  // Error handling
  const errors = validationResult(req);

  if (!errors.isEmpty()) {
    return res.status(400).json({
      ok: false,
      errors: errors.mapped(),
    });
  }

  const { email, password } = req.body;

  res.json({
    ok: true,
    msg: "login",
    email,
    password,
  });
};

export const revalidateToken = (req, res = response) => {
  res.json({
    ok: true,
    msg: "renew",
  });
};

// module.exports = { createUser };
```

Prueba `POST: localhost:4000/api/auth/new` quitando y añadiendo las `keys` y sus `valores` deberían aparecer los mensajes de error:

```bash
{
  "name": "Ale Roses",
  "email": "aleroses@gmail.com",
  "password": "123456"
}
```

Prueba también `POST: localhost:4000/api/auth/`.

### 23.11 Custom Middlewares

Estructura:

```bash
.
├── controllers
│   └── auth.js
├── .env
├── .git
├── .gitignore
├── index.html
├── index.js
├── LICENSE
├── middlewares
│   └── validate-fields.js
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes
    └── auth.js
```

`middlewares/validate-fields.js`

```js
import { response } from "express";
import { validationResult } from "express-validator";

export const validateFields = (req, res = response, next) => {
  // Error handling
  const errors = validationResult(req);

  if (!errors.isEmpty()) {
    return res.status(400).json({
      ok: false,
      errors: errors.mapped(),
    });
  }

  next();
};
```

`controllers/auth.js`

```js
import { response } from "express";

export const createUser = (req, res = response) => {
  const { name, email, password } = req.body;

  res.status(201).json({
    ok: true,
    msg: "register",
    name,
    email,
    password,
  });
};

export const loginUser = (req, res = response) => {
  const { email, password } = req.body;

  res.json({
    ok: true,
    msg: "login",
    email,
    password,
  });
};

export const revalidateToken = (req, res = response) => {
  res.json({
    ok: true,
    msg: "renew",
  });
};
```

`routes/auth.js`

```js
/* 
  User paths / Auth
  host + /api/auth
*/

import { Router } from "express";
import { check } from "express-validator";
import { validateFields } from "../middlewares/validate-fields.js";
import {
  createUser,
  loginUser,
  revalidateToken,
} from "../controllers/auth.js";

const router = Router();

router.post(
  "/new",
  [
    // Middlewares
    check("name", "The name is mandatory.").not().isEmpty(),
    check("email", "The email is mandatory.").isEmail(),
    check(
      "password",
      "The password must be 6 characters long."
    ).isLength({ min: 6 }),
    validateFields,
  ],
  createUser
);
router.post(
  "/",
  [
    check("email", "The email is mandatory.").isEmail(),
    check(
      "password",
      "The password must be 6 characterslong."
    ).isLength({ min: 6 }),
    validateFields,
  ],
  loginUser
);
router.get("/renew", revalidateToken);

// module.exports = router;
export { router };
```

### 23.12 Configuración de base de datos

Crea una cuenta:

- [Mongodb - Atlas](https://account.mongodb.com/account/login)  
- [MongooseJS.com](https://mongoosejs.com/)

#### Crear un Cluster

Dentro de la pestaña `Clusters`:

`Create a closter/Free` lo demás dejarlo por defecto.

- Cluster Name: `CalendarDB`

Credenciales de Administrador:

- **Username** alevrs_db_user
- **Password** AA22fr4jfpZyqX7L

#### Conectarnos a MongoBD Compass

Dentro de la pestaña `Clusters`:

🟢 `calendarDB`: Conectar

Access your data through tools:

	- Elige `Compass`

Connecting with MongoDB Compass:

	Si ya tienes instalado `Compass` elige esa opción si no, instálalo. 
	
	1. Elije la ultima versión.

**Pasos para instalar MongoDB Compass en Linux Mint**

Una vez descargado el archivo `mongodb-compass_1.46.11_amd64.deb` en la carpeta  `Descargas`.

🧭 PASO 1: Abre una terminal

Presiona **Ctrl + Alt + T** o búscala como “Terminal”.

🗂️ PASO 2: Navega hasta el directorio donde está el archivo

```bash
cd ~/Descargas
```

_(Si está en otra carpeta, cambia la ruta según corresponda.)_

⚙️ PASO 3: Instala el paquete `.deb`

Ejecuta el siguiente comando con privilegios de administrador:

```bash
sudo dpkg -i mongodb-compass_1.46.11_amd64.deb
```

⚠️ PASO 4: Corrige dependencias si aparecen errores

A veces `dpkg` muestra errores de dependencias. En ese caso, ejecútalo:

```bash
sudo apt -f install
```

Esto descargará e instalará los paquetes faltantes.

🧩 PASO 5: Verifica la instalación

Puedes verificar si se instaló correctamente ejecutando:

```bash
mongodb-compass
```

O buscándolo en el menú de inicio como **“MongoDB Compass”**.

🧹 OPCIONAL: Si deseas desinstalarlo después

```bash
sudo apt remove mongodb-compass
```

2. Copy the connection string, then open MongoDB Compass

	Use this connection string in your application:
	
	`mongodb+srv://alevrs_db_user:<db_password>@calendardb.l8x2lf4.mongodb.net/`

Queda algo así:

`mongodb+srv://alevrs_db_user:AA22fr4jfpZyqX7L@calendardb.l8x2lf4.mongodb.net/`

Lo pegamos en la **Mongo Compass**

![mongo](https://i.postimg.cc/L5wnJ0cg/23-12-mongo.png)

Para el ejemplo vamos a crear un usuario y una contraseña:

Pestaña `Database Access` y `+Add New Database User`

Authentication Method:

	- Password

Password Authentication

	- DB user: mern-user
	- Password: HAzCB7Tw4gQ3ln1m

Built-in Role: Select one built-in role for this user.

	Read and Write to any database

El enlace que usaremos queda algo así:

`mongodb+srv://mern-user:HAzCB7Tw4gQ3ln1m@calendardb.l8x2lf4.mongodb.net/`

En `MongoDB Compass` añádelo a favoritos.

### 23.13 Conectar Node a Mongo Atlas

```bash
# Install Mongoose
npm i mongoose
```

Estructura:

```bash
.
├── controllers
│   └── auth.js
├── database
│   └── config.js
├── .env
├── .git
├── .gitignore
├── index.html
├── index.js
├── LICENSE
├── middlewares
│   └── validate-fields.js
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes
    └── auth.js
```

`.env`

```
PORT=4000
DB_CNN=mongodb+srv://mern-user:HAzCB7Tw4gQ3ln1m@calendardb.l8x2lf4.mongodb.net/mern_calendar
```

`index.js`

```js
import express from "express";
import "dotenv/config";
import { router as authRoutes } from "./routes/auth.js";
import { dbConnection } from "./database/config.js";

// Create the Express server
const app = express();

// Data Base
dbConnection();

// Public directory
app.use(express.static("public"));

// Reading and parsing the body
app.use(express.json());

// Rutes
app.use("/api/auth", authRoutes);
// TODO: CRUD: Events

// Listen to requests
app.listen(process.env.PORT, () => {
  console.log(`Server running on port ${process.env.PORT}`);
});
```

`database/config.js`

```js
import mongoose from "mongoose";

export const dbConnection = async () => {
  try {
    await mongoose.connect(process.env.DB_CNN);

    console.log("DB Online");
  } catch (error) {
    console.log(error);
    throw new Error("Error initializing the database.");
  }
};

// { This is no longer necessary. 👈👀 
//   useNewUrlParser: true,
//   useUnifiedTopology: true,
//   useCreateIndex: true,
// };
```

### 23.14 Crear un usuario en nuestra Base de Datos

Estructura:

```bash
.
├── controllers
│   └── auth.js
├── database
│   └── config.js
├── .env
├── .git
├── .gitignore
├── index.html
├── index.js
├── LICENSE
├── middlewares
│   └── validate-fields.js
├── models 👈👀👇
│   └── User.js
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes
    └── auth.js
```

`models/User.js`

```js
import { Schema, model } from "mongoose";

const UserSchema = Schema({
  name: {
    type: String,
    required: true,
  },
  email: {
    type: String,
    required: true,
    unique: true,
  },
  password: {
    type: String,
    required: true,
  },
});

export const User = model("User", UserSchema);
```

`controllers/auth.js`

```js
import { response } from "express";
import { User } from "../models/User.js";

export const createUser = async (req, res = response) => {
  // const { name, email, password } = req.body;

  try {
    const user = new User(req.body);

    await user.save();

    res.status(201).json({
      ok: true,
      msg: "register",
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Please speak to the manager!",
    });
  }
};

export const loginUser = (req, res = response) => {
  const { email, password } = req.body;

  res.json({
    ok: true,
    msg: "login",
    email,
    password,
  });
};

export const revalidateToken = (req, res = response) => {
  res.json({
    ok: true,
    msg: "renew",
  });
};

// module.exports = { createUser };
```

Esto hace aparecer el `mern_calendar` en MongoDB Compass. Dentro de este encontramos `users`

![users](https://i.postimg.cc/hjJ7JNSM/23-14-users.png)

No podrás grabar nuevamente los mismos datos, si lo intentas marcará un error en consola.

### 23.15 Validaciones del usuario

`controllers/auth`

```js
import { response } from "express";
import { User } from "../models/User.js";

export const createUser = async (req, res = response) => {
  const { email, password } = req.body;

  try {
    let user = await User.findOne({ email });

    if (user) {
      return res.status(400).json({
        ok: false,
        msg: "This email address is already in use.",
      });
    }

    user = new User(req.body);

    await user.save();

    res.status(201).json({
      ok: true,
      uid: user.id,
      name: user.name,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Please speak to the manager!",
    });
  }
};

export const loginUser = (req, res = response) => {
  const { email, password } = req.body;

  res.json({
    ok: true,
    msg: "login",
    email,
    password,
  });
};

export const revalidateToken = (req, res = response) => {
  res.json({
    ok: true,
    msg: "renew",
  });
};
```

### 23.16 Encriptar la contraseña

```bash
# Install
npm i bcryptjs
```

`controllers/auth`

```js
import { response } from "express";
import bcrypt from "bcryptjs";
import { User } from "../models/User.js";

export const createUser = async (req, res = response) => {
  const { email, password } = req.body;

  try {
    let user = await User.findOne({ email });

    if (user) {
      return res.status(400).json({
        ok: false,
        msg: "This email address is already in use.",
      });
    }

    user = new User(req.body);

    // Encrypt password
    const salt = bcrypt.genSaltSync();
    user.password = bcrypt.hashSync(password, salt);

    await user.save();

    res.status(201).json({
      ok: true,
      uid: user.id,
      name: user.name,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Please speak to the manager!",
    });
  }
};

export const loginUser = (req, res = response) => {
  const { email, password } = req.body;

  res.json({
    ok: true,
    msg: "login",
    email,
    password,
  });
};

export const revalidateToken = (req, res = response) => {
  res.json({
    ok: true,
    msg: "renew",
  });
};

// module.exports = { createUser };
```

Guardar el servicio en Postman `Post: localhost:4000/api/auth/new`:

- `Ctrl + S`
- `Auth - Create user`
- New folder: `MERN Calendar`

### 23.17 Login de usuario

En Postman saca un duplicado de `Auth - Create user` y nómbralo como `Auth - Login`. Queda así `Post: localhost:4000/api/auth/`.

Usaremos los siguientes datos:

```bash
{
  "email": "aleroses@gmail.com",
  "password": "123456"
}
```

`controllers/auth`

```js
import { response } from "express";
import bcrypt from "bcryptjs";
import { User } from "../models/User.js";

export const createUser = async (req, res = response) => {
  const { email, password } = req.body;

  try {
    let user = await User.findOne({ email });

    if (user) {
      return res.status(400).json({
        ok: false,
        msg: "This email address is already in use.",
      });
    }

    user = new User(req.body);

    // Encrypt password
    const salt = bcrypt.genSaltSync();
    user.password = bcrypt.hashSync(password, salt);

    await user.save();

    res.status(201).json({
      ok: true,
      uid: user.id,
      name: user.name,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Please speak to the manager!",
    });
  }
};

export const loginUser = async (req, res = response) => {
  const { email, password } = req.body;

  try {
    const user = await User.findOne({ email });

    if (!user) {
      return res.status(400).json({
        ok: false,
        msg: "The user doesn't exist with that email address.",
      });
    }

    // Confirm passwords
    const validPassword = bcrypt.compareSync(
      password,
      user.password
    );

    if (!validPassword) {
      return res.status(400).json({
        ok: false,
        msg: "Incorrect password",
      });
    }

    // Generate our JWT (JSON Web Token)
    res.json({
      ok: true,
      uid: user.id,
      name: user.name,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Please speak to the manager!",
    });
  }
};

export const revalidateToken = (req, res = response) => {
  res.json({
    ok: true,
    msg: "renew",
  });
};
```

En Postman siempre usa `Ctrl + S` para guardar los cambios.

### 23.18 Generar un Json Web Token

Estructura:

```bash
.
├── controllers
│   └── auth.js
├── database
│   └── config.js
├── .env
├── .git
├── .gitignore
├── helpers 👈👀👇
│   └── jwt.js
├── index.html
├── index.js
├── LICENSE
├── middlewares
│   └── validate-fields.js
├── models
│   └── User.js
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes
    └── auth.js
```

```bash
# Install https://www.npmjs.com/package/jsonwebtoken
npm i jsonwebtoken
```

`.env`

```
PORT=4000
DB_CNN=mongodb+srv://mern-user:HAzCB7Tw4gQ3ln1m@calendardb.l8x2lf4.mongodb.net/mern_calendar
SECRET_JWT_SEED=This-is-@-secret-Word
```

`helpers/jwt.js`

```js
import jwt from "jsonwebtoken";

export const generateJWT = (uid, name) => {
  return new Promise((resolve, reject) => {
    const payload = { uid, name };

    jwt.sign(
      payload,
      process.env.SECRET_JWT_SEED,
      {
        expiresIn: "2h",
      },
      (err, token) => {
        if (err) {
          console.log(err);

          reject("The token couldn't be generated!!!");
        }

        resolve(token);
      }
    );
  });
};
```

También funciona:

```js
import jwt from "jsonwebtoken";

export const generateJWT = async (uid, name) => {
  const payload = { uid, name };
  const secret = process.env.SECRET_JWT_SEED;

  try {
    const token = await jwt.sign(payload, secret, {
      expiresIn: "2h",
    });
    return token;
  } catch (error) {
    console.error("Error generating token:", error.message);
    throw new Error("The token couldn't be generated!!!");
  }
};
```

`controllers/auth.js`

```js
import { response } from "express";
import bcrypt from "bcryptjs";
import { User } from "../models/User.js";
import { generateJWT } from "../helpers/jwt.js";

export const createUser = async (req, res = response) => {
  const { email, password } = req.body;

  try {
    let user = await User.findOne({ email });

    if (user) {
      return res.status(400).json({
        ok: false,
        msg: "This email address is already in use.",
      });
    }

    user = new User(req.body);

    // Encrypt password
    const salt = bcrypt.genSaltSync();
    user.password = bcrypt.hashSync(password, salt);

    await user.save();

    // Generate our JWT (JSON Web Token)
    const token = await generateJWT(user.id, user.name);

    res.status(201).json({
      ok: true,
      uid: user.id,
      name: user.name,
      token,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Please speak to the manager!",
    });
  }
};

export const loginUser = async (req, res = response) => {
  const { email, password } = req.body;

  try {
    const user = await User.findOne({ email });

    if (!user) {
      return res.status(400).json({
        ok: false,
        msg: "The user doesn't exist with that email address.",
      });
    }

    // Confirm passwords
    const validPassword = bcrypt.compareSync(
      password,
      user.password
    );

    if (!validPassword) {
      return res.status(400).json({
        ok: false,
        msg: "Incorrect password",
      });
    }

    // Generate our JWT (JSON Web Token)
    const token = await generateJWT(user.id, user.name);

    res.json({
      ok: true,
      uid: user.id,
      name: user.name,
      token,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Please speak to the manager!",
    });
  }
};

export const revalidateToken = (req, res = response) => {
  res.json({
    ok: true,
    msg: "renew",
  });
};
```

En Postman:

Prueba el login: `Post: localhost:4000/api/auth/` copia el token y pégalo en la web JWT para verificarla.

`eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1aWQiOiI2OGU1MWIxMGY1YjFmNDJkOGZjM2RmMGEiLCJuYW1lIjoiQWxlIFJvc2VzIiwiaWF0IjoxNzU5OTQ0NTkyLCJleHAiOjE3NTk5NTE3OTJ9.1_laKPHRVzNxQUYwVrncH-oDjsvH2oBwgmoSx-hg-Jo`

Prueba el create: `Post: localhost:4000/api/auth/new` solo cambia los datos, copia el token y pégalo en la web JWT para verificarla.

[Json Web Token](https://www.jwt.io/)

### 23.19 Revalidar JWT

Estructura:

```bash
.
├── controllers
│   └── auth.js
├── database
│   └── config.js
├── .env
├── .git
├── .gitignore
├── helpers
│   └── jwt.js
├── index.html
├── index.js
├── LICENSE
├── middlewares 👈👀👇
│   ├── validate-fields.js
│   └── validate-jwt.js
├── models
│   └── User.js
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes
    └── auth.js
```

`middlewares/validate-jwt.js`

```js
import { response } from "express";
import jwt from "jsonwebtoken";

export const validateJWT = (req, res = response, next) => {
  // x-token headers
  const token = req.header("x-token");

  // console.log(token);

  if (!token) {
    return res.status(401).json({
      ok: false,
      msg: "There isn't token in the request.",
    });
  }

  try {
    const { uid, name } = jwt.verify(
      token,
      process.env.SECRET_JWT_SEED
    );

    // console.log(payload);

    req.uid = uid;
    req.name = name;
  } catch (error) {
    return res.status(401).json({
      ok: false,
      msg: "Invalid token.",
    });
  }

  next();
};
```

`controllers/auth.js`

```js
import { response } from "express";
import bcrypt from "bcryptjs";
import { User } from "../models/User.js";
import { generateJWT } from "../helpers/jwt.js";

export const createUser = async (req, res = response) => {
  const { email, password } = req.body;

  try {
    let user = await User.findOne({ email });

    if (user) {
      return res.status(400).json({
        ok: false,
        msg: "This email address is already in use.",
      });
    }

    user = new User(req.body);

    // Encrypt password
    const salt = bcrypt.genSaltSync();
    user.password = bcrypt.hashSync(password, salt);

    await user.save();

    // Generate our JWT (JSON Web Token)
    const token = await generateJWT(user.id, user.name);

    res.status(201).json({
      ok: true,
      uid: user.id,
      name: user.name,
      token,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Please speak to the manager!",
    });
  }
};

export const loginUser = async (req, res = response) => {
  const { email, password } = req.body;

  try {
    const user = await User.findOne({ email });

    if (!user) {
      return res.status(400).json({
        ok: false,
        msg: "The user doesn't exist with that email address.",
      });
    }

    // Confirm passwords
    const validPassword = bcrypt.compareSync(
      password,
      user.password
    );

    if (!validPassword) {
      return res.status(400).json({
        ok: false,
        msg: "Incorrect password",
      });
    }

    // Generate our JWT (JSON Web Token)
    const token = await generateJWT(user.id, user.name);

    res.json({
      ok: true,
      uid: user.id,
      name: user.name,
      token,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Please speak to the manager!",
    });
  }
};

export const revalidateToken = async (
  req,
  res = response
) => {
  const { uid, name } = req;

  // Generate a new JWT and return it in this request.
  const token = await generateJWT(uid, name);

  res.json({
    ok: true,
    // uid,
    // name,
    token,
  });
};
```

`routes/auth.js`

```js
/* 
  User paths / Auth
  host + /api/auth
*/

import { Router } from "express";
import { check } from "express-validator";
import { validateFields } from "../middlewares/validate-fields.js";
import {
  createUser,
  loginUser,
  revalidateToken,
} from "../controllers/auth.js";
import { validateJWT } from "../middlewares/validate-jwt.js";

const router = Router();

router.post(
  "/new",
  [
    // Middlewares
    check("name", "The name is mandatory.").not().isEmpty(),
    check("email", "The email is mandatory.").isEmail(),
    check(
      "password",
      "The password must be 6 characters long."
    ).isLength({ min: 6 }),
    validateFields,
  ],
  createUser
);

router.post(
  "/",
  [
    check("email", "The email is mandatory.").isEmail(),
    check(
      "password",
      "The password must be 6 characterslong."
    ).isLength({ min: 6 }),
    validateFields,
  ],
  loginUser
);

router.get("/renew", validateJWT, revalidateToken);

// module.exports = router;
export { router };
```

En Postman duplicar `Login` y renombrar como `Auth - Revalidate JWT`. Ejecutamos `GET: localhost:4000/api/auth/renew`

Entramos a los `Headers`

- Key: `x-token`
- Value: `ABC123`

```json
{
    "ok": true,
    "msg": "renew"
}
```

En consola:

```bash
❯ npm run dev

> 10-calendar-backend@1.0.0 dev
> node --watch index.js

Server running on port 4000
DB Online
ABC123
```

Validemos un Token:

Entramos en `Login`, damos en `SEND` y copiamos el token. Entramos en `Revalidate JWT`, pegamos en el campo `Value` y le damos en `SEND`.

- Key: `x-token`
- Value: `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1aWQiOiI2OGU1MWIxMGY1YjFmNDJkOGZjM2RmMGEiLCJuYW1lIjoiQWxlIFJvc2VzIiwiaWF0IjoxNzU5OTQ5MzQyLCJleHAiOjE3NTk5NTY1NDJ9.CcWNXqe_epjbUGQbZbgJA_7N-vmk_tACmPMW9-tRl4M`

En consola debe aparecer el token.

`Auth - Revalidate JWT` damos en `SEND` y revisamos la consola:

```bash
Restarting 'index.js'
Server running on port 4000
DB Online
{
  uid: '68e51b10f5b1f42d8fc3df0a',
  name: 'Ale Roses',
  iat: 1759949342,
  exp: 1759956542
}
```

### 23.20 Configurar CORS

`index.js`

```js
import express from "express";
import cors from "cors";
import "dotenv/config";
import { router as authRoutes } from "./routes/auth.js";
import { dbConnection } from "./database/config.js";

// Create the Express server
const app = express();

// Data Base
dbConnection();

// CORS
app.use(cors());

// Public directory
app.use(express.static("public"));

// Reading and parsing the body
app.use(express.json());

// Rutes
app.use("/api/auth", authRoutes);
// TODO: CRUD: Events

// Listen to requests
app.listen(process.env.PORT, () => {
  console.log(`Server running on port ${process.env.PORT}`);
});
```

Guarda los cambios en Postman `Ctrl + S`.

[npm - cors](https://www.npmjs.com/package/cors)

### 23.21 Código de la sección

Aquí les dejo el código fuente de la sección por si lo quieren clonar. Recuerden que puede no funcionarles la conexión a la base de datos porque es algo que en cualquier momento yo puedo cambiar, recuerden utilizar su cadena de conexión a Mongo Atlas

[MERN-Calendar-Backend - Autenticación](https://github.com/Klerith/MERN-Calendar-Backend/releases/tag/v1.0.0)

**POSTMAN Backup**

Si necesitan tener en POSTMAN los endpoints creados hasta el momento, pueden descargar y cargar el archivo JSON que está adjunto a la clase mediante el botón de importación en Postman.

![](https://files.cdn.thinkific.com/file_uploads/643563/images/d0d/dfb/a57/1656111035885.jpg)

**Recursos de la lección:**

> - MERN+Calendar.postman_collection.json [Descargar](https://import.cdn.thinkific.com/643563/courses/1901683/MERNCalendarpostman_collection-220624-165026.json)

## 🟣 24. Backend - Eventos del calendario - CRUD

### 24.1 Introducción a la sección

### 24.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- CRUD completo de eventos de calendario
- Modelos
- Validaciones automáticas
- Validaciones personalizadas

Aquí trabajaremos creando todo lo necesario para que podamos insertar, actualiza y eliminar información relacionada a los eventos que nuestra aplicación del calendario necesitará.

### 24.3 Continuación del proyecto - Calendar Backend

Estructura:

```bash
.
├── controllers 👀👇
│   ├── auth.js
│   └── events.js 👈👀
├── database
│   └── config.js
├── .env
├── .git
├── .gitignore
├── helpers
│   └── jwt.js
├── index.html
├── index.js
├── LICENSE
├── middlewares
│   ├── validate-fields.js
│   └── validate-jwt.js
├── models
│   └── User.js
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes 👀👇
    ├── auth.js
    └── events.js 👈👀
```

### 24.4 Resolución de la tarea - CRUD

`routes/events.js`

```js
/* 
  Event Routes
  /api/events
*/

import { Router } from "express";
import { validateJWT } from "../middlewares/validate-jwt.js";
import {
  getEvent,
  createEvent,
  updateEvent,
  deleteEvent,
} from "../controllers/events.js";

const router = Router();

// All of them must undergo JWT validation.
router.use(validateJWT); // Everything is protected.

// Get events
router.get("/", getEvent);

// Create a new event
router.post("/", createEvent);

// Update event
router.put("/:id", updateEvent);

// Delete event
router.delete("/:id", deleteEvent);

export { router };
```

`controllers/events.js`

```js
import { response } from "express";

export const getEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Get events",
  });
};

export const createEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Create event",
  });
};

export const updateEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Update event",
  });
};

export const deleteEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Delete event",
  });
};
```

`index.js`

```js
import express from "express";
import cors from "cors";
import "dotenv/config";
import { router as authRoutes } from "./routes/auth.js";
import { dbConnection } from "./database/config.js";
import { router as eventRoutes } from "./routes/events.js";

// Create the Express server
const app = express();

// Data Base
dbConnection();

// CORS
app.use(cors());

// Public directory
app.use(express.static("public"));

// Reading and parsing the body
app.use(express.json());

// Rutes
app.use("/api/auth", authRoutes);
// TODO: CRUD: Events
app.use("/api/events", eventRoutes);

// Listen to requests
app.listen(process.env.PORT, () => {
  console.log(`Server running on port ${process.env.PORT}`);
});
```

Duplicar 4 veces `Revalidate JWT` y renombrar como:

- `Event - getEvent` y la petición es `GET: localhost:4000/api/events`.
- `Event - createEvent` y la petición es `POST: localhost:4000/api/events`.
- `Event - updateEvent` y la petición es `PUT: localhost:4000/api/events/123456`.
- `Event - deleteEvent` y la petición es `DELETE: localhost:4000/api/events/123456`.

Verifica que el token aún sea válido. Para obtener uno nuevo revisa la clase [[#23.19 Revalidar JWT]]

Entramos en `Auth - Create Login`, damos en `SEND` y copiamos el token. Entramos en `Auth - Revalidate JWT` y luego en `Event - getEvents`, pegamos en el campo `Value` y le damos en `SEND`.

- Key: `x-token`
- Value: `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1aWQiOiI2OGU1MWIxMGY1YjFmNDJkOGZjM2RmMGEiLCJuYW1lIjoiQWxlIFJvc2VzIiwiaWF0IjoxNzU5OTQ5MzQyLCJleHAiOjE3NTk5NTY1NDJ9.CcWNXqe_epjbUGQbZbgJA_7N-vmk_tACmPMW9-tRl4M`

Debe aparecer:

```bash
{
    "ok": true,
    "msg": "Get events"
}
```

 > 📌 Nota: Esto no requiere un `Body` así que lo puedes quitar. Usa `Ctrl + S` para guardar y `Ctrl + E` para renombrar.

### 24.5 Modelo Evento

Estructura:

```bash
.
├── controllers
│   ├── auth.js
│   └── events.js
├── database
│   └── config.js
├── .env
├── .git
├── .gitignore
├── helpers
│   └── jwt.js
├── index.html
├── index.js
├── LICENSE
├── middlewares
│   ├── validate-fields.js
│   └── validate-jwt.js
├── models 👈👀👇
│   ├── Event.js
│   └── User.js
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes
    ├── auth.js
    └── events.js
```

`models/Event.js`

```js
import { Schema, model } from "mongoose";

const EventSchema = Schema({
  title: {
    type: String,
    required: true,
  },
  notes: {
    type: String,
  },
  start: {
    type: Date,
    required: true,
  },
  end: {
    type: Date,
    required: true,
  },
  user: {
    type: Schema.Types.ObjectId,
    ref: "User",
    required: true,
  },
});

export const Event = model("Event", EventSchema);
```

`controllers/events.js`

```js
import { response } from "express";

export const getEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Get events",
  });
};

export const createEvent = (req, res = response) => {
  // Verify that it have the event
  console.log(req.body);

  res.json({
    ok: true,
    msg: "Create event",
  });
};

export const updateEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Update event",
  });
};

export const deleteEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Delete event",
  });
};
```

En `Event - createEvent` `POST: localhost:4000/api/events` enviamos en `Body`:

```json
{
  "title": "The boss's birthday",
  "start": 1,
  "end": 100000
}
```

Si te da error debes renovar el Token, luego te debe salir:

```json
{
    "ok": true,
    "msg": "Create event"
}
```

En consola:

```json
Restarting 'index.js'
Server running on port 4000
DB Online
{ title: "The boss's birthday", start: 0, end: 100000 }
```

### 24.6 Validar campos necesarios

Estructura:

```bash
.
├── controllers
│   ├── auth.js
│   └── events.js
├── database
│   └── config.js
├── .env
├── .git
├── .gitignore
├── helpers 👈👀👇
│   ├── isDate.js
│   └── jwt.js
├── index.html
├── index.js
├── LICENSE
├── middlewares
│   ├── validate-fields.js
│   └── validate-jwt.js
├── models
│   ├── Event.js
│   └── User.js
├── node_modules
├── package.json
├── package-lock.json
├── public
│   ├── index.html
│   └── styles.css
└── routes
    ├── auth.js
    └── events.js
```

```bash
# Install
npm i moment
```

`routes/events.js`

```js
/* 
  Event Routes
  /api/events
*/

import { Router } from "express";
import { check } from "express-validator";
import { isDate } from "../helpers/isDate.js";
import { validateJWT } from "../middlewares/validate-jwt.js";
import {
  getEvent,
  createEvent,
  updateEvent,
  deleteEvent,
} from "../controllers/events.js";
import { validateFields } from "../middlewares/validate-fields.js";

const router = Router();

// All of them must undergo JWT validation.
router.use(validateJWT); // Everything is protected.

// Get events
router.get("/", getEvent);

// Create a new event
router.post(
  "/",
  [
    check("title", "The title is mandatory!").not().isEmpty(),
    check("start", "The start date is mandatory!").custom(
      isDate
    ),
    check("end", "The completion date is mandatory!").custom(
      isDate
    ),
    validateFields,
  ],
  createEvent
);

// Update event
router.put("/:id", updateEvent);

// Delete event
router.delete("/:id", deleteEvent);

export { router };
```

`helpers/isDate.js`

```js
import moment from "moment";

export const isDate = (value, { req, location, path }) => {
  // console.log({ value, req, location, path });

  if (!value) {
    return false;
  }

  const date = moment(value);

  if (date.isValid()) {
    return true;
  } else {
    return false;
  }
};
```

Al intentar enviar sin `title`...

```bash
{
  "start": 1,
  "end": 100000
}
```

Debe salir:

```bash
{
    "ok": false,
    "errors": {
        "title": {
            "type": "field",
            "msg": "The title is mandatory!",
            "path": "title",
            "location": "body"
        }
    }
}
```

[NPM - Moment ](https://www.npmjs.com/package/moment)

### 24.7 Grabar el evento en la base de datos

`controllers/events.js`

```js
import { response } from "express";
import { Event } from "../models/Event.js";

export const getEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Get events",
  });
};

export const createEvent = async (req, res = response) => {
  // Verify that it have the event
  // console.log(req.body);

  const event = new Event(req.body);

  try {
    event.user = req.uid;
    const savedEvent = await event.save();

    res.json({
      ok: true,
      event: savedEvent,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Talk to the administrator.",
    });
  }
};

export const updateEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Update event",
  });
};

export const deleteEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Delete event",
  });
};
```

`models/Event.js`

```js
import { Schema, model } from "mongoose";

const EventSchema = Schema({
  title: {
    type: String,
    required: true,
  },
  notes: {
    type: String,
  },
  start: {
    type: Date,
    required: true,
  },
  end: {
    type: Date,
    required: true,
  },
  user: {
    type: Schema.Types.ObjectId,
    ref: "User",
    required: true,
  },
});

EventSchema.method("toJSON", function () {
  const { __v, _id, ...object } = this.toObject();
  object.id = _id;

  return object;
});

export const Event = model("Event", EventSchema);
```

`models/User.js` Verifica que realmente estés usando `required`

```js
import { Schema, model } from "mongoose";

const UserSchema = Schema({
  name: {
    type: String,
    required: true,
  },
  email: {
    type: String,
    required: true,
    unique: true,
  },
  password: {
    type: String,
    required: true,
  },
});

export const User = model("User", UserSchema);
```

`Body`: aunque envíes `ABC` en Postman esto será ignorado, ya que no está especificado:

```json
{
  "title": "The boss's birthday",
  "start": 1,
  "end": 100000,
  "notes": "Buy cake.",
  "ABC": 123
}
```

Obtenemos:

```json
{
    "ok": true,
    "event": {
        "title": "The boss's birthday",
        "notes": "Buy cake.",
        "start": "1970-01-01T00:00:00.001Z",
        "end": "1970-01-01T00:01:40.000Z",
        "user": "68e51b10f5b1f42d8fc3df0a",
        "id": "68e80f38517f9aa9e0bf3041"
    }
}
```

Abrimos MongoDB Compass `mern_calendar/events`, debemos ver el objeto almacenado.

### 24.8 Obtener el listado de los Eventos

`controllers/events.js`

```js
import { response } from "express";
import { Event } from "../models/Event.js";

export const getEvent = async (req, res = response) => {
  const events = await Event.find().populate("user", "name");

  res.json({
    ok: true,
    msg: "Get events",
    events,
  });
};

export const createEvent = async (req, res = response) => {
  // Verify that it have the event
  // console.log(req.body);

  const event = new Event(req.body);

  try {
    event.user = req.uid;
    const savedEvent = await event.save();

    res.json({
      ok: true,
      event: savedEvent,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Talk to the administrator.",
    });
  }
};

export const updateEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Update event",
  });
};

export const deleteEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Delete event",
  });
};
```

En `Event - createEvent` `POST: localhost:4000/api/events` enviamos en `Body`:

```json
{
  "title": "Work pending",
  "start": 1000,
  "end": 200000
}
```

En `Event - getEvents` `GET: localhost:4000/api/events` obtenemos lo anteriormente enviado.

### 24.9 Actualizar un Evento

`controllers/events.js`

```js
import { response } from "express";
import { Event } from "../models/Event.js";

export const getEvent = async (req, res = response) => {
  const events = await Event.find().populate("user", "name");

  res.json({
    ok: true,
    msg: "Get events",
    events,
  });
};

export const createEvent = async (req, res = response) => {
  // Verify that it have the event
  // console.log(req.body);

  const event = new Event(req.body);

  try {
    event.user = req.uid;
    const savedEvent = await event.save();

    res.json({
      ok: true,
      event: savedEvent,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Talk to the administrator.",
    });
  }
};

export const updateEvent = async (req, res = response) => {
  const eventId = req.params.id;
  const uid = req.uid;

  try {
    const event = await Event.findById(eventId);

    if (!event) {
      res.status(404).json({
        ok: false,
        msg: "The event doesn't exist for that ID",
      });
    }

    if (event.user.toString() !== uid) {
      return res.status(401).json({
        ok: false,
        msg: "You don't have privileges to edit this event.",
      });
    }

    const newEvent = {
      ...req.body,
      user: uid,
    };

    const updatedEvent = await Event.findByIdAndUpdate(
      eventId,
      newEvent,
      { new: true }
    );

    res.json({
      ok: true,
      event: updatedEvent,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Talk to the administrator.",
    });
  }
};

export const deleteEvent = (req, res = response) => {
  res.json({
    ok: true,
    msg: "Delete event",
  });
};
```

En `Event - updateEvent` `PUT: localhost:4000/api/events/68e51b10f5b1f42d8fc3df0a` debemos añadir un `id` obtenido de `Event - getEvents`.

`Body`:

```json
{
  "title": "Work pending!!!",
  "start": 1000,
  "end": 200000,
  "notes": "Hi world..."
}
```

Obtenemos:

```json
{
    "ok": true,
    "msg": "Update event"
}
```

Ahora en **MongoDB Compass** escogemos el `email` de un usuario diferente. Ingresamos en `Auth - Create Login` y generamos un nuevo token. Para esto inserta los datos en el `Body`.

```json
{
  "email": "alesmith@gmail.com",
  "password": "123456"
}
```

Obtenemos:

```json
{
    "ok": true,
    "uid": "68e6a33c804f66fa3bde0406",
    "name": "Ale Smith",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1aWQiOiI2OGU2YTMzYzgwNGY2NmZhM2JkZTA0MDYiLCJuYW1lIjoiQWxlIFNtaXRoIiwiaWF0IjoxNzYwMTAzOTcxLCJleHAiOjE3NjAxMTExNzF9.zGQqNDqL0_etxf9TbzECnXr9KARJgHkyHQmFMlqWpkg"
}
```

Regresamos a `Event - updateEvent` y pegamos el token en `Headers`.

Obtenemos:

```json
{
    "ok": false,
    "msg": "You don't have privileges to edit this event."
}
```

### 24.10 Eliminar Eventos

`controllers/events.js`

```js
import { response } from "express";
import { Event } from "../models/Event.js";

export const getEvent = async (req, res = response) => {
  const events = await Event.find().populate("user", "name");

  res.json({
    ok: true,
    msg: "Get events",
    events,
  });
};

export const createEvent = async (req, res = response) => {
  // Verify that it have the event
  // console.log(req.body);

  const event = new Event(req.body);

  try {
    event.user = req.uid;
    const savedEvent = await event.save();

    res.json({
      ok: true,
      event: savedEvent,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Talk to the administrator.",
    });
  }
};

export const updateEvent = async (req, res = response) => {
  const eventId = req.params.id;
  const uid = req.uid;

  try {
    const event = await Event.findById(eventId);

    if (!event) {
      return res.status(404).json({
        ok: false,
        msg: "The event doesn't exist for that ID",
      });
    }

    if (event.user.toString() !== uid) {
      return res.status(401).json({
        ok: false,
        msg: "You don't have privileges to edit this event.",
      });
    }

    const newEvent = {
      ...req.body,
      user: uid,
    };

    const updatedEvent = await Event.findByIdAndUpdate(
      eventId,
      newEvent,
      { new: true }
    );

    res.json({
      ok: true,
      event: updatedEvent,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Talk to the administrator.",
    });
  }
};

export const deleteEvent = async (req, res = response) => {
  const eventId = req.params.id;
  const uid = req.uid;

  try {
    const event = await Event.findById(eventId);

    if (!event) {
      return res.status(404).json({
        ok: false,
        msg: "The event doesn't exist for that ID",
      });
    }

    if (event.user.toString() !== uid) {
      return res.status(401).json({
        ok: false,
        msg: "You don't have privileges to delete this event.",
      });
    }

    await Event.findByIdAndDelete(eventId);

    res.json({
      ok: true,
    });
  } catch (error) {
    console.log(error);

    res.status(500).json({
      ok: false,
      msg: "Talk to the administrator.",
    });
  }
};
```

Hacemos login con el usuario propietario de los eventos creados, copiamos y pegamos el token en `Event - deleteEvent`. Nos vamos a `Event - getEvent` y copiamos el `ID` del elemento a eliminar.

En `Event - deleteEvent` debe quedar algo así `DELETE: localhost:4000/api/events/68e90c04ea6cbf6745b9626e`

```json
{
    "ok": true
}
```

Recuerda eliminar los eventos con el usuario que los creó.

> Nota: Si no te aparecen las sugerencias, puedes tratar de ir al modelo y colocar la palabra `new` justo antes de `Schema`, te quedaría algo como lo siguiente.
> `const EventSchema = new Schema({ ... ])` 👈👀
> Esto debería ayudar a que aparezcan las sugerencias.

### 24.11 Código fuente de la sección

Les dejo el código fuente de la sección por si lo llegan a necesitar, y el enlace al repositorio de GitHub para que lo puedan clonar o tener a la mano en un futuro.

[MERN-Calendar-Backend - Autenticación y CRUD](https://github.com/Klerith/MERN-Calendar-Backend/releases/tag/v2.0.0)

**POSTMAN Endpoints - Backups**

Pueden descargar todos los endpoints creados en esta sección del material adjunto a esta clase y cargarlos en Postman.

**Nota:**

> Por favor, no se olviden de dejar un comentario en el curso en las reseñas y si pueden ayúdenme a poder llegar a más personas hablando de este curso o invitándolos a tomarlo, recuerden que es un curso que tienen acceso de por vida y no hay más cobros o suscripciones, por lo que si me ayudan a que más personas lo tomen, me ayudan a que pueda seguir trabajando en la enseñanza en línea.

¡Esa era toda la publicidad que quería hacer… comencemos a desplegar nuestro back-end!

**Recursos de la Lección:**

- MERN-Calendar-Backend-2.0.0.zip [Descargar](https://import.cdn.thinkific.com/643563/courses/1901683/MERNCalendarBackend200-220626-160933.zip)
    
- MERN+Calendar.postman_collection.json [Descargar](https://import.cdn.thinkific.com/643563/courses/1901683/MERNCalendarpostman_collection-220626-160946.json)

## 🟣 25. Despliegue del backend a la nube

### 25.1 Introducción a la sección

### 25.2 Temas puntuales de la sección

En esta clase, nos enfocaremos en desplegar nuestro back-end a Railway, el cual es un servicio en la nube que nos permite desplegar fácilmente aplicaciones de Node.

**Puntualmente veremos:**

1. Configuración de Railway
2. Subida a GitHub
3. Configuración de variables de entorno
4. Prueba del back-end en la nube

### 25.3 Subir proyecto a GitHub

Mi Repo [calendar-app-backend](https://github.com/aleroses/calendar-app-backend)

### 25.4 Pruebas antes de desplegar

```bash
# Make sure everything is okay...
npm run dev

# It must run without errors.
> 10-calendar-backend@1.0.0 dev
> node --watch index.js

Server running on port 4000
DB Online
```

Ver la configuración usada en `database/config.js` [[#23.13 Conectar Node a Mongo Atlas]] nota que hay cosas que no usamos en ese momento porque ya no eran necesarias.

### 25.5 Desplegar a Railway

#### Railway 👎

Crea una cuenta en [Railway](https://railway.com/) preferiblemente usar una cuenta de **GitHub**.

`New project/GitHub Repository/calendar-app-backend`

Nos vamos a `Variables`

Abre el archivo `.env` y copia casi todo, luego solo pegalo en `Row editor/Paste` 

```json
DB_CNN=mongodb+srv://mern-user:HAzCB7Tw4gQ3ln1m@calendardb.l8x2lf4.mongodb.net/mern_calendar
SECRET_JWT_SEED=This-is-@-secret-Word
```

`Deploy`

`Settings/Generate Domain/4000`

Esto te debe dar un enlace: `calendar-app-backend-production-2d97.up.railway.app`

> Nota: Si no aparecen tus proyectos o repositorios, intenta activando `Profile Visibity` y dándole acceso a todo:
> `Account Settings/Public Profile/Profile Visibility (activar) permitir todos los proyectos.`

Luego de que todo haya funcionado puedes ir a Postman `Auth - Login` y en `POST: pegar enlace`

#### Render 👍

Crea una cuenta en [Render](https://render.com/) preferiblemente usar una cuenta de **GitHub**.

`Projects/Add new/Web Service/GitHub/All repositories/calendar-app-backend`

Añade `Environment Variables` y `Deploy Web Service`

Deberías obtener un enlace como este [Calendar Backend](https://calendar-app-backend-smi8.onrender.com/)

### 25.6 Código fuente de la sección

Aquí les dejo el código fuente con los pocos cambios que hicimos en la sección de despliegues.

[Fin-seccion-25 - Despliegue a Railway](https://github.com/DevTalles-corp/React-MERN-backend/tree/fin-seccion-25)

**Importante:**

Recuerden cambiar sus variables de entorno.

## 🟣 26. MERN - Calendario + Backend

### 26.1 Introducción a la sección

### 26.2 Temas puntuales de la sección

**¿Qué veremos en esta sección?**

- Conexión de nuestro Backend con el Frontend
    

Esta sección trabajaremos integrando nuestro back-end con el front-end hecho en React, que ya tenemos casi terminado, solo debemos de llamar los servicios y disparar las acciones respectivas que ya tenemos en nuestra aplicación del calendario.

¡Toda esta sección está enfocada en la parte de la autenticación y manejo del JWT, hay que guardar y estar actualizando el token de autenticación y realizar las pruebas respectivas!

Estamos llegando al final del curso :'(... pero aún falta mucho :D

### 26.3 Continuación de proyecto - Calendar + Backend

```bash
cd FH/10-calendar-backend
code .
npm run dev
```

```bash
cd FH/10-calendar
code .
npm run dev
```

### 26.4 Creando variables de entorno

Estructura:

```bash
.
├── .env 👈👀👇
├── .env.template
├── eslint.config.js
├── .git
├── .gitignore
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md 👈👀
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx
│   │   │   ├── CalendarModal.jsx
│   │   │   ├── FabAddNew.jsx
│   │   │   ├── FabDelete.jsx
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   ├── getEnvVariables.js 👈👀
│   │   └── getMessages.js
│   ├── hooks
│   │   ├── useCalendarStore.js
│   │   └── useUiStore.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── calendar
│   │   │   └── calendarSlice.js
│   │   ├── store.js
│   │   └── ui
│   │       └── uiSlice.js
│   └── styles.css
└── vite.config.js
```

`src/helpers/getEnvVariables.js`

```js
export const getEnvVariables = () => {
  import.meta.env;

  return {
    ...import.meta.env,
  };
};
```

`.env`

```
VITE_API_URL=http://localhost:4000/api
```

`.env.template`

```
VITE_API_URL=http://localhost:4000/api
```

`src/router/AppRouter.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { LoginPage } from "../auth/pages/LoginPage";
import { CalendarPage } from "../calendar/pages/CalendarPage";
import { getEnvVariables } from "../helpers/getEnvVariables";

export const AppRouter = () => {
  const authStatus = "authenticated";

  console.log(getEnvVariables()); 👈👀
  return (
    <Routes>
      {authStatus === "not-authenticated" ? (
        <Route path="/auth/*" element={<LoginPage />} />
      ) : (
        <Route path="/*" element={<CalendarPage />} />
      )}

      <Route
        path="/*"
        element={<Navigate to="/auth/login" />}
      />
    </Routes>
  );
};
```

En consola se muestra:

```js
Object = {
  BASE_URL: "/",
  DEV: true,
  MODE: "development",
  PROD: false,
  SSR: false,
  VITE_API_URL: "http://localhost:4000/api",
};
```

`README.md`

```md
# Calendar App

## Development steps

1. Rename the .env.template file to .env
2. Make the respective changes to the environment variables.

VITE_API_URL=http://localhost:4000/api
```

Los archivos `.env` no se subirán al repositorio, pero aquí se podrá ver su contenido.

### 26.5 AuthSlice

Estructura:

```bash
.
├── .env
├── .env.template
├── eslint.config.js
├── .git
├── .gitignore
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx
│   │   │   ├── CalendarModal.jsx
│   │   │   ├── FabAddNew.jsx
│   │   │   ├── FabDelete.jsx
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   ├── getEnvVariables.js
│   │   └── getMessages.js
│   ├── hooks
│   │   ├── useCalendarStore.js
│   │   └── useUiStore.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth 👈👀👇
│   │   │   └── authSlice.js
│   │   ├── calendar
│   │   │   └── calendarSlice.js
│   │   ├── store.js
│   │   └── ui
│   │       └── uiSlice.js
│   └── styles.css
└── vite.config.js
```

`src/store/auth/authSlice.js`

```js
import { createSlice } from "@reduxjs/toolkit";

export const authSlice = createSlice({
  name: "auth",
  initialState: {
    status: "checking", // authenticated not-authenticated
    user: {},
    errorMessage: undefined,
  },
  reducers: {
    onChecking: (state) => {
      state.status = "checking";
      state.user = {};
      state.errorMessage = undefined;
    },
    onLogin: (state, { payload }) => {
      state.status = "authenticated";
      state.user = payload;
      state.errorMessage = undefined;
    },
  },
});

export const { onChecking, onLogin } = authSlice.actions;
```

`src/store/store.js`

```js
import { configureStore } from "@reduxjs/toolkit";
import { uiSlice } from "./ui/uiSlice";
import { calendarSlice } from "./calendar/calendarSlice";
import { authSlice } from "./auth/authSlice";

export const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
    calendar: calendarSlice.reducer,
    ui: uiSlice.reducer,
  },
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware({
      serializableCheck: false,
    }),
});
```

> Nota: Recuerda usar el atajo `redux slice` para crear `slices` rápido.

### 26.6 useForm - Login y Registro

Estructura:

```bash
.
├── .env
├── .env.template
├── eslint.config.js
├── .git
├── .gitignore
├── index.html
├── LICENSE
├── node_modules
├── package.json
├── package-lock.json
├── public
├── README.md
├── src
│   ├── auth
│   │   └── pages
│   │       ├── LoginPage.css
│   │       └── LoginPage.jsx
│   ├── calendar
│   │   ├── components
│   │   │   ├── CalendarEvent.jsx
│   │   │   ├── CalendarModal.jsx
│   │   │   ├── FabAddNew.jsx
│   │   │   ├── FabDelete.jsx
│   │   │   └── Navbar.jsx
│   │   └── pages
│   │       └── CalendarPage.jsx
│   ├── CalendarApp.jsx
│   ├── helpers
│   │   ├── calendarLocalizer.js
│   │   ├── getEnvVariables.js
│   │   └── getMessages.js
│   ├── hooks
│   │   ├── useCalendarStore.js
│   │   ├── useForm.js 👈👀
│   │   └── useUiStore.js
│   ├── main.jsx
│   ├── router
│   │   └── AppRouter.jsx
│   ├── store
│   │   ├── auth
│   │   │   └── authSlice.js
│   │   ├── calendar
│   │   │   └── calendarSlice.js
│   │   ├── store.js
│   │   └── ui
│   │       └── uiSlice.js
│   └── styles.css
└── vite.config.js
```

`src/hooks/useForm.js`

```js
import { useEffect, useMemo, useState } from "react";

export const useForm = (
  initialForm = {},
  formValidations = {}
) => {
  const [formState, setFormState] = useState(initialForm);
  const [formValidation, setFormValidation] = useState({});

  // const { value, name, password } = formState;

  useEffect(() => {
    createValidators();
  }, [formState]);

  useEffect(() => {
    setFormState(initialForm);
  }, [initialForm]);

  const isFormValid = useMemo(() => {
    for (const formValue of Object.keys(formValidation)) {
      if (formValidation[formValue] !== null) return false;
    }

    return true;
  }, [formValidation]);

  const handleInputChange = ({ target }) => {
    const { value, name } = target;

    setFormState({
      ...formState,
      [name]: value,
    });
  };

  const handleResetForm = () => {
    setFormState(initialForm);
  };

  const createValidators = () => {
    const formCheckedValues = {};

    for (const formField of Object.keys(formValidations)) {
      // xd = fn
      const [
        fn,
        errorMessage, //= "This field is required",
      ] = formValidations[formField];

      formCheckedValues[`${formField}Valid`] = fn(
        formState[formField]
      )
        ? null
        : errorMessage;
    }

    setFormValidation(formCheckedValues);
  };

  return {
    ...formState,
    formState,
    handleInputChange,
    handleResetForm,
    ...formValidation,
    isFormValid,
  };
};
```

`src/router/AppRouter.jsx`

```jsx
import { Navigate, Route, Routes } from "react-router";
import { LoginPage } from "../auth/pages/LoginPage";
import { CalendarPage } from "../calendar/pages/CalendarPage";
import { getEnvVariables } from "../helpers/getEnvVariables";

export const AppRouter = () => {
  const authStatus = "not-authenticated"; 👈👀

  console.log(getEnvVariables());
  return (
    <Routes>
      {authStatus === "not-authenticated" ? (
        <Route path="/auth/*" element={<LoginPage />} />
      ) : (
        <Route path="/*" element={<CalendarPage />} />
      )}

      <Route
        path="/*"
        element={<Navigate to="/auth/login" />}
      />
    </Routes>
  );
};
```

`src/auth/pages/LoginPage.jsx`

```jsx
import { useForm } from "../../hooks/useForm";
import "./LoginPage.css";

const loginFormFields = {
  loginEmail: "",
  loginPassword: "",
};

const registerFormFields = {
  registerName: "",
  registerEmail: "",
  registerPassword: "",
  registerPassword2: "",
};

export const LoginPage = () => {
  const {
    loginEmail,
    loginPassword,
    handleInputChange: onLoginInputChange,
  } = useForm(loginFormFields);

  const {
    registerEmail,
    registerName,
    registerPassword,
    registerPassword2,
    handleInputChange: onRegisterInputChange,
  } = useForm(registerFormFields);

  const loginSubmit = (event) => {
    event.preventDefault();

    console.log({ loginEmail, loginPassword });
  };

  const registerSubmit = (event) => {
    event.preventDefault();

    console.log({
      registerName,
      registerEmail,
      registerPassword,
      registerPassword2,
    });
  };

  return (
    <div className="container login-container">
      <div className="row">
        <div className="col-md-6 login-form-1">
          <h3>Ingreso</h3>
          <form onSubmit={loginSubmit}>
            <div className="form-group mb-2">
              <input
                type="text"
                className="form-control"
                placeholder="Correo"
                name="loginEmail"
                value={loginEmail}
                onChange={onLoginInputChange}
              />
            </div>
            <div className="form-group mb-2">
              <input
                type="password"
                className="form-control"
                placeholder="Contraseña"
                name="loginPassword"
                value={loginPassword}
                onChange={onLoginInputChange}
              />
            </div>
            <div className="form-group mb-2">
              <input
                type="submit"
                className="btnSubmit"
                value="Login"
              />
            </div>
          </form>
        </div>

        <div className="col-md-6 login-form-2">
          <h3>Registro</h3>
          <form onSubmit={registerSubmit}>
            <div className="form-group mb-2">
              <input
                type="text"
                className="form-control"
                placeholder="Nombre"
                name="registerName"
                value={registerName}
                onChange={onRegisterInputChange}
              />
            </div>
            <div className="form-group mb-2">
              <input
                type="email"
                className="form-control"
                placeholder="Correo"
                name="registerEmail"
                value={registerEmail}
                onChange={onRegisterInputChange}
              />
            </div>
            <div className="form-group mb-2">
              <input
                type="password"
                className="form-control"
                placeholder="Contraseña"
                name="registerPassword"
                value={registerPassword}
                onChange={onRegisterInputChange}
              />
            </div>

            <div className="form-group mb-2">
              <input
                type="password"
                className="form-control"
                placeholder="Repita la contraseña"
                name="registerPassword2"
                value={registerPassword2}
                onChange={onRegisterInputChange}
              />
            </div>

            <div className="form-group mb-2">
              <input
                type="submit"
                className="btnSubmit"
                value="Crear cuenta"
              />
            </div>
          </form>
        </div>
      </div>
    </div>
  );
};
```

[useForm - Gist](https://gist.github.com/Klerith/09dede50a8a397231744d4545b771408)

### 26.7

`src/`

```jsx
```

`src/`

```jsx
```


`src/`

```jsx
```

☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌

### 26.8

`src/`

```jsx
```

`src/`

```jsx
```


`src/`

```jsx
```

☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌

### 26.9

`src/`

```jsx
```

`src/`

```jsx
```


`src/`

```jsx
```

☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌

### 26.10

`src/`

```jsx
```

`src/`

```jsx
```


`src/`

```jsx
```

☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌

### 26.11

`src/`

```jsx
```

`src/`

```jsx
```


`src/`

```jsx
```

☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌

### 26.12

`src/`

```jsx
```

`src/`

```jsx
```


`src/`

```jsx
```

☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌

### 26.13

`src/`

```jsx
```

`src/`

```jsx
```


`src/`

```jsx
```

☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌

### 26.14

`src/`

```jsx
```

`src/`

```jsx
```


`src/`

```jsx
```

☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌

### 26.15

`src/`

```jsx
```

`src/`

```jsx
```


`src/`

```jsx
```

☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌










⚙️
☝️👆
👈👀
❯
👈👀👇
👈👀☝️
👈👀📌



🔥
🚫
🔘
🟣
🟡

```bash
npm install react@latest react-dom@latest
# o
yarn add react@latest react-dom@latest
```

```bash
npm install react@latest react-dom@latest
# o
yarn add react@latest react-dom@latest
```

resaltado de rutas...