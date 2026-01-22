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

```html

```

```css

```

```html

```

```css

```

```html

```

```css

```
👈🏼👀
👈🏼👀👇🏼
🔥