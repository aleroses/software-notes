# TailwindCSS: Para desarrolladores de software

## 1. Introducción

### 1.1 Introducción

### 1.2 ¿Cómo funcionará el curso?

### 1.3 ¿Cómo hacer preguntas?

### 1.4 Instalaciones Necesarias

- [VSCode](https://code.visualstudio.com/)
- [NodeJS](https://nodejs.org/en/download)

#### Opcionales

- [Warp](https://app.warp.dev/referral/2KPGQV) <- Alternativa a la Powershell o Terminal

#### Extensiones de VSCode

- [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Colorize](https://marketplace.visualstudio.com/items?itemName=kamikillerto.vscode-colorize)

#### Tema de VSCode

- [Flow Icons](https://marketplace.visualstudio.com/items?itemName=thang-nm.flow-icons)
- [Tokyo Night](https://marketplace.visualstudio.com/items?itemName=enkia.tokyo-night)
- [Wallpapers Developer](https://drive.google.com/drive/folders/1ItU8rbSGJjnh2USOBGwaCo9nYKifPJ6m?usp=sharing)


#### Comunidad de Discord

<a href="https://discord.com/invite/fNp7KRDkke" target="blank">
<img src="https://files.cdn.thinkific.com/cdn-cgi/image/width=1920,dpr=3,onerror=redirect/file_uploads/643563/images/c4f/52b/ecc/HOME-BANNER-COMUNIDAD-discord.jpg">
</a>

[Gist - Instalaciones del curso](https://gist.github.com/Klerith/8988f539fb391bf783817d4bfabb290a)

## 2. TailwindCSS - Primeros pasos

### 2.1 Introducción

### 2.2 Temas puntuales

En esta sección comenzaremos nuestro camino en TailwindCSS comprendiendo desde las bases, cómo funciona hasta conceptos de Grid y Flex, los cuales son necesarios hoy en día para cualquier diseño.

Puntualmente veremos:

- **¿Qué es TailwindCSS?**  
    Explicación del enfoque Utility-First y por qué Tailwind acelera el desarrollo.  
    
- **¿Cómo funciona Tailwind?**  
    Comprender el JIT, el proceso de generación de clases y el flujo de trabajo.  
    
- **Tema, base, componentes y utilidades**  
    Cómo Tailwind organiza sus capas internas y cómo extender el diseño del proyecto.  
    
- **Creando un componente**  
    Construcción de un componente real usando únicamente utilidades de Tailwind.  
    
- **Flexbox Row**  
    Uso de flex y flex-row para crear estructuras horizontales.  
    
- **Flexbox Column**  
    Uso de flex-col para crear layouts verticales y secciones apiladas.  
    
- **Grid**  
    Creación de diseños avanzados con CSS Grid usando utilidades de Tailwind.  
    
- **TailwindCSS – Documentación**  
    Cómo navegar la documentación y encontrar utilidades y variantes rápidamente.

### 2.3 ¿Qué es TailwindCSS?

Tailwind CSS es un framework CSS "utility-first" que permite construir interfaces web modernas directamente en el HTML usando clases predefinidas (utilidades) para estilos específicos (color de fondo, padding, flexbox, etc.), eliminando la necesidad de escribir CSS personalizado y agilizando el desarrollo al no tener que pensar en nombres de clases, lo que resulta en un código más limpio y flexible, ideal para diseños responsivos y personalizables.  

¿Cómo funciona?

En lugar de clases genéricas como `.btn` o `.card`, aplicas clases de utilidad como `bg-blue-500`, `text-center`, `p-4`, `flex` o `md:text-lg` (para responsive) directamente en tus elementos HTML. 

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">  Botón de Ejemplo</button>
```

### 2.4 ¿Cómo funciona Tailwind?

En el Playground de Tailwind podemos hacer pruebas y ver como funciona.

```html
<div class="h-screen w-full bg-gray-900 text-white">
  <h1 class="text-2xl">Hi World!!!</h1>
</div>
```

En la parte inferior de la web vemos `Generated CSS` que muestra:

- All
- Theme: Variables
- Base: Normalize CSS para estandarizar.
- Components
- Utilities: Utility classes aplicadas como clases.  
	```css
	.h-screen {
    height: 100vh;
  }
	
  .w-full {
    width: 100%;
  }
	```

- [Página oficial de TailwindCSS](https://tailwindcss.com/)
- [Playground Tailwind](https://play.tailwindcss.com/)

### 2.5 Tema, base, componentes y utilidades

Nunca hagas modificaciones dentro del `Generated CSS`.

```html
<div class="h-screen w-full bg-gray-900 text-white">
  <h1 class="text-2xl">Hi World!!!</h1>
  <h2 class="text-2xl">Hi World!!!</h2>
  <h3 class="text-2xl">Hi World!!!</h3>
</div>
```

Para cambiar los valores por defecto dentro del **Tailwind Play**, entramos la pestaña `CSS`:

```html
<div class="h-screen w-full bg-gray-900 text-white">
  <h1>Hi World!!!</h1>
  <h2>Hi World!!!</h2>
  <h3>Hi World!!!</h3>
</div>
```

```css
@layer base {
  h1 {
    @apply text-5xl text-blue-500;
  }
}
```

Esto añade dentro de **Base** nuestras configuraciones personalizadas.

### 2.6 Creando un componente

Dentro de `Generated CSS` revisar **Components**.

```html
<div class="flex h-screen w-full items-center justify-center bg-gray-900 text-white">
  <button class="btn-primary 👈🏼👀">Click me</button>
</div>
```

En la pestaña `CSS` creamos el componente `.btn-primary`:

```css
@layer components {
  .btn-primary { 👈🏼👀👇🏼
    @apply rounded bg-gray-800 p-2 px-4 text-cyan-400 hover:bg-slate-900;
    font-weight: 600;
    border: 2px solid pink;
    &:hover {
      ...esto también es css
    }
  }
}
```

Nota: También nos permite usar CSS clásico.

### 2.7 Flexbox Row (default)

- Puedes añadir valores computados o arbitrarios `class="h-[100px]"`
- Puedes añadir opacidad `bg-green-400/15`

```html
<div class="flex h-screen w-full items-center justify-around bg-gray-900 text-white">
  <div class="h-[100px] w-[100px] rounded-full bg-red-400"></div>
  <div class="h-[100px] w-[100px] self-start rounded-full bg-yellow-200"></div>
  <div class="h-[100px] w-[100px] rounded-full bg-green-400/15"></div>
</div>
```

### 2.8 Flexbox Column

```html
<div class="flex h-screen w-full flex-col-reverse 👈🏼👀 items-center justify-around bg-gray-900 text-white">
  <div class="h-[100px] w-[100px] rounded-full bg-red-400"></div>
  <div class="h-[100px] w-[100px] self-start rounded-full bg-yellow-200"></div>
  <div class="h-[100px] w-[100px] rounded-full bg-green-400/15"></div>
</div>
```

Media query

```html
<div class="flex h-screen w-full flex-col items-center justify-around bg-gray-900 text-white md:flex-row 👈🏼👀">
  <div class="h-[12rem] w-[12rem] rounded-full bg-red-400"></div>
  <div class="h-[12rem] w-[12rem] self-start rounded-full bg-yellow-200"></div>
  <div class="h-[12rem] w-[12rem] rounded-full bg-green-400/15"></div>
</div>
```

En pantallas medianas cambia de `flex-col` a `flex-row`.

### 2.9 Grid

```css
<div class="grid h-screen w-screen grid-cols-2 gap-4 bg-gray-900 px-2 sm:grid-cols-3 md:grid-cols-4">
  <div class="h-[6rem] rounded-2xl bg-red-500"></div>
  <div class="h-[6rem] rounded-2xl bg-yellow-400"></div>
  <div class="h-[6rem] rounded-2xl bg-green-400"></div>
  <div class="h-[6rem] rounded-2xl bg-blue-950"></div>
  <div class="h-[6rem] rounded-2xl bg-orange-400"></div>
</div>
```

### 2.10 TailwindCSS - Documentación

Tratemos de revisar la documentación y si puedes o quieres inscríbete en el curso que brinda el equipo de Tailwind.

Lo encuentras en `Docs/Course`

[Página oficial de TailwindCSS](https://tailwindcss.com/)

## 3. TailwindCSS localmente + Recomendaciones oficiales

### 3.1 Introducción

### 3.2 Temas puntuales de la sección

En esta sección configuraremos nuestro proyecto para ejecutar TailwindCSS localmente sin frameworks.

**Puntualmente vermos:**

1. **Configuración manual**  
    
    Cómo instalar TailwindCSS desde cero y activar sus capas base, components y utilities sin depender de frameworks.
    
2. **Extensiones valiosas como TailwindCSS IntelliSense y plugin de Prettier**  
    
    Herramientas que mejoran el autocompletado, el orden de clases y la productividad en el editor.
    
3. **Configuraciones de Prettier y VSCode**  
    
    Ajustes recomendados para formatear el código automáticamente y mantener un proyecto consistente.
    
4. **Live Server**  
    
    Uso de un servidor local para visualizar cambios en tiempo real mientras desarrollamos.
    
5. **Modo observador — Watch Mode**  
    
    Cómo Tailwind recompila los estilos automáticamente al modificar el HTML o el CSS.
    
6. **Preparar todo el material para las siguientes secciones**  
    
    Dejar el entorno listo para continuar con componentes, layout y ejercicios más avanzados.

### 3.3 Inicio de proyecto - TailwindCSS localmente

```bash
mkdir tailwindCSS
cd tailwindCSS
mkdir 01-css-local
cd 01-css-local
code .
```

Instalar Tailwind con CLI:

```bash
npm init -y # Create the package.json file
npm install tailwindcss @tailwindcss/cli
```

Estructura:

```bash
.
├── dist
│   └── output.css
├── node_modules
├── package.json
├── package-lock.json
└── src
    ├── index.html
    └── styles.css
```

La instalación y los pasos para crear el archivo `src/input.css` o `src/styles.css` se encuentran en la sección **Tailwind CLI**.

`src/index.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />
    <title>Document</title>

    <link rel="stylesheet" href="../dist/output.css" />
  </head>
  <body class="bg-gray-950">
    <h1 class="text-red-500 underline">Hi World</h1>
  </body>
</html>
```

`src/styles.css`

```css
@import 'tailwindcss';
```

`package.json`

```json
{
  "name": "01-css-local",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "npx @tailwindcss/cli -i ./src/styles.css -o ./dist/output.css --watch",
    "build": "npx @tailwindcss/cli -i ./src/styles.css -o ./dist/output.css --minify"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "type": "commonjs",
  "dependencies": {
    "@tailwindcss/cli": "^4.1.18",
    "tailwindcss": "^4.1.18"
  }
}
```

```bash
npm run dev
npm run build # Minified CSS
```

No olvides que para ver los cambios en la web debes ejecutar `npm run dev`

Dentro del `index.html` dar clic derecho `Open with Live Server`

### 3.4 Prettier - Configuraciones necesarias

Instala la extensión Prettier desde VSC.

Instala el plugin que va a ordenar las clases dentro de VSC.

```bash
npm install -D prettier prettier-plugin-tailwindcss
```

Estructura:

```bash
.
├── dist
│   └── output.css
├── package.json
├── package-lock.json
├── .prettierrc 👈🏼👀
└── src
    ├── index.html
    └── styles.css
```

`.prettierrc`

```
{
  "plugins": ["prettier-plugin-tailwindcss"]
}
```

Revisa los **Settings** usando `Ctrl + ,` debes tener:

- [x] Editor: Format on save
- [x] Editor: Format On Save Mode
	- "File"

Si al usar `Ctrl + S` no se formatea, recarga la ventana usando `F1` y elige:

- Developer: Reload Window

También prueba con:

- Developer: Restart Extension Host

Enlaces:

- [Docs - Configuraciones de editor](https://tailwindcss.com/docs/editor-setup)
- [Class sorting with prettier](https://tailwindcss.com/docs/editor-setup#class-sorting-with-prettier)

### 3.5 .gitIgnore - Configuraciones de Git

Estructura:

```bash
.
├── dist
│   └── output.css
├── .gitignore 👈🏼👀
├── node_modules
├── package.json
├── package-lock.json
├── .prettierrc
└── src
    ├── index.html
    └── styles.css
```

Crea un archivo `.gitignore` en la raíz del proyecto.

`.gitignore`

```html
dist/
node_modules/
```

Usa Git, es muy importante

```bash
git init
```

- En Obsidian: [[git-github]]
- En GitHub: [git and github](https://github.com/aleroses/software-notes/blob/master/DW/1-basico/005-git-github/git-github.md#1-qu%C3%A9-es-git)

### 3.6 Live Server - Probar y desarrollar

Estructura

```bash
.
├── dist
│   └── output.css
├── .gitignore
├── node_modules
├── package.json
├── package-lock.json
├── .prettierrc
├── README.md 👈🏼👀
└── src
    ├── index.html
    └── styles.css
```

```bash
npm run dev
```

Abre el archivo `index.html`, da clic derecho y selecciona `Open with Live Server` para ver los resultados en el navegador.

Para más opciones de Live Server, usa `F1` y escribe **Live Server**:

- Change Live Server workspace
- Open with Live Server
- Stop Live Server

`README.md`

```md
# Ejercicios de Tailwind CSS

## Correr proyecto

1. Instalar dependencias `npm install`
2. Correr proyecto `npm run dev` (ver package.json para los scripts)
3. Ejecutar live server (extensión de VS Code)
4. Abrir el archivo index.html en el navegador (o cualquier otro archivo html deseado)
```

[Gist - Notas para el proyecto](https://gist.github.com/Klerith/1925248dc9b196fba92fe4d5c9aaea5a)

### 3.7 Ejercicios con pseudo clases

Estructura:

```bash
.
├── dist
│   └── output.css
├── .gitignore
├── package.json
├── package-lock.json
├── .prettierrc
├── README.md
└── src
    ├── 01-pseudo-classes
    │   ├── 01-listas.html
    │   ├── 02-tablas.html
    │   ├── 03-formularios.html
    │   ├── 04-has.html
    │   ├── 05-grupos.html
    │   ├── 06-hermanos.html
    │   ├── 07-grupos-anidados.html
    │   ├── 08-grupos-implicitos.html
    │   └── 09-diferenciando-peers.html
    ├── index.html
    └── styles.css
```

`src/index.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>

    <link rel="stylesheet" href="../dist/output.css" />
  </head>
  <body>
    <h1 class="text-2xl">Hi World</h1>

    <a
      class="underline hover:text-red-600"
      href="./01-pseudo-classes/01-listas.html"
      >Listas HTML</a
    >
  </body>
</html>
```

`src/01-pseudo-classes/01-listas.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>
  <body>
    <h1>Listas</h1>
    <hr />
    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
      <li>Item 4</li>
    </ul>
    <footer>
      <p>Soy el footer</p>
      <a href="02-tablas.html">Siguiente Tablas</a>
    </footer>
  </body>
</html>
```

`src/styles.css`

```css
@import "tailwindcss";

@layer base {
  body {
    @apply bg-gray-950 px-4 py-2 text-red-500;
  }
}
```

Este es un CSS global.

[01-pseudo-classes.zip](https://import.cdn.thinkific.com/643563/azL0ov9vSry448FniCHO_01-pseudo-classes.zip)

### 3.8 Código fuente

Aquí tienen el código fuente de la sección por si quieren saltarse toda la preparación inicial y llegar directamente a los ejercicios.

[GitHub - Tailwindcss Localmente](https://github.com/DevTalles-corp/tailwindcss-css-localmente)

## 4. Pseudo-classes

### 4.1 Introducción

### 4.2 Temas puntuales

En esta sección estaremos trabajando en el proyecto local que hicimos en la sección anterior pero con el objetivo de aprender pseudo-clases que permiten realizar mucho trabajo que normalmente hacemos con JavaScript.

**Temas puntuales de la sección “Pseudo-clases”**

- **Ejercicio: Listas**
    
    Estilizar listas usando pseudo-clases para separaciones y control.
    
- **Ejercicio: Tablas**
    
    Aplicar estilos condicionales a filas y celdas mediante pseudo-clases.
    
- **Tablas responsivas**
    
    Añadir variantes responsivas + pseudo-clases para mejorar usabilidad.
    
- **Ejercicio: Formularios**
    
    Hover, focus, disabled y otros estados comunes en inputs.
    
- **Elementos hermanos – Peer**
    
    Introducción a peer para reaccionar a estados de un elemento hermano.
    
- **Ejemplo: has()**
    
    Uso de has-* para aplicar estilos basados en contenido o estados hijos.
    
- **Ejemplo: Grupos**
    
    Variantes group para manejar estados colectivos de varios elementos.
    
- **Ejemplo: Hermanos**
    
    Estilos aplicados a elementos hermanos con variantes avanzadas.
    
- **Ejemplo: Grupos anidados**
    
    Comportamiento de group dentro de otro group.
    
- **Ejemplo: Diferenciando peers**
    
    Cómo usar varios peer para controlar interacciones más complejas.

### 4.3 Continuación de proyecto

Empezaremos a trabajar con listas, pero mientras revisa la documentación.

- [GitHub - Repositorio inicial](https://github.com/DevTalles-corp/tailwindcss-css-localmente)
- [Docs hover-focus-and-other-states](https://tailwindcss.com/docs/hover-focus-and-other-states)

### 4.4 Ejercicio - Listas

```bash
cd 01-css-local
npm run dev
```

`src/01-pseudo-classes/01-listas.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>
  <body>
    <h1>Listas</h1>
    <hr />
    <ul class="list-inside list-disc">
      <!-- Se aplica solo al primer elemento -->
      <li class="first:mt-4">Item 1</li>
      <li class="first:mt-4">Item 2</li>
      <li class="first:mt-4">Item 3</li>
      <li class="first:mt-4 last:mb-4">Item 4</li>
    </ul>
    <footer>
      <p>Soy el footer</p>
      <a
        href="02-tablas.html"
        class="text-bold cursor-pointer text-red-400 hover:underline"
        >Siguiente Tablas</a
      >
    </footer>
  </body>
</html>
```

`01-css-local/src/styles.css`

```css
@import "tailwindcss";

@layer base {
  body {
    @apply bg-gray-950 p-8 px-4 py-2 text-red-500;
  }

  h1 {
    @apply mb-2 text-3xl font-bold;
  }
}
```

### 4.5 Ejercicio - Tablas

`src/01-pseudo-classes/02-tablas.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body>
    <h1>Tablas</h1>
    <hr />

    <table>
      <thead class="bg-gray-900/35">
        <tr
          class="odd:bg-white even:bg-gray-50 dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
        >
          <th class="p-3">Foto</th>
          <th class="p-3">Nombre</th>
          <th class="p-3">Edad</th>
          <th class="p-3 text-right">Email</th>
        </tr>
      </thead>
      <tbody>
        <!--  -->
        <tr
          class="odd:bg-white even:bg-gray-50 dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
        >
          <td>
            <img
              src="https://randomuser.me/api/portraits/men/1.jpg"
              alt="Foto de Juan Pérez"
            />
          </td>
          <td>Juan Pérez</td>
          <td>28</td>
          <td>juan.perez@email.com</td>
        </tr>
        <tr
          class="odd:bg-white even:bg-gray-50 dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
        >
          <td>
            <img
              src="https://randomuser.me/api/portraits/women/2.jpg"
              alt="Foto de Maria Gomez"
            />
          </td>
          <td>Maria Gomez</td>
          <td>34</td>
          <td>maria.gomez@email.com</td>
        </tr>
        <tr
          class="odd:bg-white even:bg-gray-50 dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
        >
          <td>
            <img
              src="https://randomuser.me/api/portraits/men/3.jpg"
              alt="Foto de Luis Fernández"
            />
          </td>
          <td>Luis Fernández</td>
          <td>25</td>
          <td>luis.fernandez@email.com</td>
        </tr>
        <tr
          class="odd:bg-white even:bg-gray-50 dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
        >
          <td>
            <img
              src="https://randomuser.me/api/portraits/women/4.jpg"
              alt="Foto de Ana Ruiz"
            />
          </td>
          <td>Ana Ruiz</td>
          <td>30</td>
          <td>ana.ruiz@email.com</td>
        </tr>
        <tr
          class="odd:bg-white even:bg-gray-50 dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
        >
          <td>
            <img
              src="https://randomuser.me/api/portraits/men/5.jpg"
              alt="Foto de Carlos Torres"
            />
          </td>
          <td>Carlos Torres</td>
          <td>41</td>
          <td>carlos.torres@email.com</td>
        </tr>
        <tr
          class="odd:bg-white even:bg-gray-50 dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
        >
          <td>
            <img
              src="https://randomuser.me/api/portraits/women/6.jpg"
              alt="Foto de Laura Sánchez"
            />
          </td>
          <td>Laura Sánchez</td>
          <td>22</td>
          <td>laura.sanchez@email.com</td>
        </tr>
      </tbody>
    </table>

    <a href="03-formularios.html">Siguiente Formularios</a>
  </body>
</html>
```

[Hover focus and other states#first-last-odd-and-even](https://tailwindcss.com/docs/hover-focus-and-other-states#first-last-odd-and-even)

### 4.6 Tablas responsivas

```bash
npm run dev
```

`src/01-pseudo-classes/02-tablas.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body>
    <h1>Tablas</h1>
    <hr />

    <div class="overflow-x-auto">
      <table class="w-full min-w-max">
        <thead class="hidden bg-gray-900/35 md:table-header-group">
          <tr
            class="odd:bg-white even:bg-gray-50 dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
          >
            <th class="p-3">Foto</th>
            <th class="p-3">Nombre</th>
            <th class="p-3">Edad</th>
            <th class="p-3 text-right">Email</th>
          </tr>
        </thead>
        <tbody>
          <!--  -->
          <tr
            class="mb-5 flex flex-col items-center justify-center p-2 odd:bg-white even:bg-gray-50 md:table-row dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
          >
            <td>
              <img
                src="https://randomuser.me/api/portraits/men/1.jpg"
                alt="Foto de Juan Pérez"
                class="h-12 w-12 rounded-full"
              />
            </td>
            <td class="capitalize">Juan Pérez</td>
            <td>28</td>
            <td>juan.perez@email.com</td>
          </tr>
          <tr
            class="mb-5 flex flex-col items-center justify-center p-2 odd:bg-white even:bg-gray-50 md:table-row dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
          >
            <td>
              <img
                src="https://randomuser.me/api/portraits/women/2.jpg"
                alt="Foto de Maria Gomez"
                class="h-12 w-12 rounded-full"
              />
            </td>
            <td>Maria Gomez</td>
            <td>34</td>
            <td class="lowercase">maria.gomez@email.com</td>
          </tr>
          <tr
            class="mb-5 flex flex-col items-center justify-center p-2 odd:bg-white even:bg-gray-50 md:table-row dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
          >
            <td>
              <img
                src="https://randomuser.me/api/portraits/men/3.jpg"
                alt="Foto de Luis Fernández"
                class="h-12 w-12 rounded-full"
              />
            </td>
            <td>Luis Fernández</td>
            <td>25</td>
            <td>luis.fernandez@email.com</td>
          </tr>
          <tr
            class="mb-5 flex flex-col items-center justify-center p-2 odd:bg-white even:bg-gray-50 md:table-row dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
          >
            <td>
              <img
                src="https://randomuser.me/api/portraits/women/4.jpg"
                alt="Foto de Ana Ruiz"
                class="h-12 w-12 rounded-full"
              />
            </td>
            <td>Ana Ruiz</td>
            <td>30</td>
            <td>ana.ruiz@email.com</td>
          </tr>
          <tr
            class="mb-5 flex flex-col items-center justify-center p-2 odd:bg-white even:bg-gray-50 md:table-row dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
          >
            <td>
              <img
                src="https://randomuser.me/api/portraits/men/5.jpg"
                alt="Foto de Carlos Torres"
                class="h-12 w-12 rounded-full"
              />
            </td>
            <td>Carlos Torres</td>
            <td>41</td>
            <td>carlos.torres@email.com</td>
          </tr>
          <tr
            class="mb-5 flex flex-col items-center justify-center p-2 odd:bg-white even:bg-gray-50 md:table-row dark:odd:bg-gray-900/50 dark:even:bg-gray-950"
          >
            <td>
              <img
                src="https://randomuser.me/api/portraits/women/6.jpg"
                alt="Foto de Laura Sánchez"
                class="h-12 w-12 rounded-full"
              />
            </td>
            <td>Laura Sánchez</td>
            <td>22</td>
            <td>laura.sanchez@email.com</td>
          </tr>
        </tbody>
      </table>
    </div>
    <a
      href="03-formularios.html"
      class="text-bold cursor-pointer text-red-400 hover:underline"
      >Siguiente Formularios</a
    >
  </body>
</html>
```

### 4.7 Ejercicio - Formularios

```bash
npm run dev
```

`src/01-pseudo-classes/03-formularios.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Formularios</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>
  <body class="p-8">
    <h1 class="mb-2 text-3xl font-bold">Formularios</h1>
    <hr />

    <form
      action=""
      class="mx-auto mt-10 flex max-w-md flex-col gap-6 rounded-lg border border-gray-700 bg-slate-900 p-8"
    >
      <!-- Campo Username (disabled) -->
      <div class="flex flex-col gap-2">
        <label for="username" class="font-medium text-white">Username</label>
        <input
          type="text"
          id="username"
          value="JuanCarlos"
          disabled
          class="form-control"
        />
      </div>

      <!-- Campo Email (con validación) -->
      <div class="flex flex-col gap-2">
        <label for="email" class="font-medium text-white">Email</label>
        <input
          type="email"
          id="email"
          placeholder="correo@ejemplo.com"
          class="form-control"
        />
        <span class="text-sm text-pink-500">Ingresa un correo válido</span>
      </div>

      <!-- Campo Password -->
      <div class="flex flex-col gap-2">
        <label for="password" class="font-medium text-white">Password</label>
        <input
          type="password"
          id="password"
          minlength="8"
          maxlength="16"
          placeholder="Mínimo 8 caracteres"
          class="form-control"
        />
        <span class="text-sm text-pink-500"
          >Ingresa una contraseña válida de entre 8 y 16 caracteres</span
        >
      </div>

      <!-- Botón Submit -->
      <div class="flex justify-end">
        <button
          type="submit"
          class="rounded-md bg-sky-500 px-6 py-3 font-semibold text-white transition-colors"
        >
          Save changes
        </button>
      </div>
    </form>

    <a href="04-has.html" class="mt-4 block text-blue-500">Siguiente Has</a>
  </body>
</html>
```

`src/styles.css`

```css
@import "tailwindcss";

@layer base {
  body {
    @apply bg-gray-950 p-8 px-4 py-2 text-red-500;
  }

  h1 {
    @apply mb-2 text-3xl font-bold;
  }
}

@layer components {
  .form-control {
    @apply rounded-md border border-gray-600 bg-transparent px-4 py-3 text-white transition-colors outline-none placeholder:text-sm placeholder:italic invalid:border-pink-500 invalid:text-pink-400 focus:border-sky-500 focus:invalid:border-pink-500 disabled:bg-transparent disabled:text-gray-400;
  }
}
```

### 4.8 Elementos hermanos - Peer

`src/01-pseudo-classes/03-formularios.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Formularios</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>
  <body class="p-8">
    <h1 class="mb-2 text-3xl font-bold">Formularios</h1>
    <hr />

    <form
      action=""
      class="mx-auto mt-10 flex max-w-md flex-col gap-6 rounded-lg border border-gray-700 bg-slate-900 p-8"
    >
      <!-- Campo Username (disabled) -->
      <div class="flex flex-col gap-2">
        <label for="username" class="font-medium text-white">Username</label>
        <input
          type="text"
          id="username"
          value="JuanCarlos"
          disabled
          class="form-control"
        />
      </div>

      <!-- Campo Email (con validación) -->
      <div class="flex flex-col gap-2">
        <label for="email" class="font-medium text-white">Email</label>
        <input
          type="email"
          id="email"
          placeholder="correo@ejemplo.com"
          class="form-control peer" 👈🏼👀👇🏼
        />
        <span class="invisible text-sm text-pink-500 peer-invalid:visible" 👈🏼👀
          >Ingresa un correo válido</span
        >
      </div>

      <!-- Campo Password -->
      <div class="flex flex-col gap-2">
        <label for="password" class="font-medium text-white">Password</label>
        <input
          type="password"
          id="password"
          minlength="8"
          maxlength="16"
          placeholder="Mínimo 8 caracteres"
          class="peer form-control"
        />
        <span class="invisible text-sm text-pink-500 peer-invalid:visible"
          >Ingresa una contraseña válida de entre 8 y 16 caracteres</span
        >
      </div>

      <!-- Botón Submit -->
      <div class="flex justify-end">
        <button
          type="submit"
          class="rounded-md bg-sky-500 px-6 py-3 font-semibold text-white transition-colors hover:bg-gray-800 focus:ring-2 focus:ring-sky-500 focus:ring-offset-2 focus:ring-offset-slate-900 focus:outline-none" 👈🏼👀
        >
          Save changes
        </button>
      </div>
    </form>

    <a href="04-has.html" class="mt-4 block text-blue-500">Siguiente Has</a>
  </body>
</html>
```

`01-css-local/src/styles.css`

```css
@import "tailwindcss";

@layer base {
  body {
    @apply bg-gray-950 p-8 px-4 py-2 text-red-500;
  }

  h1 {
    @apply mb-2 text-3xl font-bold;
  }

  button { 👈🏼👀👇🏼
    @apply cursor-pointer;
  }
}

@layer components {
  .form-control {
    @apply rounded-md border border-gray-600 bg-transparent px-4 py-3 text-white transition-colors outline-none placeholder:text-sm placeholder:italic invalid:border-pink-500 invalid:text-pink-400 focus:border-sky-500 focus:invalid:border-pink-500 disabled:bg-transparent disabled:text-gray-400;
  }
}
```

### 4.9 Ejemplo - Has()

`src/01-pseudo-classes/04.has.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body class="p-8">
    <h1 class="mb-2 text-3xl font-bold">
      Has - Estado basado en los descendientes
    </h1>
    <hr />
    <form
      action=""
      class="mx-auto mt-10 flex max-w-md flex-col gap-6 rounded-lg border border-gray-700 bg-slate-900 p-8"
    >
      <label
        class="flex 👈🏼👀 items-center gap-4 rounded-md p-2 transition-all has-checked:bg-indigo-500/50 has-checked:text-indigo-400" 👈🏼👀
      >
        <svg
          fill="currentColor" 👈🏼👀
          xmlns="http://www.w3.org/2000/svg"
          width="48"
          height="48"
          viewBox="0 0 24 24"
        >
          <path
            d="M3.963 7.235A3.96 3.96 0 0 0 .422 9.419a3.96 3.96 0 0 0 0 3.559a3.96 3.96 0 0 0 3.541 2.184c1.07 0 1.97-.352 2.627-.957c.748-.69 1.18-1.71 1.18-2.916a5 5 0 0 0-.07-.806H3.964v1.526h2.14a1.84 1.84 0 0 1-.79 1.205c-.356.241-.814.379-1.35.379c-1.034 0-1.911-.697-2.225-1.636a2.38 2.38 0 0 1 0-1.517c.314-.94 1.191-1.636 2.225-1.636a2.15 2.15 0 0 1 1.52.594l1.132-1.13a3.8 3.8 0 0 0-2.652-1.033zm6.501.55v6.9h.886V11.89h1.465q.904 0 1.522-.588a1.91 1.91 0 0 0 .635-1.464a1.92 1.92 0 0 0-.635-1.456a2.13 2.13 0 0 0-1.522-.598zm2.427.85a1.16 1.16 0 0 1 .823.365a1.176 1.176 0 0 1 0 1.686a1.17 1.17 0 0 1-.877.357H11.35V8.635zm4.124 1.175q-1.262 0-1.907.925l.781.491q.432-.626 1.175-.626a1.25 1.25 0 0 1 .856.323a1 1 0 0 1 .366.785v.202q-.51-.29-1.3-.289q-.926 0-1.479.434q-.555.432-.554 1.165a1.48 1.48 0 0 0 .525 1.156q.525.463 1.305.463q.915 0 1.465-.81h.038v.655h.848v-2.909q0-.915-.568-1.44q-.57-.525-1.551-.525m2.263.154l1.946 4.422l-1.098 2.38h.915L24 9.963h-.965l-1.368 3.391h-.02l-1.406-3.39zm-2.146 2.368q.741 0 1.156.33q0 .558-.44.973a1.4 1.4 0 0 1-.997.414a1.08 1.08 0 0 1-.69-.232a.71.71 0 0 1-.293-.578q0-.383.363-.647q.36-.26.9-.26Z"
          />
        </svg>
        <span class="flex-1 👈🏼👀 font-medium">Google Pay</span>
        <input checked type="radio" name="payment" value="google-pay" />
      </label>
      <label
        class="flex items-center gap-4 rounded-md p-2 transition-all has-checked:bg-indigo-500/50 has-checked:text-indigo-400"
      >
        <svg
          fill="currentColor"
          xmlns="http://www.w3.org/2000/svg"
          width="48"
          height="48"
          viewBox="0 0 24 24"
        >
          <path
            d="m2.15 4.318l-.454.003c-.15.005-.303.013-.452.04a1.44 1.44 0 0 0-1.06.772c-.07.138-.114.278-.14.43c-.028.148-.037.3-.04.45L0 6.222v11.557q0 .104.003.207c.004.15.013.303.04.452q.039.224.142.429a1.44 1.44 0 0 0 .63.63c.138.07.278.115.43.142c.148.027.3.036.45.04l.208.003h20.194l.207-.003c.15-.004.303-.013.452-.04s.291-.071.428-.141a1.43 1.43 0 0 0 .631-.631c.07-.138.115-.278.141-.43c.027-.148.036-.3.04-.45q.003-.104.003-.208l.001-.246V6.221q0-.104-.004-.207a3 3 0 0 0-.04-.452a1.45 1.45 0 0 0-1.2-1.201a3 3 0 0 0-.452-.04a11 11 0 0 0-.453-.003zm0 .512h19.942q.098 0 .197.003c.115.004.25.01.375.032c.109.02.2.05.287.094a.93.93 0 0 1 .407.407a1 1 0 0 1 .094.288c.022.123.028.258.031.374q.003.097.003.197v11.552q0 .097-.003.196c-.003.115-.009.25-.032.375a.93.93 0 0 1-.5.693a1 1 0 0 1-.286.094a3 3 0 0 1-.373.032l-.2.003H1.906q-.1 0-.196-.003a3 3 0 0 1-.375-.032c-.109-.02-.2-.05-.288-.094a.9.9 0 0 1-.406-.407a1 1 0 0 1-.094-.288a2.5 2.5 0 0 1-.032-.373l-.002-.197V6.224l.002-.197c.004-.114.01-.248.032-.375c.02-.108.05-.199.094-.287a.93.93 0 0 1 .407-.406a1 1 0 0 1 .287-.094c.125-.022.26-.029.375-.032l.196-.003zm4.71 3.7c-.3.016-.668.199-.88.456c-.191.22-.36.58-.316.918c.338.03.675-.169.888-.418c.205-.258.345-.603.308-.955zm2.207.42v5.493h.852v-1.877h1.18c1.078 0 1.835-.739 1.835-1.812c0-1.07-.742-1.805-1.808-1.805zm.852.719h.982c.739 0 1.161.396 1.161 1.089c0 .692-.422 1.092-1.164 1.092h-.979zm-3.154.3c-.45.01-.83.28-1.05.28c-.235 0-.593-.264-.981-.257a1.45 1.45 0 0 0-1.23.747c-.527.908-.139 2.255.374 2.995c.249.366.549.769.944.754c.373-.014.52-.242.973-.242c.454 0 .586.242.98.235c.41-.007.667-.366.915-.733c.286-.417.403-.82.41-.841c-.007-.008-.79-.308-.797-1.209c-.008-.754.615-1.113.644-1.135c-.352-.52-.9-.578-1.09-.593zm8.204.397c-.99 0-1.606.533-1.652 1.256h.777c.072-.358.369-.586.845-.586c.502 0 .803.266.803.711v.309l-1.097.064c-.951.054-1.488.484-1.488 1.184c0 .72.548 1.207 1.332 1.207c.526 0 1.032-.281 1.264-.727h.019v.659h.788v-2.76c0-.803-.62-1.317-1.591-1.317m1.94.072l1.446 4.009c0 .003-.073.24-.073.247c-.125.41-.33.571-.711.571c-.069 0-.206 0-.267-.015v.666c.06.011.267.019.335.019c.83 0 1.226-.312 1.568-1.283l1.5-4.214h-.868l-1.012 3.259h-.015l-1.013-3.26zm-1.167 2.189v.316c0 .521-.45.917-1.024.917c-.442 0-.731-.228-.731-.579c0-.342.278-.56.769-.593z"
          />
        </svg>
        <span class="flex-1 font-medium">Apple Pay</span>
        <input type="radio" name="payment" value="google-pay" />
      </label>
    </form>

    <a href="05-grupos.html" class="text-blue-500">Siguiente Grupos</a>
  </body>
</html>
```

### 4.10 Ejemplo - Grupos

`src/01-pseudo-classes/05-grupos.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body class="p-8">
    <h1 class="mb-2 text-3xl font-bold">Grupos</h1>
    <hr />

    <div
      class="group 👈🏼👀 mt-10 cursor-pointer rounded-md border bg-slate-800 p-6 text-white transition-colors hover:bg-sky-400 👈🏼👀"
    >
      <svg
        class="group-hover:text-gray-900 group-has-[a]:text-red-500" 👈🏼👀
        xmlns="http://www.w3.org/2000/svg"
        width="48"
        height="48"
        viewBox="0 0 16 16"
      >
        <path
          fill="currentColor" 👈🏼👀
          fill-rule="evenodd"
          d="M12.5 12.618c.307-.275.5-.674.5-1.118V6.977a1.5 1.5 0 0 0-.585-1.189l-3.5-2.692a1.5 1.5 0 0 0-1.83 0l-3.5 2.692A1.5 1.5 0 0 0 3 6.978V11.5A1.496 1.496 0 0 0 4.493 13H5V9.5a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2V13h.507c.381-.002.73-.146.993-.382m2-1.118a3 3 0 0 1-3 3h-7a3 3 0 0 1-3-3V6.977A3 3 0 0 1 2.67 4.6l3.5-2.692a3 3 0 0 1 3.66 0l3.5 2.692a3 3 0 0 1 1.17 2.378zm-5-2A.5.5 0 0 0 9 9H7a.5.5 0 0 0-.5.5V13h3z"
          clip-rule="evenodd"
        />
      </svg>
      <p class="mb-3">
        Este es un contenedor que cambiará de color si contiene un enlace.
      </p>
      <span class="hidden group-has-[a]:inline-block" 👈🏼👀>Ir al enlace</span>
      <a
        href="#"
        class="underline group-hover:text-gray-900 group-has-[a]:text-red-500" 👈🏼👀
        >Visita este enlace</a
      >
    </div>

    <div
      class="mt-10 rounded-md border bg-slate-800 p-6 text-white transition-colors"
    >
      <p class="mb-3">Este no cambiará de color.</p>

      <span class="hidden group-has-[a]:inline-block" 👈🏼👀
        >Ir al enlace (Yo no debería verme)</span
      >
    </div>

    <a href="06-hermanos.html" class="text-blue-500">Siguiente Hermanos</a>
  </body>
</html>
```

### 4.11 Ejemplo - Hermanos

`src/01-pseudo-classes/06-hermanos.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Selectores de Hermanos - Peer</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>
  <body class="p-8">
    <h1 class="mb-2 text-3xl font-bold">Selectores de Hermanos - Peer</h1>
    <hr />

    <div
      class="mx-auto mt-10 w-full max-w-lg rounded-lg bg-slate-900 p-8 shadow-xl"
    >
      <h1 class="mb-6 text-2xl font-bold text-white">
        Hoy es un buen día para...
      </h1>

      <ul class="space-y-4">
        <!-- Item completado -->
        <li class="flex items-center gap-4">
          <label
            for="task-1"
            class="peer 👈🏼👀 text-slate-40 flex flex-1 cursor-pointer items-center gap-4 text-lg"
          >
            <input
              type="checkbox"
              id="task-1"
              checked
              class="peer 👈🏼👀 relative h-6 w-6 cursor-pointer appearance-none rounded border-2 border-slate-600 checked:after:absolute checked:after:top-1/2 checked:after:left-1/2 checked:after:-translate-x-1/2 checked:after:-translate-y-1/2 checked:after:text-sm checked:after:text-white checked:after:content-['✓']"
            />
            <span
              class="flex-1 transition-all duration-300 ease-in-out peer-checked:line-through" 👈🏼👀
            >
              Crear una lista de tareas
            </span>
          </label>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="hidden h-5 w-5 text-gray-500 peer-has-checked:block" 👈🏼👀
            viewBox="0 0 20 20"
            fill="currentColor"
          >
            <path
              fill-rule="evenodd"
              d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
              clip-rule="evenodd"
            />
          </svg>
        </li>

        <!-- Item no completado -->
        <li class="flex items-center gap-4">
          <label
            for="task-2"
            class="peer text-slate-40 flex flex-1 cursor-pointer items-center gap-4 text-lg"
          >
            <input
              type="checkbox"
              id="task-2"
              class="peer relative h-6 w-6 cursor-pointer appearance-none rounded border-2 border-slate-600 checked:after:absolute checked:after:top-1/2 checked:after:left-1/2 checked:after:-translate-x-1/2 checked:after:-translate-y-1/2 checked:after:text-sm checked:after:text-white checked:after:content-['✓']"
            />
            <span class="flex-1 peer-checked:line-through">
              Aprender sobre selectores de hermanos
            </span>
          </label>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="hidden h-5 w-5 text-gray-500 peer-has-checked:block"
            viewBox="0 0 20 20"
            fill="currentColor"
          >
            <path
              fill-rule="evenodd"
              d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
              clip-rule="evenodd"
            />
          </svg>
        </li>

        <!-- Item no completado -->
        <li class="flex items-center gap-4">
          <label
            for="task-3"
            class="peer text-slate-40 flex flex-1 cursor-pointer items-center gap-4 text-lg"
          >
            <input
              type="checkbox"
              id="task-3"
              class="peer relative h-6 w-6 cursor-pointer appearance-none rounded border-2 border-slate-600 checked:after:absolute checked:after:top-1/2 checked:after:left-1/2 checked:after:-translate-x-1/2 checked:after:-translate-y-1/2 checked:after:text-sm checked:after:text-white checked:after:content-['✓']"
            />
            <span class="flex-1 peer-checked:line-through">
              Compartir mi lista con amigos
            </span>
          </label>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="hidden h-5 w-5 text-gray-500 peer-has-checked:block"
            viewBox="0 0 20 20"
            fill="currentColor"
          >
            <path
              fill-rule="evenodd"
              d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
              clip-rule="evenodd"
            />
          </svg>
        </li>
      </ul>
    </div>

    <a
      href="07-grupos-anidados.html"
      class="mt-4 block self-start text-blue-500"
      >Siguiente Grupos Anidados</a
    >
  </body>
</html>
```

### 4.12 Ejemplo - Grupos anidados

`src/01-pseudo-classes/07-grupos-anidados.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body class="p-8">
    <h1 class="mb-2 text-3xl font-bold">Grupos Anidados</h1>
    <hr />

    <div
      class="mx-auto mt-10 w-full max-w-lg rounded-lg bg-slate-900 p-8 shadow-xl"
    >
      <h2 class="mb-6 text-2xl font-bold text-white">Nuestro equipo</h2>

      <ul role="list" class="mt-10 space-y-4">
        <!-- Person 1 -->
        <li
          class="group/item 👈🏼👀 flex cursor-pointer items-center gap-4 rounded-xl bg-slate-800 px-6 py-4 hover:bg-red-500/30 👈🏼👀"
        >
          <img
            src="https://randomuser.me/api/portraits/women/32.jpg"
            alt="Foto de Leslie Abbott"
            class="h-12 w-12 rounded-full object-cover"
          />
          <div class="flex-1">
            <p class="font-semibold text-white">Leslie Abbott</p>
            <p class="text-sm text-slate-400">Co-Founder / CEO</p>
          </div>
          <a
            href="#"
            class="group/edit 👈🏼👀 invisible 👈🏼👀 flex items-center gap-1 font-medium text-blue-400 transition group-hover/item:visible 👈🏼👀"
          >
            <span class="transition-colors group-hover:text-gray-200"
              >Call</span
            >
            <svg
              class="transition-transform delay-200 group-hover/edit:translate-x-0.5 👈🏼👀"
              width="18"
              height="18"
              fill="none"
              viewBox="0 0 20 20"
            >
              <path
                fill="currentColor"
                fill-rule="evenodd"
                d="M7.293 14.707a1 1 0 0 1 0-1.414L10.586 10 7.293 6.707a1 1 0 0 1 1.414-1.414l4 4a1 1 0 0 1 0 1.414l-4 4a1 1 0 0 1-1.414 0z"
                clip-rule="evenodd"
              />
            </svg>
          </a>
        </li>
        <!-- Person 2 -->
        <li
          class="group/item flex cursor-pointer items-center gap-4 rounded-xl bg-slate-800 px-6 py-4 hover:bg-red-500/30"
        >
          <img
            src="https://randomuser.me/api/portraits/men/44.jpg"
            alt="Foto de Hector Adams"
            class="h-12 w-12 rounded-full object-cover"
          />
          <div class="flex-1">
            <p class="font-semibold text-white">Hector Adams</p>
            <p class="text-sm text-slate-400">VP, Marketing</p>
          </div>
          <a
            href="#"
            class="group/edit invisible flex items-center gap-1 font-medium text-blue-400 transition group-hover/item:visible"
          >
            <span class="transition-colors group-hover/edit:text-gray-200"
              >Call</span
            >
            <svg
              class="transition-transform group-hover/edit:translate-x-0.5"
              width="18"
              height="18"
              fill="none"
              viewBox="0 0 20 20"
            >
              <path
                fill="currentColor"
                fill-rule="evenodd"
                d="M7.293 14.707a1 1 0 0 1 0-1.414L10.586 10 7.293 6.707a1 1 0 0 1 1.414-1.414l4 4a1 1 0 0 1 0 1.414l-4 4a1 1 0 0 1-1.414 0z"
                clip-rule="evenodd"
              />
            </svg>
          </a>
        </li>
        <!-- Person 3 -->
        <li
          class="group/item flex cursor-pointer items-center gap-4 rounded-xl bg-slate-800 px-6 py-4"
        >
          <img
            src="https://randomuser.me/api/portraits/men/36.jpg"
            alt="Foto de Blake Alexander"
            class="h-12 w-12 rounded-full object-cover"
          />
          <div class="flex-1">
            <p class="font-semibold text-white">Blake Alexander</p>
            <p class="text-sm text-slate-400">Account Coordinator</p>
          </div>
          <a
            href="#"
            class="group/edit invisible flex items-center gap-1 font-medium text-blue-400 transition group-hover/item:visible"
          >
            <span class="transition-colors group-hover/edit:text-gray-200"
              >Call</span
            >
            <svg
              class="transition-transform group-hover/edit:translate-x-0.5"
              width="18"
              height="18"
              fill="none"
            >
              <path
                fill="currentColor"
                fill-rule="evenodd"
                d="M7.293 14.707a1 1 0 0 1 0-1.414L10.586 10 7.293 6.707a1 1 0 0 1 1.414-1.414l4 4a1 1 0 0 1 0 1.414l-4 4a1 1 0 0 1-1.414 0z"
                clip-rule="evenodd"
              />
            </svg>
          </a>
        </li>
      </ul>
    </div>

    <a href="08-grupos-implicitos.html" class="text-blue-500"
      >Siguiente Grupos Implícitos</a
    >
  </body>
</html>
```

### 4.13 Ejemplo - Grupos implícitos

`src/01-pseudo-classes/08-grupos-implicitos.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body class="p-8">
    <h1 tabindex="0" class="mb-2 text-3xl font-bold">Grupos Implícitos</h1>
    <hr />

    <div
      class="mx-auto mt-10 w-full max-w-lg rounded-lg bg-slate-900 p-8 shadow-xl"
    >
      <h2 class="mb-6 text-2xl font-bold text-white">
        Ejemplo: Grupos Implícitos (in-*)
      </h2>

      <div class="space-y-8">
        <!-- Ejemplo con .group y .group-focus -->
        <div>
          <p class="mb-4 font-medium text-white">
            Usando
            <span class="rounded bg-slate-700 px-1">group</span> tradicional:
          </p>
          <div
            tabindex="0" 👈🏼👀
            class="group 👈🏼👀 cursor-pointer rounded-lg bg-slate-800 p-4 ring-pink-500 👈🏼👀 transition outline-none 👈🏼👀 focus:ring-2 👈🏼👀"
          >
            <p class="mb-2 text-sm text-slate-300">
              Haz foco (tab o click) en esta caja para ver el efecto:
            </p>
            <div
              class="rounded bg-pink-500 p-3 text-white opacity-30 👈🏼👀 transition-opacity group-hover:bg-red-800 👈🏼👀 group-focus:opacity-100 👈🏼👀"
            >
              <span class="font-semibold">group-focus:</span> ¡Ahora me ves
              claramente!
            </div>
          </div>
        </div>

        <!-- Ejemplo con in-focus -->
        <div>
          <p class="mb-2 font-medium text-white">
            Usando
            <span class="rounded bg-slate-700 px-1">in-focus</span> (grupo
            implícito):
          </p>
          <div
            tabindex="0" 👈🏼👀
            class="cursor-pointer rounded-lg bg-slate-800 p-4 ring-pink-500 transition outline-none 👈🏼👀 focus:ring-2 👈🏼👀"
          >
            <p class="mb-2 text-sm text-slate-300">
              Haz foco (tab o click) en esta caja para ver el efecto:
            </p>
            <div
              class="rounded bg-pink-500 p-3 text-white opacity-30 👈🏼👀 transition-opacity in-hover:bg-amber-500 👈🏼👀 in-focus:opacity-100 👈🏼👀"
            >
              <span class="font-semibold">in-focus:</span> ¡Yo no necesito
              class="group"!
            </div>
          </div>
        </div>
      </div>
    </div>

    <a href="09-diferenciando-peers.html" class="text-blue-500"
      >Siguiente Diferenciando Peers</a
    >
  </body>
</html>
```

| Característica   | group-focus       | in-focus            |
|------------------|-------------------|---------------------|
| Clase en padre   | ✅ Necesita group | ❌ No necesita nada |
| Sintaxis en hijo | group-focus:*     | in-focus:*          |
| Versión          | v3+               | v4+                 |
| Verbosidad       | Mayor             | Menor               |

### 4.14 Ejemplo - Diferenciando peers

`src/01-pseudo-classes/09-diferenciando-peers.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body class="p-8">
    <h1 class="mb-2 text-3xl font-bold">Diferenciando Peers</h1>
    <hr />

    <fieldset
      class="mx-auto mt-10 w-full max-w-lg rounded-lg bg-slate-900 p-8 shadow-xl"
    >
      <legend>Published status</legend>

      <!-- Los inputs deben estar ANTES y ser HERMANOS de los elementos que reaccionan -->
      <input id="draft" class="peer/draft" 👈🏼👀 type="radio" name="status" />
      <label for="draft" class="mr-6 cursor-pointer font-medium">Draft</label>

      <input id="published" class="peer/published" 👈🏼👀 type="radio" name="status" />
      <label for="published" class="cursor-pointer font-medium"
        >Published</label
      >

      <!-- Estos divs son hermanos de los inputs -->
      <div class="mt-4 hidden 👈🏼👀 text-gray-300 peer-checked/draft:block 👈🏼👀">
        Drafts are only visible to administrators.
      </div>
      <div class="mt-4 hidden 👈🏼👀 text-gray-300 peer-checked/published:block 👈🏼👀">
        Your post will be publicly visible on your site.
      </div>
    </fieldset>
  </body>
</html>
```

[Styling based on sibling state](https://tailwindcss.com/docs/hover-focus-and-other-states#styling-based-on-sibling-state)

### 4.15 Código fuente

Aquí tienen el código fuente de la sección por si quieren saltarse toda la preparación inicial y llegar directamente a los ejercicios.

[GitHub - Tailwindcss Localmente](https://github.com/DevTalles-corp/tailwindcss-css-localmente/tree/fin-seccion-04)

## 5. Tema y configuraciones

### 5.1 Introducción

### 5.2 Temas puntuales

En esta sección estaremos aprendiendo sobre personalizaciones en el lado de TailwindCSS, tanto en modo light y dark como en configuraciones globales de estilo y temas.

**Puntualmente veremos:**

- **Ejemplo – Diseño responsivo**
    
    Crear una interfaz adaptable usando breakpoints y utilidades responsivas.
    
- **Ejemplo – Tema Light y Dark**
    
    Implementar soporte para modos claro y oscuro usando clases y configuraciones.
    
- **Cambiar tema manualmente**
    
    Agregar botón o toggle para alternar entre temas en tiempo real.
    
- **Ejercicio – Variables de color**
    
    Practicar la creación y uso de variables personalizadas dentro del tema.
    
- **Ejercicio – Fuentes personalizadas**
    
    Integrar nuevas tipografías y aplicarlas mediante configuraciones del theme.

### 5.3 Continuación de proyecto

Revisa el README.md de la sección anterior y descarga el archivo adjunto.

Estructura:

```bash
.
└── 01-css-local
    ├── dist
    │   └── output.css
    ├── .gitignore
    ├── package.json
    ├── package-lock.json
    ├── .prettierrc
    ├── README.md
    └── src
        ├── 01-pseudo-classes
        │   ├── 01-listas.html
        │   ├── 02-tablas.html
        │   ├── 03-formularios.html
        │   ├── 04-has.html
        │   ├── 05-grupos.html
        │   ├── 06-hermanos.html
        │   ├── 07-grupos-anidados.html
        │   ├── 08-grupos-implicitos.html
        │   └── 09-diferenciando-peers.html
        ├── 02-temas 👈🏼👀👇🏼
        │   ├── 01-responsivo.html
        │   ├── 02-dark.html
        │   ├── 03-variantes-color.html
        │   └── 04-fuente.html
        ├── index.html
        └── styles.css
```

[Descargar](https://import.cdn.thinkific.com/643563/tn8Cam8MSjSVQwCfdT99_02-temas.zip)

### 5.4 Ejemplo - Diseño responsivo

`src/02-temas/01-responsivo.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body>
    <h1 class="text-3xl font-bold">Diseño responsivo con Tailwind</h1>

    <!-- Ejemplo de Grid responsivo en TailwindCSS -->
    <div
      class="mt-10 grid 👈🏼👀 grid-cols-1 gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 👈🏼👀"
    >
      <div
        class="rounded-lg bg-slate-700 p-6 text-white shadow-lg sm:bg-red-400 👈🏼👀 md:bg-red-500 lg:bg-red-600 xl:bg-red-700 👈🏼👀"
      >
        <h2 class="mb-2 text-xl font-semibold">Card 1</h2>
        <p>
          Este es un ejemplo de una tarjeta en un grid responsivo. En pantallas
          pequeñas hay una columna, en medianas dos, y en grandes tres.
        </p>
      </div>
      <div class="rounded-lg bg-slate-700 p-6 text-white shadow-lg">
        <h2 class="mb-2 text-xl font-semibold">Card 2</h2>
        <p>
          Usa <code>grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3</code> para
          controlar el número de columnas según el tamaño de pantalla.
        </p>
      </div>
      <div class="rounded-lg bg-slate-700 p-6 text-white shadow-lg">
        <h2 class="mb-2 text-xl font-semibold">Card 3</h2>
        <p>
          El sistema de grid de TailwindCSS hace que el diseño sea flexible y
          sencillo de adaptar.
        </p>
      </div>
      <div class="rounded-lg bg-slate-700 p-6 text-white shadow-lg">
        <h2 class="mb-2 text-xl font-semibold">Card 4</h2>
        <p>
          Puedes agregar o quitar tarjetas y el grid se ajustará
          automáticamente.
        </p>
      </div>
      <div class="rounded-lg bg-slate-700 p-6 text-white shadow-lg">
        <h2 class="mb-2 text-xl font-semibold">Card 5</h2>
        <p>
          Con Tailwind puedes personalizar el número de columnas y el espacio
          entre ellas para lograr diferentes diseños responsivos.
        </p>
      </div>
      <div class="rounded-lg bg-slate-700 p-6 text-white shadow-lg">
        <h2 class="mb-2 text-xl font-semibold">Card 6</h2>
        <p>
          Tailwind facilita la creación de layouts adaptables a cualquier
          dispositivo con clases utilitarias.
        </p>
      </div>
    </div>

    <a href="02-dark.html" class="text-blue-500">Siguiente Tema Dark / Light</a>
  </body>
</html>
```

### 5.5 Ejemplo - Tema light y Dark

`src/02-temas/02-dark.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body>
    <h1 class="text-3xl font-bold">Tema Dark / Light</h1>

    <div class="mt-10 flex gap-8">
      <!-- Tarjeta Modo Light -->
      <div
        class="flex-1 rounded-lg border border-slate-200 bg-white p-6 text-slate-900 shadow-lg transition-colors dark:border-gray-700 👈🏼👀 dark:bg-gray-800 👈🏼👀"
      >
        <div class="mb-4 flex items-center">
          <svg
            class="mr-3 h-7 w-7 text-yellow-400"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <circle
              cx="12"
              cy="12"
              r="5"
              stroke="currentColor"
              fill="currentColor"
            />
            <g stroke="currentColor">
              <line x1="12" y1="1" x2="12" y2="3" />
              <line x1="12" y1="21" x2="12" y2="23" />
              <line x1="4.22" y1="4.22" x2="5.64" y2="5.64" />
              <line x1="18.36" y1="18.36" x2="19.78" y2="19.78" />
              <line x1="1" y1="12" x2="3" y2="12" />
              <line x1="21" y1="12" x2="23" y2="12" />
              <line x1="4.22" y1="19.78" x2="5.64" y2="18.36" />
              <line x1="18.36" y1="5.64" x2="19.78" y2="4.22" />
            </g>
          </svg>
          <h2 class="text-xl font-semibold text-slate-900 dark:text-white 👈🏼👀">
            Modo Light
          </h2>
        </div>
        <p class="text-slate-700 dark:text-white/80 👈🏼👀">
          Este es un ejemplo de tarjeta en modo
          <span class="font-bold">claro (light)</span>. El fondo es claro y el
          texto oscuro. El icono representa el sol.
        </p>
      </div>

      <!-- Tarjeta Modo Dark -->
      <div
        class="flex-1 rounded-lg border border-slate-700 bg-slate-800 p-6 text-white shadow-lg transition-colors dark:border-gray-200 👈🏼👀 dark:bg-gray-50 👈🏼👀"
      >
        <div class="mb-4 flex items-center">
          <svg
            class="mr-3 h-7 w-7 text-sky-400"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <path
              d="M21 12.79A9 9 0 1111.21 3 7 7 0 0021 12.79z"
              fill="currentColor"
              stroke="currentColor"
            />
          </svg>
          <h2 class="text-xl font-semibold text-white dark:text-gray-900 👈🏼👀">
            Modo Dark
          </h2>
        </div>
        <p class="text-slate-300 dark:text-gray-900 👈🏼👀">
          Este es un ejemplo de tarjeta en modo
          <span class="font-bold">oscuro (dark)</span>. El fondo es oscuro y el
          texto claro. El icono representa la luna.
        </p>
      </div>
    </div>

    <h1 class="my-5 text-xl font-bold">
      Actualmente:
      <span>Tema Light</span>
      <span>Tema Dark</span>
    </h1>

    <button
      id="theme-toggle"
      class="my-10 mt-10 block rounded-md bg-sky-500 px-6 py-3 font-semibold text-white transition-colors hover:bg-sky-600 focus:ring-2 focus:ring-sky-500 focus:ring-offset-2 focus:ring-offset-slate-900 focus:outline-none"
    >
      Toggle theme
    </button>

    <a href="03-variantes-color.html" class="text-blue-500"
      >Siguiente: Variantes de color</a
    >

    <script>
      // Todo: Agregar botón para cambiar tema aquí:
      // Docs: https://tailwindcss.com/docs/dark-mode#toggling-dark-mode-manually
    </script>
  </body>
</html>
```

Luego de añadir las clases utilitarias, ve a apariencia de tu computador y cambia a modo light o modo dark para hacer prueba.

[Toggling dark mode manually](https://tailwindcss.com/docs/dark-mode#toggling-dark-mode-manually)

### 5.6 Cambiar tema manualmente

`src/02-temas/0.html`

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="../../dist/output.css" />
  </head>

  <body>
    <h1 class="text-3xl font-bold">Tema Dark / Light</h1>

    <div class="mt-10 flex gap-8">
      <!-- Tarjeta Modo Light -->
      <div
        class="flex-1 rounded-lg border border-slate-200 bg-white p-6 text-slate-900 shadow-lg transition-colors dark:border-gray-700 dark:bg-gray-800"
      >
        <div class="mb-4 flex items-center">
          <svg
            class="mr-3 h-7 w-7 text-yellow-400"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <circle
              cx="12"
              cy="12"
              r="5"
              stroke="currentColor"
              fill="currentColor"
            />
            <g stroke="currentColor">
              <line x1="12" y1="1" x2="12" y2="3" />
              <line x1="12" y1="21" x2="12" y2="23" />
              <line x1="4.22" y1="4.22" x2="5.64" y2="5.64" />
              <line x1="18.36" y1="18.36" x2="19.78" y2="19.78" />
              <line x1="1" y1="12" x2="3" y2="12" />
              <line x1="21" y1="12" x2="23" y2="12" />
              <line x1="4.22" y1="19.78" x2="5.64" y2="18.36" />
              <line x1="18.36" y1="5.64" x2="19.78" y2="4.22" />
            </g>
          </svg>
          <h2 class="text-xl font-semibold text-slate-900 dark:text-white">
            Modo Light
          </h2>
        </div>
        <p class="text-slate-700 dark:text-white/80">
          Este es un ejemplo de tarjeta en modo
          <span class="font-bold">claro (light)</span>. El fondo es claro y el
          texto oscuro. El icono representa el sol.
        </p>
      </div>

      <!-- Tarjeta Modo Dark -->
      <div
        class="flex-1 rounded-lg border border-slate-700 bg-slate-800 p-6 text-white shadow-lg transition-colors dark:border-gray-200 dark:bg-gray-50"
      >
        <div class="mb-4 flex items-center">
          <svg
            class="mr-3 h-7 w-7 text-sky-400"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <path
              d="M21 12.79A9 9 0 1111.21 3 7 7 0 0021 12.79z"
              fill="currentColor"
              stroke="currentColor"
            />
          </svg>
          <h2 class="text-xl font-semibold text-white dark:text-gray-900">
            Modo Dark
          </h2>
        </div>
        <p class="text-slate-300 dark:text-gray-900">
          Este es un ejemplo de tarjeta en modo
          <span class="font-bold">oscuro (dark)</span>. El fondo es oscuro y el
          texto claro. El icono representa la luna.
        </p>
      </div>
    </div>

    <h1 class="my-5 text-xl font-bold">
      Actualmente:
      <span class="block dark:hidden">Tema Light</span>
      <span class="hidden dark:block">Tema Dark</span>
    </h1>

    <button
      id="theme-toggle"
      class="my-10 mt-10 block rounded-md bg-sky-500 px-6 py-3 font-semibold text-white transition-colors hover:bg-sky-600 focus:ring-2 focus:ring-sky-500 focus:ring-offset-2 focus:ring-offset-slate-900 focus:outline-none"
    >
      Toggle theme
    </button>

    <a href="03-variantes-color.html" class="text-blue-500"
      >Siguiente: Variantes de color</a
    >

    <script> 👈🏼👀👇🏼
      // Todo: Agregar botón para cambiar tema aquí:
      // Docs: https://tailwindcss.com/docs/dark-mode#toggling-dark-mode-manually
      document.documentElement.classList.toggle(
        "dark",
        localStorage.theme === "dark" ||
          (!("theme" in localStorage) &&
            window.matchMedia("(prefers-color-scheme: dark)").matches),
      );

      document.querySelector("#theme-toggle").addEventListener("click", () => {
        // console.log("Click en toggle");
        localStorage.theme = document.documentElement.classList.contains("dark")
          ? "dark"
          : "light";
      });
    </script>
  </body>
</html>
```

`src/styles.css`

```css
@import "tailwindcss";
@custom-variant dark (&:where(.dark, .dark *)); 👈🏼👀

@layer base {
  body {
    @apply bg-gray-950 p-8 px-4 py-2 text-red-500;
  }

  h1 {
    @apply mb-2 text-3xl font-bold;
  }

  button {
    @apply cursor-pointer;
  }
}

@layer components {
  .form-control {
    @apply rounded-md border border-gray-600 bg-transparent px-4 py-3 text-white transition-colors outline-none placeholder:text-sm placeholder:italic invalid:border-pink-500 invalid:text-pink-400 focus:border-sky-500 focus:invalid:border-pink-500 disabled:bg-transparent disabled:text-gray-400;
  }
}
```

#### `document.documentElement`

En el DOM, `document` representa todo el documento HTML.

Dentro de él existe una propiedad llamada:

```js
document.documentElement
```

Eso representa el elemento raíz del HTML, es decir:

```html
<html>...</html>
```

🔎 Entonces:

```js
document.documentElement
```

es exactamente lo mismo que hacer:

```js
document.querySelector("html")
```

Es el elemento `<html>`.

#### `classList`

Todos los elementos HTML tienen una propiedad:

```js
element.classList
```

Es un objeto que permite manipular las clases CSS fácilmente.

Ejemplo:

```js
element.classList.add("dark")
element.classList.remove("dark")
element.classList.toggle("dark")
element.classList.contains("dark")
```

No es una clase CSS.  
No es algo de Tailwind.  
Es una API nativa del DOM.

#### `toggle()`

`toggle()` es un método de `classList`.

Funciona así:

```js
element.classList.toggle("dark")
```

Si la clase existe → la elimina  
Si la clase NO existe → la agrega

Es básicamente un interruptor.

##### ⚡ Pero aquí lo usan diferente:

```js
document.documentElement.classList.toggle(
  "dark",
  condicion
);
```

`toggle()` tiene una segunda forma:

```js
toggle(nombreClase, booleano)
```

Si el booleano es:

- `true` → agrega la clase
- `false` → la elimina

Entonces esto:

```js
classList.toggle("dark", true)
```

es igual a:

```js
classList.add("dark")
```

Y esto:

```js
classList.toggle("dark", false)
```

es igual a:

```js
classList.remove("dark")
```

Ahora entendamos esta parte completa

```js
document.documentElement.classList.toggle(
  "dark",
  localStorage.theme === "dark" ||
    (!("theme" in localStorage) &&
      window.matchMedia("(prefers-color-scheme: dark)").matches),
);
```

Vamos por partes.

#### `localStorage`

`localStorage` es un almacenamiento del navegador.

Guarda datos en formato clave → valor.

Ejemplo:

```js
localStorage.theme = "dark";
```

Eso guarda:

```
clave: "theme"
valor: "dark"
```

Se mantiene incluso si recargas la página.

¿De dónde sale `"theme"`?

Aquí:

```js
localStorage.theme = ...
```

Ahí se está creando la clave.

No existe antes.  
Se crea cuando la asignas.

Es lo mismo que:

```js
localStorage.setItem("theme", "dark")
```

¿Qué significa esto?

```js
localStorage.theme === "dark"
```

Significa:

> "Si en el almacenamiento existe una clave llamada theme y su valor es 'dark'"

#### `"theme" in localStorage`

El operador `in` en JavaScript verifica si una propiedad existe dentro de un objeto.

Ejemplo:

```js
"theme" in localStorage
```

Significa:

> ¿Existe la clave "theme" en localStorage?

Devuelve `true` o `false`.

Entonces esto:

```js
!("theme" in localStorage)
```

Significa:

> NO existe la clave "theme" en localStorage

El `!` es negación.

#### `window.matchMedia()`

`matchMedia()` es una API que permite evaluar media queries desde JavaScript.

Es como escribir CSS, pero en JS.

Ejemplo:

```js
window.matchMedia("(prefers-color-scheme: dark)")
```

Pregunta al sistema operativo:

> ¿El usuario tiene activado modo oscuro en su sistema?

Devuelve un objeto.

#### `.matches`

Ese objeto tiene una propiedad:

```js
.matches
```

Devuelve:

- `true` → si la condición se cumple
    
- `false` → si no
    

Entonces:

```js
window.matchMedia("(prefers-color-scheme: dark)").matches
```

Significa:

> ¿El sistema del usuario está en modo oscuro?

#### 🔥 Ahora entendamos TODA la condición

```js
localStorage.theme === "dark" ||
(
  !("theme" in localStorage) &&
  window.matchMedia("(prefers-color-scheme: dark)").matches
)
```

Traducción en español:

Activa dark si:

1. El usuario ya guardó dark en localStorage  
    O
    
2. No existe preferencia guardada Y el sistema está en dark
    

"Si el usuario ya eligió modo oscuro, respétalo.  
Si nunca eligió nada, usa la preferencia del sistema."

#### Ahora el botón

```js
document.querySelector("#theme-toggle")
  .addEventListener("click", () => {
```

Esto selecciona el botón con id:

```html
<button id="theme-toggle">
```

Y le agrega un evento click.

Dentro del click:

```js
document.documentElement.classList.toggle("dark");
```

Sin segundo parámetro.

Eso significa:

Si tiene dark → lo quita  
Si no tiene dark → lo agrega

Es un interruptor manual.

Luego:

```js
localStorage.theme = document.documentElement.classList.contains("dark")
  ? "dark"
  : "light";
```

Aquí aparece algo nuevo:

#### `classList.contains()`

Sirve para verificar si una clase existe.

Devuelve `true` o `false`.

#### Operador ternario

```js
condicion ? valor1 : valor2
```

Es lo mismo que:

```js
if (condicion) {
  return valor1
} else {
  return valor2
}
```

Entonces esto:

```js
document.documentElement.classList.contains("dark")
  ? "dark"
  : "light";
```

Significa:

Si el html tiene la clase dark → guarda "dark"  
Si no → guarda "light"

#### Resumen

Cuando la página carga:

1. Revisa si hay una preferencia guardada.
2. Si sí → la usa.
3. Si no → revisa el sistema operativo.
4. Agrega o quita la clase `dark` al `<html>`.

Cuando haces click:

1. Alterna la clase `dark`.
2. Guarda la nueva preferencia en localStorage.

Visualización simple

```text
<html class="dark">   ← aquí vive todo el sistema
```

Tailwind detecta esa clase y activa todos los estilos `dark:`.

Lo más importante que aprendiste aquí

|Código                   |Qué es                                  |
|-------------------------|----------------------------------------|
|document.documentElement |El `<html>`                             |
|classList                |API para manipular clases               |
|toggle()                 |Agrega o quita clase                    |
|contains()               |Verifica si existe                       |
|localStorage             |Almacenamiento persistente del navegador |
|"prop" in objeto         |Verifica si existe una propiedad         |
|matchMedia()             |Evalúa media queries en JS               |
|.matches                 |Devuelve true/false                      |
|? :                      |Operador ternario                        |

[Toggling dark mode manually](https://tailwindcss.com/docs/dark-mode#toggling-dark-mode-manually)

### 5.7

`src/02-temas/0.html`

```html

```
👈🏼👀
👈🏼👀👇🏼
🔥

### 5.8

`src/02-temas/0.html`

```html

```
👈🏼👀
👈🏼👀👇🏼
🔥