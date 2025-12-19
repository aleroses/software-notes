# Zustand: Gestor de estado para React

## 1. Introducción

### 1.1 Introducción

### 1.2 ¿Cómo funcionará el curso?

### 1.3 ¿Cómo hacer preguntas?

### 1.4 Instalaciones necesarias

![](https://repository-images.githubusercontent.com/180328715/fca49300-e7f1-11ea-9f51-cfd949b31560)

- [Google Chrome](https://www.google.com/chrome/)
- [React Developer Tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=es&authuser=1)
- [Redux Devtools](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=es)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Postman](https://www.postman.com/downloads/)
- [Node](https://nodejs.org/es/)
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)

#### Temas que estoy usando en VSCode:

* [Tokyo Night](https://marketplace.visualstudio.com/items?itemName=enkia.tokyo-night)

* [Iconos](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)

#### Extensiones Recomendadas

- [Activitus Bar](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.activitusbar)
- [ES7 React/Redux](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
- [Simple React Snippets](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets)
- [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)

#### Mis wallpapers 

[Wallpapers Developer](https://drive.google.com/drive/folders/1ItU8rbSGJjnh2USOBGwaCo9nYKifPJ6m?usp=sharing)

#### Comunidad de Discord

[Comunidad de Discord](https://discord.gg/KySgxtdKv6)

#### Adicional

Muchos me preguntan sobre mis ajustes de VSCode, aquí se los dejo como los estoy usando en este curso:

```json
{
    "editor.tabSize": 2,
    "editor.detectIndentation": false,
    "editor.insertSpaces": true,
    "terminal.integrated.fontFamily": "MesloLGM NF",
    "explorer.compactFolders": false,
    "workbench.iconTheme": "material-icon-theme",
    // "material-icon-theme.activeIconPack": "qwik",
    "workbench.startupEditor": "none",
    "workbench.colorCustomizations": {
        "statusBar.background": "#121016",
        "statusBar.debuggingBackground": "#121016",
        "statusBar.debuggingForeground": "#525156",
        "debugToolBar.background": "#121016",
    },
    "[dart]": {
        "editor.formatOnSave": false,
        "editor.formatOnType": false,
        "editor.selectionHighlight": false,
        "editor.suggest.snippetsPreventQuickSuggestions": false,
        "editor.suggestSelection": "first",
        "editor.tabCompletion": "onlySnippets",
        "editor.wordBasedSuggestions": false
    },
    "explorer.confirmDelete": false,
    "[json]": {
        "editor.defaultFormatter": "vscode.json-language-features"
    },
    "explorer.confirmDragAndDrop": false,
    "extensions.autoUpdate": false,
    "git.enableSmartCommit": true,
    "terminal.integrated.enableMultiLinePasteWarning": false,
    "workbench.layoutControl.enabled": false,
    "window.commandCenter": false,
    "security.workspace.trust.untrustedFiles": "open",
    "git.openRepositoryInParentFolders": "never",
    "git.confirmSync": false,
    "codesnap.backgroundColor": "rgba(0, 0, 0, 0.0)",
    "editor.minimap.enabled": false,
    "workbench.activityBar.visible": false,
    "window.titleBarStyle": "custom",
    "codesnap.boxShadow": "rgba(0, 0, 0, 0.55) 0px 0px 20px",
    "terminal.integrated.env.osx": {
      "FIG_NEW_SESSION": "1"
    },
    "audioCues.diffLineDeleted": "off",
    "editor.accessibilitySupport": "off",
    "workbench.colorTheme": "Tokyo Night",
    "liveServer.settings.donotVerifyTags": true,
    "git.autofetch": true,
    "editor.cursorBlinking": "smooth",
    "editor.cursorSmoothCaretAnimation": "on",
    "editor.cursorWidth": 2,
    "reactSnippets.settings.importReactOnTop": false,
    "window.zoomLevel": 4,
    "codesnap.shutterAction": "copy",
    "codesnap.showWindowControls": false,
    "dart.flutterSdkPath": "/Users/strider/Development/flutter",
    "javascript.format.insertSpaceAfterOpeningAndBeforeClosingNonemptyBraces": true,
    "javascript.format.insertSpaceAfterOpeningAndBeforeClosingNonemptyBrackets": true,
    "javascript.format.insertSpaceAfterOpeningAndBeforeClosingNonemptyParenthesis": true,
    "javascript.format.insertSpaceAfterOpeningAndBeforeClosingTemplateStringBraces": true,
    "typescript.format.insertSpaceAfterOpeningAndBeforeClosingNonemptyBraces": true,
    "typescript.format.insertSpaceAfterOpeningAndBeforeClosingNonemptyParenthesis": true,
    "typescript.format.insertSpaceAfterOpeningAndBeforeClosingNonemptyBrackets": true,
    "typescript.format.insertSpaceAfterOpeningAndBeforeClosingTemplateStringBraces": true,
    "typescript.format.insertSpaceAfterOpeningAndBeforeClosingJsxExpressionBraces": true,
    "javascript.format.insertSpaceAfterOpeningAndBeforeClosingJsxExpressionBraces": true,
    "typescript.format.semicolons": "insert",
    "typescript.preferences.quoteStyle": "single",
    "javascript.format.semicolons": "insert",
    "javascript.preferences.quoteStyle": "single",
    "javascript.preferences.jsxAttributeCompletionStyle": "none",
    "javascript.preferences.useAliasesForRenames": false,
    "typescript.preferences.jsxAttributeCompletionStyle": "none",
    "typescript.preferences.useAliasesForRenames": false,
    "github.copilot.enable": {
      "*": false,
      "plaintext": false,
      "markdown": true,
      "scminput": false
    },
    "dart.showInspectorNotificationsForWidgetErrors": false,
    "editor.guides.bracketPairs": "active",
    "editor.guides.bracketPairsHorizontal": true,
    "files.associations": {
      "*.css": "tailwindcss"
    }
}
```

[Instalaciones necesarias y opcionales](https://gist.github.com/Klerith/75e5bc8c3168d0896e68828829647bdf)

### 1.4 Descarga e instalación de proyecto inicial

[Admin Dashboard - Tailwind](https://github.com/Klerith/zustand-mini-curso)

```bash
git clone git@github.com:Klerith/zustand-mini-curso.git
mv zustand-mini-curso zustand-dashboard

cd zustand-dashboard
npm i
npm run dev
```

Activar parpadeo:

- React Developed Tools
- Components
- ⚙️
- [x] Highlight updates when components render.

### 1.5 ¡Únete a Nuestra Comunidad de DevTalles en Discord!

Te invitamos a que formes parte de nuestra comunidad de DevTalles en Discord, un espacio donde tendrás la oportunidad de establecer conexiones con otros estudiantes, compartir y colaborar.

¿Cómo unirse?

- Haz clic en el siguiente enlace de invitación: Comunidad DevTalles
- Una vez dentro, cuéntanos un poco de ti en el canal de bienvenida(#presentate).

Estamos entusiasmados de tener nuevos miembros y crecer juntos como comunidad.

¡Esperamos verte pronto en Discord!

Atentamente,

El equipo de DevTalles

## 2. Bases de Zustand

### 2.1 Introducción a la sección

### 2.2 Temas puntuales de la sección

En esta sección tendremos las bases de Zustand, como son:

- Instalaciones
- Configuraciones
- Propiedades computadas
- Objetos anidados
- Actualizaciones de estado
- Configuraciones con TypeScript
- useShallow

Esta sección nos dejará las bases para poder entender el objetivo de este gestor de estado tan poderoso.

### 2.3 Continuación de proyecto

Estructura del proyecto:

```bash
.
├── .eslintrc.cjs
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
├── postcss.config.js
├── public
│   ├── screenshot.png
│   └── vite.svg
├── README.md
├── src
│   ├── assets
│   │   └── react.svg
│   ├── components
│   │   ├── index.ts
│   │   ├── jira
│   │   │   └── JiraTasks.tsx
│   │   └── shared
│   │       ├── cards
│   │       │   └── WhiteCard.tsx
│   │       └── sidemenu
│   │           ├── SideMenu.css
│   │           ├── SideMenuItem.tsx
│   │           └── SideMenu.tsx
│   ├── index.css
│   ├── layouts
│   │   ├── AuthLayout.tsx
│   │   ├── DashboardLayout.tsx
│   │   └── index.ts
│   ├── main.tsx
│   ├── pages
│   │   ├── 01-basic
│   │   │   ├── BearPage.tsx
│   │   │   └── PersonPage.tsx
│   │   ├── 02-objects
│   │   │   └── JiraPage.tsx
│   │   ├── 03-slices
│   │   │   └── WeddingInvitationPage.tsx
│   │   ├── auth
│   │   │   └── LoginPage.tsx
│   │   ├── dashboard
│   │   │   └── DashboardPage.tsx
│   │   └── index.ts
│   ├── Root.tsx
│   ├── router
│   │   └── router.tsx
│   └── vite-env.d.ts
├── tailwind.config.js
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

### 2.4 Nuestro primer store

Estructura:

```bash
.
├── .eslintrc.cjs
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
├── postcss.config.js
├── public
│   ├── screenshot.png
│   └── vite.svg
├── README.md
├── src
│   ├── assets
│   │   └── react.svg
│   ├── components
│   │   ├── index.ts
│   │   ├── jira
│   │   │   └── JiraTasks.tsx
│   │   └── shared
│   │       ├── cards
│   │       │   └── WhiteCard.tsx
│   │       └── sidemenu
│   │           ├── SideMenu.css
│   │           ├── SideMenuItem.tsx
│   │           └── SideMenu.tsx
│   ├── index.css
│   ├── layouts
│   │   ├── AuthLayout.tsx
│   │   ├── DashboardLayout.tsx
│   │   └── index.ts
│   ├── main.tsx
│   ├── pages
│   │   ├── 01-basic
│   │   │   ├── BearPage.tsx
│   │   │   └── PersonPage.tsx
│   │   ├── 02-objects
│   │   │   └── JiraPage.tsx
│   │   ├── 03-slices
│   │   │   └── WeddingInvitationPage.tsx
│   │   ├── auth
│   │   │   └── LoginPage.tsx
│   │   ├── dashboard
│   │   │   └── DashboardPage.tsx
│   │   └── index.ts
│   ├── Root.tsx
│   ├── router
│   │   └── router.tsx
│   ├── stores 👈🏼👀👇🏻
│   │   └── bears
│   │       └── bears.store.ts
│   └── vite-env.d.ts
├── tailwind.config.js
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

```bash
npm install zustand
```

`./src/stores/bears.store.ts`

```ts
import { create } from 'zustand';

interface BearState {
  blackBears: number;
  polarBears: number;
  pandaBears: number;

  increaseBlackBears: (by: number) => void;
}

export const useBearStore = create<BearState>()((set) => ({
  blackBears: 10,
  polarBears: 5,
  pandaBears: 1,

  increaseBlackBears: (by: number) =>
    set((state) => ({ blackBears: state.blackBears + by })),
}));
```

#### Interfaz: interface

En JavaScript no existen "tipos" realmente.  
Pero TypeScript te deja **describir la forma de un objeto**.

Ejemplo:  
Sin interfaz:

```ts
const persona = {
  nombre: "Henry",
  edad: 25,
};
```

Ahora con una interfaz:

```ts
interface Persona {
  nombre: string;
  edad: number;
}
```

Esto NO crea código.  
LE DICE A TYPESCRIPT:

> Cada objeto tipo `Persona` debe tener un `nombre: string` y `edad: number`.

Ejemplo usando la interfaz:

```ts
const p1: Persona = {
  nombre: "Henry",
  edad: 25,
};
```

Si escribes mal:

```ts
const p2: Persona = {
  nombre: "Henry",
  edad: "veinticinco", // ❌ error
};
```

TS te avisa que la forma está mal.

#### Genericos - Generic

Los genéricos son como **variables para tipos**.

Una función normal usa variables para valores:

```ts
function identidad(valor) {
  return valor;
}
```

Ahora imagina una función que recibe un “tipo variable”.

Así:

```ts
// Esto equivale a create en zustand
function identidad<T>(valor: T): T {
  return valor;
}
```

`<T>` significa:

> "T es un tipo que me dirá el usuario".

Ejemplo:

```ts
const numero = identidad<number>(3);   // T = number
const texto = identidad<string>("hola"); // T = string
```

TypeScript usa genéricos para “adaptarse” según el tipo que le pases.

#### En Zustand: `create<BearState>()()`?

Aquí se juntan las dos cosas:

- **interface** = describe la forma del estado  
- **genérico `<T>`** = le dice a Zustand qué forma tendrá el estado

Zustand necesita saber **qué estructura tendrá tu store**.  
Así que tú se la dices usando generics:

```ts
create<BearState>()()
```

Eso significa:

> “Oye Zustand, este store tendrá la forma de la interfaz BearState.”

**NO es JavaScript.  
NO es un método especial.  
NO es una función.  
Es solo TypeScript diciéndole a Zustand el tipo del store.**

Luego llamas a esa función usando un patrón conocido como IIFE:

```ts
// create()()
create<BearState>()((set) => ({ ... }))
```

#### Ejemplos

Ejemplo 1: genéricos sin interfaces

```ts
function caja<T>(valor: T) {
  return valor;
}

const n = caja<number>(5);   // T = number
const s = caja<string>("hola"); // T = string
```

Ejemplo 2: interfaz + genérico (más parecido a Zustand)

Interfaz del objeto:

```ts
interface Configuracion {
  url: string;
  puerto: number;
}
```

Función genérica:

```ts
// Esto equivale a create en zustand
function crearServidor<T>(config: T) {
  return config;
}
```

Pasas el tipo:

```ts
const servidor = crearServidor<Configuracion>({
  url: "localhost",
  puerto: 3000,
});
```

Aquí usamos **crearServidor()**, parecido a **create()**.

#### Finalmente: Zustand

Tu interfaz:

```ts
interface BearState {
  blackBears: number;
  polarBears: number;
  pandaBears: number;
  increaseBlackBears: (by: number) => void;
}
```

Zustand necesita saber que el estado tiene esa forma.

Entonces usas el genérico:

```ts
export const useBearStore = create<BearState>()(
  (set) => ({ 
    blackBears: 10,
    polarBears: 5,
    pandaBears: 1,
    increaseBlackBears: (by) => set((state) => ({ blackBears: state.blackBears + by })),
  })
);
```

Si olvidas una propiedad → error  
Si pones un tipo incorrecto → error  
Si escribes mal un método → error

El genérico `<BearState>` hace que el store esté 100% tipado.

#### IIFE o Currying? IIFE

Vamos a explicar **por qué existe `create<BearState>()((set) => {...})`**  
y por qué NO es simplemente `create<BearState>((set) => {...})`.

> Lo entenderás al 100% cuando veas que **create devuelve otra función**.  
Ese es el truco.

Pensaba que debería ser:

```ts
create<BearState>((set) => ({
  …
}))
```

Porque eso sería:

- `<BearState>` = tipeo
- `()` = paso los argumentos
    

Y eso es **lógico**.

Peeero Zustand usa una forma más avanzada:  
**create es una función _que devuelve otra función_.**

Ahora, así funciona `create` de Zustand por dentro (simplificado)

Zustand tiene dos versiones internas:

1. **Versión simple**: `create((set) => { ... })`
2. **Versión tipada**: `create<BearState>()((set) => { ... })`

¿Por qué existe esa segunda forma?

Porque Zustand usa un **pattern** que se llama _currying_.

Currying:

Es simplemente cuando una función **devuelve otra función**.

Ejemplo sencillo:

```ts
function saludar(primeraParte) {
  return function (segundaParte) {
    console.log(primeraParte + " " + segundaParte);
  }
}

saludar("Hola")("Ale");
```

Aquí pasa esto:

- `saludar("Hola")` → devuelve una función
- luego llamas esa función → `("Ale")`

Salida: `"Hola Ale"`

Esto es **2 llamadas seguidas**:

```ts
saludar("Hola")("Ale")
```

Ahora mira Zustand de la misma forma

Zustand hace ALGO COMO ESTO por dentro:

```ts
function create<T>() {
  return function (initializer) {
    // crea el store con los tipos T
  }
}
```

Es exactamente el mismo patrón de antes.

Visualización práctica

Cuando haces:

```ts
create<BearState>()
```

Estás llamando la **primera función**, que devuelve otra.

Luego llamas la segunda:

```ts
((set) => ({ ... }))
```

Es decir:

```ts
create<BearState>()   → devuelve función
create<BearState>()(...) → llamas esa función
```

Comparación lado a lado

✔ Lo que pensaba que era (una sola función):

```ts
create<BearState>((set) => ({}))
```

❌ Pero en Zustand no es así.

En Zustand es una función que devuelve otra:

```ts
create<BearState>()((set) => ({}))
```

Es como:

```ts
const funcionGenerica = create<BearState>();
const store = funcionGenerica((set) => ({ ... }));
```

Pero escrito directo en una sola línea:

```ts
create<BearState>()((set) => ({ ... }));
```

¿POR QUÉ Zustand hizo esto así? 🤔

Por temas avanzados de:

- inference de tipos  
- API unificada
- soportar diferentes estilos de uso
- permitir pasar middlewares

También se usa mucho para permitir cosas como:

```ts
create<BearState>()(
  persist(
    (set) => ({ ... }),
    { name: "store-name" }
  )
)
```

[https://docs.pmnd.rs/zustand/getting-started/introduction](https://docs.pmnd.rs/zustand/getting-started/introduction)

### 2.5 Consumir nuestro store

`./src/stores/bears/bears.store.ts`

```ts
import { create } from 'zustand';

interface BearState {
  blackBears: number;
  polarBears: number;
  pandaBears: number;

  increaseBlackBears: (by: number) => void;
  increasePolarBears: (by: number) => void;
  increasePandaBears: (by: number) => void;
}

export const useBearStore = create<BearState>()((set) => ({
  blackBears: 10,
  polarBears: 5,
  pandaBears: 1,

  increaseBlackBears: (by: number) =>
    set((state) => ({ blackBears: state.blackBears + by })),
  increasePolarBears: (by: number) =>
    set((state) => ({ polarBears: state.polarBears + by })),
  increasePandaBears: (by: number) =>
    set((state) => ({ pandaBears: state.pandaBears + by })),
}));
```

`./src/pages/01-basic/BearPage.tsx`

```tsx
import { WhiteCard } from '../../components';
import { useBearStore } from '../../stores/bears/bears.store';

export const BearPage = () => {
  return (
    <>
      <h1>Contador de Osos</h1>
      <p>Manejo de estado simple de Zustand</p>
      <hr />

      <div className='grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-2'>
        <BlackBears />
        <PolarBears />
        <PandaBears />
      </div>
    </>
  );
};

export const BlackBears = () => {
  const blackBears = useBearStore(
    (state) => state.blackBears
  );
  const increaseBlackBears = useBearStore(
    (state) => state.increaseBlackBears
  );
  const isDisabled = blackBears === 0;

  return (
    <WhiteCard centered>
      <h2>Osos Negros</h2>

      <div className='flex flex-col md:flex-row'>
        <button onClick={() => increaseBlackBears(+1)}>
          +1
        </button>
        <span className='text-3xl mx-2 lg:mx-10'>
          {blackBears}
        </span>
        <button
          onClick={() => increaseBlackBears(-1)}
          disabled={isDisabled}
        >
          -1
        </button>
      </div>
    </WhiteCard>
  );
};

export const PolarBears = () => {
  const polarBears = useBearStore(
    (state) => state.polarBears
  );
  const increasePolarBears = useBearStore(
    (state) => state.increasePolarBears
  );
  const isDisabled = polarBears === 0;

  return (
    <WhiteCard centered>
      <h2>Osos Polares</h2>

      <div className='flex flex-col md:flex-row'>
        <button onClick={() => increasePolarBears(+1)}>
          +1
        </button>
        <span className='text-3xl mx-2 lg:mx-10'>
          {polarBears}
        </span>
        <button
          onClick={() => increasePolarBears(-1)}
          disabled={isDisabled}
        >
          -1
        </button>
      </div>
    </WhiteCard>
  );
};

export const PandaBears = () => {
  const pandaBears = useBearStore(
    (state) => state.pandaBears
  );
  const increasePandaBears = useBearStore(
    (state) => state.increasePandaBears
  );
  const isDisabled = pandaBears === 0;

  // const { pandaBears, increasePandaBears } = useBearStore(
  //   (state) => state
  // );

  return (
    <WhiteCard centered>
      <h2>Osos Pandas</h2>

      <div className='flex flex-col md:flex-row'>
        <button onClick={() => increasePandaBears(+1)}>
          +1
        </button>
        <span className='text-3xl mx-2 lg:mx-10'>
          {pandaBears}
        </span>
        <button
          onClick={() => increasePandaBears(-1)}
          disabled={isDisabled}
        >
          -1
        </button>
      </div>
    </WhiteCard>
  );
};
```

### 2.6 Resolución de la tarea

`./src/pages/01-basic/BearPage.tsx`

```ts
// No se recomienda desestructurar
const { pandaBears, increasePandaBears } = useBearStore(
    (state) => state
  );
```

La solución es la misma mostrada en la clase anterior.

### 2.7 Objetos anidados en el store

`./src/stores/bears/bears.store.ts`

```ts
import { create } from 'zustand';

interface Bear { 👈🏼👀
  id: number;
  name: string;
}

interface BearState {
  blackBears: number;
  polarBears: number;
  pandaBears: number;

  // Array de objetos [ {}, {} ]
  bears: Bear[]; 👈🏼👀

  increaseBlackBears: (by: number) => void;
  increasePolarBears: (by: number) => void;
  increasePandaBears: (by: number) => void;

  doNothing: () => void; 👈🏼👀👇🏻
}

export const useBearStore = create<BearState>()((set) => ({
  blackBears: 10,
  polarBears: 5,
  pandaBears: 1,

  bears: [{ id: 1, name: 'Oso #1' }], 👈🏼👀👇🏻

  increaseBlackBears: (by: number) =>
    set((state) => ({ blackBears: state.blackBears + by })),
  increasePolarBears: (by: number) =>
    set((state) => ({ polarBears: state.polarBears + by })),
  increasePandaBears: (by: number) =>
    set((state) => ({ pandaBears: state.pandaBears + by })),

  doNothing: () => 👈🏼👀👇🏻
    set((state) => ({ bears: [...state.bears] })),
}));
```

`./src/pages/01-basic/BearPage.tsx`

```ts
import { useShallow } from 'zustand/shallow'; 👈🏼👀
import { WhiteCard } from '../../components';
import { useBearStore } from '../../stores/bears/bears.store';

export const BearPage = () => {
  return (
    <>
      <h1>Contador de Osos</h1>
      <p>Manejo de estado simple de Zustand</p>
      <hr />

      <div className='grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-2'>
        <BlackBears />
        <PolarBears />
        <PandaBears />

        <BearsDisplay /> 👈🏼👀 
      </div>
    </>
  );
};

export const BlackBears = () => {
};

export const PolarBears = () => {
};

export const PandaBears = () => {
};

export const BearsDisplay = () => {
  const bears = useBearStore( 👈🏼👀👇🏻
    useShallow((state) => state.bears)
  );
  const doNothing = useBearStore((state) => state.doNothing);

  return (
    <WhiteCard>
      <h1>Osos</h1>
      <button onClick={doNothing}>Do Nothing</button>

      <pre>{JSON.stringify(bears, null, 2)}</pre>
    </WhiteCard>
  );
};
```

[use-shallow](https://zustand.docs.pmnd.rs/hooks/use-shallow)

### 2.8 Métodos con objetos anidados

`./src/stores/bears/bears.store.ts`

```ts
import { create } from 'zustand';

interface Bear {
  id: number;
  name: string;
}

interface BearState {
  blackBears: number;
  polarBears: number;
  pandaBears: number;

  bears: Bear[];

  increaseBlackBears: (by: number) => void;
  increasePolarBears: (by: number) => void;
  increasePandaBears: (by: number) => void;

  doNothing: () => void;
  addBear: () => void; 👈🏼👀
  clearBears: () => void; 👈🏼👀
}

export const useBearStore = create<BearState>()((set) => ({
  blackBears: 10,
  polarBears: 5,
  pandaBears: 1,

  bears: [{ id: 1, name: 'Oso #1' }],

  increaseBlackBears: (by: number) =>
    set((state) => ({ blackBears: state.blackBears + by })),
  increasePolarBears: (by: number) =>
    set((state) => ({ polarBears: state.polarBears + by })),
  increasePandaBears: (by: number) =>
    set((state) => ({ pandaBears: state.pandaBears + by })),

  doNothing: () =>
    set((state) => ({ bears: [...state.bears] })),
  addBear: () => 👈🏼👀
    set((state) => ({
      bears: [
        ...state.bears,
        {
          id: state.bears.length + 1,
          name: `Oso #${state.bears.length + 1}`,
        },
      ],
    })),
  clearBears: () => set({ bears: [] }), 👈🏼👀
}));
```

`./src/pages/01-basic/BearPage.tsx`

```ts
import { useShallow } from 'zustand/shallow';
import { WhiteCard } from '../../components';
import { useBearStore } from '../../stores/bears/bears.store';

export const BearPage = () => {
  return (
    <>
      <h1>Contador de Osos</h1>
      <p>Manejo de estado simple de Zustand</p>
      <hr />

      <div className='grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-2'>
        <BlackBears />
        <PolarBears />
        <PandaBears />

        <BearsDisplay /> 
      </div>
    </>
  );
};

export const BlackBears = () => {
};

export const PolarBears = () => {
};

export const PandaBears = () => {
};

export const BearsDisplay = () => {
  const bears = useBearStore(
    useShallow((state) => state.bears)
  );
  const doNothing = useBearStore((state) => state.doNothing);
  const addBear = useBearStore((state) => state.addBear); 👈🏼👀
  const clearBears = useBearStore( 👈🏼👀
    (state) => state.clearBears
  );

  return (
    <WhiteCard>
      <h1>Osos</h1>
      <button onClick={doNothing}>Do Nothing</button>
      <button className='mt-2' onClick={addBear}> 👈🏼👀
        Add bear
      </button>
      <button className='mt-2' onClick={clearBears}> 👈🏼👀
        Delete bear
      </button>

      <pre>{JSON.stringify(bears, null, 2)}</pre>
    </WhiteCard>
  );
};
```

### 2.9 Propiedades computadas

`./src/stores/bears/bears.store.ts`

```ts
import { create } from 'zustand';

interface Bear {
  id: number;
  name: string;
}

interface BearState {
  blackBears: number;
  polarBears: number;
  pandaBears: number;

  bears: Bear[];

  computed: { // 👈🏼👀👇🏻
    totalBears: number;
  };

  increaseBlackBears: (by: number) => void;
  increasePolarBears: (by: number) => void;
  increasePandaBears: (by: number) => void;

  doNothing: () => void;
  addBear: () => void;
  clearBears: () => void;
}

export const useBearStore = create<BearState>()(
  (set, get) => ({
    blackBears: 10,
    polarBears: 5,
    pandaBears: 1,

    bears: [{ id: 1, name: 'Oso #1' }],

    computed: { // 👈🏼👀👇🏻
      get totalBears(): number {
        return (
          get().blackBears +
          get().polarBears +
          get().pandaBears +
          get().bears.length
        );
      },
    },

    increaseBlackBears: (by: number) =>
      set((state) => ({ blackBears: state.blackBears + by })),
    increasePolarBears: (by: number) =>
      set((state) => ({ polarBears: state.polarBears + by })),
    increasePandaBears: (by: number) =>
      set((state) => ({ pandaBears: state.pandaBears + by })),

    doNothing: () =>
      set((state) => ({ bears: [...state.bears] })),
    addBear: () =>
      set((state) => ({
        bears: [
          ...state.bears,
          {
            id: state.bears.length + 1,
            name: `Oso #${state.bears.length + 1}`,
          },
        ],
      })),
    clearBears: () => set({ bears: [] }),
  })
);
```

`./src/pages/dashboard/DashboardPage.tsx`

```ts
import {
  IoAccessibilityOutline,
  IoHeartOutline,
  IoListOutline,
  IoLockClosedOutline,
  IoPawOutline,
} from 'react-icons/io5';
import { WhiteCard } from '../../components';
import { useBearStore } from '../../stores/bears/bears.store';

export const Dashboard = () => {
  const totalBears = useBearStore( 👈🏼👀👇🏻
    (state) => state.computed.totalBears
  );

  return (
    <>
      <h1>Dashboard</h1>
      <p>Información colectiva de varios stores de Zustand</p>
      <hr />

      <div className='grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-4'>
        <WhiteCard centered>
          <IoPawOutline
            size={50}
            className='text-indigo-600'
          />
          <h2>Osos</h2> 👈🏼👀👇🏻
          <p>{totalBears}</p>
        </WhiteCard>

        <WhiteCard centered>
          <IoAccessibilityOutline
            size={50}
            className='text-indigo-600'
          />
          <h2>Persona</h2>
          <p>Información</p>
        </WhiteCard>

        <WhiteCard centered>
          <IoListOutline
            size={50}
            className='text-indigo-600'
          />
          <h2>Tareas</h2>
          <p>Información</p>
        </WhiteCard>

        <WhiteCard centered>
          <IoHeartOutline
            size={50}
            className='text-indigo-600'
          />
          <h2>Boda</h2>
          <p>Información</p>
        </WhiteCard>

        <WhiteCard centered>
          <IoLockClosedOutline
            size={50}
            className='text-indigo-600'
          />
          <h2>Auth</h2>
          <p>Información</p>
        </WhiteCard>
      </div>
    </>
  );
};
```

#### Propiedad computada

⚠️ **Importante:**  
En **Zustand NO existe oficialmente algo llamado `computed`** como en Vue.

- `computed` **no es una feature de Zustand**,  
- es **una convención creada por el instructor** usando **getters de JavaScript**.

Es decir:

```ts
computed: {
  get totalBears() {
    ...
  }
}
```

Eso es **100% JavaScript**, no Zustand.

Ejemplo simple en JS puro:

```ts
const obj = {
  a: 2,
  b: 3,

  get suma() {
    return this.a + this.b;
  },
};

console.log(obj.suma); // 5
```

🔹 `suma` **no es un valor guardado**  
🔹 es una **función disfrazada de propiedad**  
🔹 se ejecuta **cada vez que accedes a ella**

No se llama así:

```ts
obj.suma(); ❌
```

Se usa así:

```ts
obj.suma; ✅
```

#### Qué está pasando en el store de Zustand

Estructura clave

```ts
(set, get) => ({
  blackBears: 10,
  polarBears: 5,
  pandaBears: 1,

  bears: [{ id: 1, name: 'Oso #1' }],

  computed: {
    get totalBears() {
      return (
        get().blackBears +
        get().polarBears +
        get().pandaBears +
        get().bears.length
      );
    },
  },
});
```

Zustand te da dos funciones:

|Función |Qué hace             |
|-------|---------------------|
|`set` |Modifica el estado   |
|`get` |Lee el estado actual |

Ejemplo:

```ts
get().blackBears
```

- Lee el valor **actual** del store  
- No importa desde qué componente lo llames

#### Cómo funciona `totalBears`

Cuando React ejecuta esto:

```ts
const totalBears = useBearStore(
  (state) => state.computed.totalBears
);
```

Pasa lo siguiente:

1. Zustand devuelve el `state`
    
2. Accedes a `state.computed.totalBears`
    
3. ⚡ **JS ejecuta el getter**
    
4. El getter llama a `get()`
    
5. `get()` lee el estado más reciente
    
6. Se calcula la suma
    
7. Se devuelve el número
    

- **No hay estado duplicado**  
- **No hay sincronización manual**  
- Siempre es el valor correcto

#### ¿Esto hace que el componente se re-renderice?

Sí, **pero solo cuando cambia algo que el selector usa**.

Este selector:

```ts
(state) => state.computed.totalBears
```

Depende indirectamente de:

- `blackBears`
- `polarBears`
- `pandaBears`
- `bears.length`

Si cualquiera cambia →  
Zustand vuelve a evaluar el selector →  
React se re-renderiza.

#### `computed` como objeto

Es **solo organización**.

Podrías escribir esto:

```ts
get totalBears() {
  ...
}
```

Pero el instructor prefirió:

```ts
computed: {
  get totalBears() {
    ...
  }
}
```

Ventajas:

✔ Agrupa valores derivados  
✔ Más legible  
✔ Escalable si hay muchos cálculos

Ejemplo futuro:

```ts
computed: {
  get totalBears() { ... },
  get hasBears() { ... },
  get bearsSummary() { ... },
}
```

Entonces

> **`computed.totalBears` NO es un estado**
> 
> **Es una función que se ejecuta cada vez que la lees**

Pero **se ve como una propiedad**, gracias al `get`.

- `computed` → convención, no Zustand
    
- `get totalBears()` → getter de JS
    
- `get()` → lee el estado actual de Zustand
    
- No se guarda nada, se calcula al vuelo
    
- React se re-renderiza cuando cambian dependencias

### 2.10 Código fuente de la sección

Código fuente de la sección por si lo llegan a necesitar.

[Github - Fin sección 2 - Bases](https://github.com/Klerith/zustand-mini-curso/tree/fin-seccion-02)

## 3. Middlewares de Zustand

### 3.1 Introducción a la sección

### 3.2 Temas puntuales de la sección

En esta sección vamos a trabajar con middlewares o funciones adicionales que expanden el comportamiento por defecto de Zustand. Puntualmente veremos:

- Persist Middlewares
- createJSONStore
- Guardar automáticamente en session storage
- Guardar automáticamente en Firebase
- Crear un storage personalizado
- Diferentes interfaces de Zustand
- Custom Middleware
- Redux DevTools y acciones

### 3.3 Continuación de la sección

### 3.4 Crear un segundo store

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.5

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.6

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.7

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.8

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.9

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.10

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.11

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.12

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.13

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

### 3.14

```ts
```

```ts
```

```ts
```

👈🏼👀
👈🏼👀👇🏻

```
```


```
```
⚙️