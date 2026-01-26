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

### 4.4

```html

```

```css

```


```html

```


👈🏼👀
👈🏼👀👇🏼
🔥

### 4.5

```html

```

```css

```


```html

```


👈🏼👀
👈🏼👀👇🏼
🔥

### 4.6

```html

```

```css

```


```html

```


👈🏼👀
👈🏼👀👇🏼
🔥

### 4.7

```html

```

```css

```


```html

```


👈🏼👀
👈🏼👀👇🏼
🔥

### 4.8

```html

```

```css

```


```html

```


👈🏼👀
👈🏼👀👇🏼
🔥

### 4.9

```html

```

```css

```


```html

```


👈🏼👀
👈🏼👀👇🏼
🔥

### 4.10

```html

```

```css

```


```html

```


👈🏼👀
👈🏼👀👇🏼
🔥

### 4.11

```html

```

```css

```


```html

```


👈🏼👀
👈🏼👀👇🏼
🔥

### 4.12

```html

```

```css

```


```html

```


👈🏼👀
👈🏼👀👇🏼
🔥

```html

```

```css

```
👈🏼👀
👈🏼👀👇🏼
🔥