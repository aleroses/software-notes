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

Estructura:

```ts
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
│   ├── stores
│   │   ├── bears
│   │   │   └── bears.store.ts
│   │   └── person 👈🏼👀👇🏻
│   │       └── person.store.ts
│   └── vite-env.d.ts
├── tailwind.config.js
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

`./src/stores/person/person.store.ts`

```ts
import { create } from 'zustand';

interface PersonState {
  firstName: string;
  lastName: string;

  // setFistName: (value: string) => void;
  // setLastName: (value: string) => void;
}

interface Actions {
  setFirstName: (value: string) => void;
  setLastName: (value: string) => void;
}

export const usePersonStore = create<PersonState & Actions>()(
  (set) => ({
    firstName: '',
    lastName: '',
    setFirstName: (value: string) =>
      set((state) => ({ firstName: value })),
    setLastName: (value: string) =>
      set((state) => ({ lastName: value })),
  })
);
```

`./src/pages/01-basic/PersonPage.tsx`

```ts
import { WhiteCard } from '../../components';
import { usePersonStore } from '../../stores/person/person.store';

export const PersonPage = () => {
  const firstName = usePersonStore(
    (state) => state.firstName
  );
  const lastName = usePersonStore((state) => state.lastName);

  const setFirstName = usePersonStore(
    (state) => state.setFirstName
  );
  const setLastName = usePersonStore(
    (state) => state.setLastName
  );

  return (
    <>
      <h1>Persona</h1>
      <p>
        Información que se compartirá a otro store, Session
        Storage y Firebase
      </p>
      <hr />

      <WhiteCard className='flex items-center justify-center p-12'>
        <div className='mx-auto w-full max-w-[550px]'>
          <form>
            <div className='-mx-3 flex flex-wrap'>
              <div className='w-full px-3 sm:w-1/2'>
                <div className='mb-5'>
                  <label className='mb-3 block text-base font-medium text-[#07074D]'>
                    Nombre
                  </label>
                  <input
                    type='text'
                    name='firstName'
                    id='firstName'
                    placeholder='Primer Nombre'
                    value={firstName}
                    onChange={(e) =>
                      setFirstName(e.target.value)
                    }
                  />
                </div>
              </div>
              <div className='w-full px-3 sm:w-1/2'>
                <div className='mb-5'>
                  <label className='mb-3 block text-base font-medium text-[#07074D]'>
                    Apellido
                  </label>
                  <input
                    type='text'
                    name='lastName'
                    id='lastName'
                    placeholder='Apellido'
                    value={lastName}
                    onChange={(e) =>
                      setLastName(e.target.value)
                    }
                  />
                </div>
              </div>
            </div>

            <pre className='bg-gray-200 p-5 rounded-[20px]'>
              {JSON.stringify(
                {
                  firstName,
                  lastName,
                },
                null,
                2
              )}
            </pre>
          </form>
        </div>
      </WhiteCard>
    </>
  );
};
```

### 3.5 Persist Middleware

`./src/stores/person/person.store.ts`

```ts
import { create } from 'zustand';
import { persist } from 'zustand/middleware'; 👈🏼👀

interface PersonState {
  firstName: string;
  lastName: string;

  // setFistName: (value: string) => void;
  // setLastName: (value: string) => void;
}

interface Actions {
  setFirstName: (value: string) => void;
  setLastName: (value: string) => void;
}

export const usePersonStore = create<PersonState & Actions>()(
  persist( 👈🏼👀👇🏻
    (set) => ({
      firstName: '',
      lastName: '',
      setFirstName: (value: string) =>
        set((state) => ({ firstName: value })),
      setLastName: (value: string) =>
        set((state) => ({ lastName: value })),
    }),
    { name: 'person-storage' }
  )
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
import { usePersonStore } from '../../stores/person/person.store';

export const Dashboard = () => {
  const totalBears = useBearStore(
    (state) => state.computed.totalBears
  );
  const firstName = usePersonStore(
    (state) => state.firstName
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
          <h2>Osos</h2>
          <p>{totalBears}</p>
        </WhiteCard>

        <WhiteCard centered>
          <IoAccessibilityOutline
            size={50}
            className='text-indigo-600'
          />
          <h2>Persona</h2>
          <p>{firstName}</p> 👈🏼👀
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

El middleware Persist **le permite almacenar su estado de Zustand en un almacenamiento** (por ejemplo, localStorage , AsyncStorage , IndexedDB , etc.), persistiendo así sus datos. Tenga en cuenta que este middleware admite tanto almacenamientos síncronos, como localStorage , como asíncronos, como AsyncStorage .

[Using middlewares](https://zustand.docs.pmnd.rs/guides/advanced-typescript#using-middlewares)

### 3.6 StateCreator Interface

`./src/stores/person/person.store.ts`

```ts
import { create, type StateCreator } from 'zustand';
import { persist } from 'zustand/middleware';

interface PersonState {
  firstName: string;
  lastName: string;

  // setFistName: (value: string) => void;
  // setLastName: (value: string) => void;
}

interface Actions {
  setFirstName: (value: string) => void;
  setLastName: (value: string) => void;
}

const storeAPI: StateCreator<PersonState & Actions> = ( 👈🏼👀👇🏻
  set
) => ({
  firstName: '',
  lastName: '',
  setFirstName: (value: string) =>
    set((state) => ({ firstName: value })),
  setLastName: (value: string) =>
    set((state) => ({ lastName: value })),
});

export const usePersonStore = create<PersonState & Actions>()(
  persist(storeAPI, { name: 'person-storage' }) 👈🏼👀
);
```

`StateCreator` en Zustand es una función que defines para **crear tu tienda (store)**, recibiendo `set`, `get`, y `store` como argumentos para manipular el estado, obtenerlo y acceder a funciones del store, respectivamente, permitiéndote devolver un objeto con tus estados y acciones de forma organizada, ideal para usar con TypeScript para tipado fuerte y middlewares como `devtools` o `persist`. 

1. Conceptos Clave

- **`create<StateCreator>(...)`**: La función principal de Zustand para crear tiendas. La `StateCreator` es la función que le pasas a `create`.
- **Argumentos de `StateCreator`**:
    - `set`: Para actualizar el estado (inmutablemente).
    - `get`: Para leer el estado actual.
    - `store`: El objeto completo del store (útil para resets o middlewares).
- **Inmutabilidad**: Al actualizar, siempre usa el operador spread (`...`) para objetos o arrays, como en `set(state => ({ ...state, count: state.count + 1 }))`. 

2. Ejemplo Básico (Sin TypeScript)

```js
import { create } from 'zustand';

const useCounterStore = create((set, get) => ({
  count: 0, // Estado inicial
  increment: () => set(state => ({ count: state.count + 1 })), // Acción
  decrement: () => set(state => ({ count: state.count - 1 })), // Acción
  // Puedes usar 'get' para leer el estado dentro de una acción
  doubleCount: () => get().count * 2
}));

// Uso en un componente React:
function Counter() {
  const { count, increment, decrement } = useCounterStore();
  return (
    <div>
      <span>{count}</span>
      <button onClick={increment}>+</button>
      <button onClick={decrement}>-</button>
    </div>
  );
}
```

3. Con TypeScript y Middlewares (Forma Recomendada)

```js
import { create } from 'zustand';
import { devtools, persist } from 'zustand/middleware'; // Para devtools y persistencia

// 1. Define el tipo de tu estado y acciones
interface CounterState {
  count: number;
  increment: () => void;
  decrement: () => void;
}

interface CounterActions {
  increment: () => void;
  decrement: () => void;
}

// 2. Crea la StateCreator con tipos y middlewares
const useCounterStore = create<CounterState & CounterActions>()(
  persist( // Middleware de persistencia
    devtools( // Middleware de devtools
      (set, get) => ({ // Tu StateCreator
        count: 0,
        increment: () => set(state => ({ count: state.count + 1 })),
        decrement: () => set(state => ({ count: state.count - 1 })),
      }),
      { name: 'counter-storage' } // Opciones para devtools
    ),
    { name: 'counter-storage' } // Opciones para persist
  )
);

// Uso es similar, pero con tipado completo
```

4. Patrones Avanzados

- **Slices**: Organiza estados y acciones grandes en objetos pequeños (slices) dentro de tu `StateCreator` para mejorar la legibilidad y el mantenimiento.
- **`create<State>(...)()`**: La doble llamada (currying) es la forma recomendada en Zustand para que TypeScript infiera correctamente los tipos de tu store. 

Resumiendo, `StateCreator` es la definición funcional de tu tienda, controlando cómo se crea, se actualiza y qué métodos expone, siendo clave para la estructura y el tipado en tus aplicaciones con Zustand.

En Zustand, un store normalmente se crea así:

```ts
create((set, get) => ({
  count: 0,
  increment: () => set({ count: 1 }),
}));
```

Ese `(set, get) => ({ ... })` **tiene un tipo**.  
Zustand ya lo definió y lo llamó **`StateCreator`**.

👉 `StateCreator` describe **la forma de la función que crea el estado**.

Ahora al importar:

```ts
import { create, type StateCreator } from 'zustand';
```

La palabra clave **`type`** significa:

> 📌 “Estoy importando esto **solo como tipo**, no como valor de JavaScript”.

Forma del `StateCreator`

Simplificado, es algo así:

```ts
type StateCreator<T> = (
  set: (fn: (state: T) => Partial<T>) => void,
  get: () => T,
  api: unknown
) => T;
```

O sea:

👉 **una función que recibe `set`, `get` y devuelve el estado**

Aplicándolo a nuestro código:

```ts
interface PersonState {
  firstName: string;
  lastName: string;
}

interface Actions {
  setFirstName: (value: string) => void;
  setLastName: (value: string) => void;
}
```

Tu store tendrá:

```ts
PersonState & Actions
```

Aquí está la clave

```ts
const storeAPI: StateCreator<PersonState & Actions> = (set) => ({
  firstName: '',
  lastName: '',
  setFirstName: (value) =>
    set(() => ({ firstName: value })),
  setLastName: (value) =>
    set(() => ({ lastName: value })),
});
```

Esto significa:

🧠 **storeAPI es una función que crea un estado del tipo  
`PersonState & Actions`**

TypeScript ahora puede:

- Verificar que `firstName` y `lastName` existan
- Verificar que `setFirstName` y `setLastName` existan
- Autocompletar correctamente
- Marcar errores si te equivocas

### 3.7 Custom Storage - SessionStorage

`./src/stores/person/person.store.ts`

```ts
import { create, type StateCreator } from 'zustand';
import {
  createJSONStorage, 👈🏼👀
  persist,
  StateStorage, 👈🏼👀
} from 'zustand/middleware';

interface PersonState {
  firstName: string;
  lastName: string;

  // setFistName: (value: string) => void;
  // setLastName: (value: string) => void;
}

interface Actions {
  setFirstName: (value: string) => void;
  setLastName: (value: string) => void;
}

const storeAPI: StateCreator<PersonState & Actions> = (
  set
) => ({
  firstName: 'Ale',
  lastName: 'Ghost',
  setFirstName: (value: string) =>
    set((state) => ({ firstName: value })),
  setLastName: (value: string) =>
    set((state) => ({ lastName: value })),
});

// Usa Ctrl + . sobre sessionStorage para autocompletar
const sessionStorage: StateStorage = { 👈🏼👀👇🏻
  getItem: function (
    name: string
  ): string | null | Promise<string | null> {
    console.log('getItem', name);

    // throw new Error('Function not implemented.');
    return null;
  },
  setItem: function (name: string, value: string): unknown {
    console.log('setItem', { name, value });

    // throw new Error('Function not implemented.');
    return null;
  },
  removeItem: function (name: string): unknown {
    console.log('removeItem', name);

    // throw new Error('Function not implemented.');
    return null;
  },
};

export const usePersonStore = create<PersonState & Actions>()(
  persist(storeAPI, {
    name: 'person-storage', // el name que usa sessionStorage arriba
    storage: createJSONStorage(() => sessionStorage), 👈🏼👀
  })
);
```

📌 Nota: `const session|Storage:` Si haces `Ctrl + .` se despliegan algunas opciones, puedes elegir `Add missing properties` para autocompletar la implementación.

`sessionStorage` y `localStorage` son APIs de almacenamiento web que guardan datos en el navegador, siendo la principal diferencia su **duración**: `sessionStorage` guarda datos solo para la **sesión actual** (se borra al cerrar la pestaña/ventana), mientras que `localStorage` guarda datos de forma **permanente** hasta que se borren manualmente o por el usuario, persistiendo entre sesiones y reinicios del navegador, aunque ambos se borran al limpiar el historial o caché del navegador, y comparten métodos como `setItem()`, `getItem()`, `removeItem()` y `clear()`.

Comparativa detallada:

|Característica |`localStorage`                    |`sessionStorage`                                   |
|---------------|-----------------------------------|-----------------------------------------------------|
|**Duración**   |Permanente (hasta limpieza manual).|Temporal (solo para la sesión de la pestaña/ventana).|
|**Alcance**    |Mismo origen (dominio), compartido entre todas las pestañas/ventanas.|Mismo origen, pero cada pestaña/ventana tiene su propio almacenamiento.|
|**Eliminación**|Manualmente por el usuario o por código.|Automáticamente al cerrar la pestaña/navegador.|
|**Uso Típico** |Preferencias de usuario, temas, información que debe durar.|Datos de formulario temporal, estado de sesión, carrito de compras.|

Similitudes Clave:

- **Mismos métodos:** Ambos usan `setItem(clave, valor)`, `getItem(clave)`, `removeItem(clave)`, `clear()`, etc..
- **Almacenamiento por origen (Same-Origin Policy):** Los datos son privados para el dominio que los creó.
- **Almacenamiento de cadenas:** Solo guardan cadenas; objetos deben ser convertidos a JSON (`JSON.stringify()`) y luego parseados (`JSON.parse()`).
- **Límite de tamaño:** Ambos tienen un límite (ej. 5-10 MB), mayor en `localStorage`. 

En resumen, usa `sessionStorage` para datos efímeros de una sesión y `localStorage` para persistencia de datos a largo plazo.

### 3.8 Implementar SessionStorage

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
│   ├── stores
│   │   ├── bears
│   │   │   └── bears.store.ts
│   │   ├── person
│   │   │   └── person.store.ts
│   │   └── storages 👈🏼👀👇🏻
│   │       └── session-storage.storage.ts
│   └── vite-env.d.ts
├── tailwind.config.js
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

`./src/stores/person/person.store.ts`

```ts
import { create, type StateCreator } from 'zustand';
import { persist } from 'zustand/middleware';
import { customSessionStorage } from '../storages/session-storage.storage';

interface PersonState {
  firstName: string;
  lastName: string;

  // setFistName: (value: string) => void;
  // setLastName: (value: string) => void;
}

interface Actions {
  setFirstName: (value: string) => void;
  setLastName: (value: string) => void;
}

const storeAPI: StateCreator<PersonState & Actions> = (
  set
) => ({
  firstName: '',
  lastName: '',
  setFirstName: (value: string) =>
    set((state) => ({ firstName: value })),
  setLastName: (value: string) =>
    set((state) => ({ lastName: value })),
});

export const usePersonStore = create<PersonState & Actions>()(
  persist(storeAPI, {
    name: 'person-storage', // el name que usa sessionStorage arriba
    storage: customSessionStorage,
  })
);
```

`./src/stores/storages/session-storage.storage.ts`

```ts
import {
  createJSONStorage,
  StateStorage,
} from 'zustand/middleware';

const storageApi: StateStorage = {
  getItem: function (
    name: string
  ): string | null | Promise<string | null> {
    const data = sessionStorage.getItem(name);

    return data;
  },
  setItem: function (name: string, value: string): void {
    sessionStorage.setItem(name, value);
  },
  removeItem: function (name: string): unknown {
    console.log('removeItem', name);

    // throw new Error('Function not implemented.');
    return null;
  },
};

export const customSessionStorage = createJSONStorage(
  () => storageApi
);
```

Revisa en las DevTools `Storage` y busca `Session Storage` para ver la data guardada.

### 3.9 Aprovisionar base de datos en Firebase

Entra en [Firebase](https://firebase.google.com/?hl=es) y sigue estos pasos:

- Ver en Obsidian: [[react-hooks-mern#React (Hooks y MERN)#19.7 Configuración inicial de Firebase#Crear proyecto en Firebase]]
- Ver en GitHub: [19.7 Configuración inicial de Firebase](https://github.com/aleroses/software-notes/blob/master/DW/3-avanzado/1.react.js/devTalles/react-hooks-mern.md#197-configuracio%CC%81n-inicial-de-firebase)

Nombre del proyecto: `zustandStoragexd`

> En lugar de grabar en el localStorage debe grabar en la nube de Firebase.

- Compilation
- RealtimeDatabase
- Crear base de datos
- Ubicación: Por defecto
- Comenzar en Modo de prueba 
	- Modo bloqueado en la vida real

Realtime Database: Reglas

```ts
{
  "rules": {
    ".read": "now < 1769922000000",  // 2026-2-1
    ".write": "now < 1769922000000",  // 2026-2-1
  }
}
```

```ts
{
  "rules": {
    ".read": true,  // 2026-2-1
    ".write": true,  // 2026-2-1
  }
}
```

`Publicar`

Realtime Database: Datos

En datos podemos crear objetos con clave y valor.

`https://console.firebase.google.com/u/0/project/zustandstoragexd/database/zustandstoragexd-default-rtdb/data/~2F?hl=es-419` ➕

```ts
// Clave Valor 👀👇🏻
message: "Hi World"
```

Si haces clic en `message` aparece `/message` copia el enlace y abre Postman.

`Get: https://zustandstoragexd-default-rtdb.firebaseio.com/message.json`

En Firebase:

```ts
// Clave Valor 👀👇🏻
person ➕
  firstName: Ale
  lastName: Roses
```

En Postman al copiar el enlace y añadir `.json` debe aparecer el objeto creado en Firebase.
`Get: https://zustandstoragexd-default-rtdb.firebaseio.com/person.json`

### 3.10 Firebase CustomStorage

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
│   ├── stores
│   │   ├── bears
│   │   │   └── bears.store.ts
│   │   ├── person
│   │   │   └── person.store.ts
│   │   └── storages 👈🏼👀👇🏻
│   │       ├── firebase.storage.ts
│   │       └── session.storage.ts
│   └── vite-env.d.ts
├── tailwind.config.js
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

Compilación

- Realtime Database, entra y borra todo lo que se hizo antes.
- Authentication: Settings/Dominios Autorizados/localhost

Además, borra el session y local storage en el navegador.

`src/stores/storages/firebase.storage.ts`

```ts
import {
  createJSONStorage,
  StateStorage,
} from 'zustand/middleware';

// Firebase URL + /zustand
const firebaseUrl =
  'https://zustandstoragexd-default-rtdb.firebaseio.com/zustand';

const storageApi: StateStorage = {
  getItem: async function (
    name: string
  ): Promise<string | null> {
    try {
      const data = await fetch(
        `${firebaseUrl}/${name}.json`
      ).then((res) => res.json());
      // const data = await response.json();

      console.log(data);

      return JSON.stringify(data);
    } catch (error) {
      throw error;
    }
  },
  setItem: async function (
    name: string,
    value: string
  ): Promise<void> {
    const response = await fetch(
      `${firebaseUrl}/${name}.json`,
      {
        method: 'PUT',
        body: value,
        // headers: {
        //   'Content-Type': 'application/json',
        // },
      }
    ).then((res) => res.json());

    console.log(response);

    return;

    // sessionStorage.setItem(name, value);
  },
  removeItem: function (name: string): unknown {
    console.log('removeItem', name);

    // throw new Error('Function not implemented.');
    return null;
  },
};

export const firebaseStorage = createJSONStorage(
  () => storageApi
);
```

`src/stores/person/person.store.ts`

```ts
import { create, type StateCreator } from 'zustand';
import { persist } from 'zustand/middleware';
import { firebaseStorage } from '../storages/firebase.storage';

interface PersonState {
  firstName: string;
  lastName: string;

  // setFistName: (value: string) => void;
  // setLastName: (value: string) => void;
}

interface Actions {
  setFirstName: (value: string) => void;
  setLastName: (value: string) => void;
}

const storeAPI: StateCreator<PersonState & Actions> = (
  set
) => ({
  firstName: '',
  lastName: '',
  setFirstName: (value: string) =>
    set((state) => ({ firstName: value })),
  setLastName: (value: string) =>
    set((state) => ({ lastName: value })),
});

export const usePersonStore = create<PersonState & Actions>()(
  persist(storeAPI, {
    name: 'person-storage', // el name que usa sessionStorage arriba
    storage: firebaseStorage,
  })
);
```

En nuestra web/Persona debe salir `null` escribimos algo en los campos Nombres y Apellidos para ver cambios en la consola y en Firebase.

Puedes cambiar los datos en Firebase y se verán reflejados en nuestra web.

Firebase:

```
zustand
└── person-storage
    ├── state
    │   ├── firstName: "Ghost"
    │   └── lastName: "Dark"
    └── version: 0
```

### 3.11 Persist Middleware - Consideraciones

Condición de carrera

`src/stores/storages/firebase.storage.ts`

```ts
import {
  createJSONStorage,
  StateStorage,
} from 'zustand/middleware';

// Firebase URL + /zustand
const firebaseUrl =
  'https://zustandstoragexd-default-rtdb.firebaseio.com/zustand';

const storageApi: StateStorage = {
  getItem: async function (
    name: string
  ): Promise<string | null> {
    try {
      const data = await fetch(
        `${firebaseUrl}/${name}.json`
      ).then((res) => res.json());
      // const data = await response.json();

      console.log(data);

      return JSON.stringify(data);
    } catch (error) {
      throw error;
    }
  },
  setItem: async function (
    name: string,
    value: string
  ): Promise<void> {
    await fetch(`${firebaseUrl}/${name}.json`, { // 👈🏼👀👇🏻
      method: 'PUT',
      body: value,
      // headers: {
      //   'Content-Type': 'application/json',
      // },
    }).then((res) => res.json());

    console.count('setItem');

    return;

    // sessionStorage.setItem(name, value);
  },
  removeItem: function (name: string): unknown {
    console.log('removeItem', name);

    // throw new Error('Function not implemented.');
    return null;
  },
};

export const firebaseStorage = createJSONStorage(
  () => storageApi
);
```

`src/stores/bears/bears.store.ts`

```ts
import { create } from 'zustand';
import { persist } from 'zustand/middleware';

interface Bear {
  id: number;
  name: string;
}

interface BearState {
  blackBears: number;
  polarBears: number;
  pandaBears: number;

  bears: Bear[];

  totalBears: () => number; // 👈🏼👀

  increaseBlackBears: (by: number) => void;
  increasePolarBears: (by: number) => void;
  increasePandaBears: (by: number) => void;

  doNothing: () => void;
  addBear: () => void;
  clearBears: () => void;
}

export const useBearStore = create<BearState>()(
  persist(
    (set, get) => ({
      blackBears: 10,
      polarBears: 5,
      pandaBears: 1,

      bears: [{ id: 1, name: 'Oso #1' }],

      totalBears: () => { // 👈🏼👀👇🏻
        return (
          get().blackBears +
          get().polarBears +
          get().pandaBears +
          get().bears.length
        );
      },

      increaseBlackBears: (by: number) =>
        set((state) => ({
          blackBears: state.blackBears + by,
        })),
      increasePolarBears: (by: number) =>
        set((state) => ({
          polarBears: state.polarBears + by,
        })),
      increasePandaBears: (by: number) =>
        set((state) => ({
          pandaBears: state.pandaBears + by,
        })),

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
    }),
    {
      name: 'bears-store',
    }
  )
);
```

`src/pages/dashboard/DashboardPage.tsx`

```tsx
import {
  IoAccessibilityOutline,
  IoHeartOutline,
  IoListOutline,
  IoLockClosedOutline,
  IoPawOutline,
} from 'react-icons/io5';
import { WhiteCard } from '../../components';
import { useBearStore } from '../../stores/bears/bears.store';
import { usePersonStore } from '../../stores/person/person.store';

export const Dashboard = () => {
  const totalBears = useBearStore(
    (state) => state.totalBears
  );
  const firstName = usePersonStore(
    (state) => state.firstName
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
          <h2>Osos</h2>
          <p>{totalBears()}</p>
        </WhiteCard>

        <WhiteCard centered>
          <IoAccessibilityOutline
            size={50}
            className='text-indigo-600'
          />
          <h2>Persona</h2>
          <p>{firstName}</p>
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

### 3.12 Redux DevTools

Ejecutamos nuestro proyecto usando `npm run dev`, nos vamos a las Devtools y buscamos `Redux`. Luego seleccionamos la sección `Persona` en el Dashboard y recargamos, elegimos `State` y `Chart` para ver los siguientes pasos y sus valores.

`src/stores/person/person.store.ts`

```ts
import { create, type StateCreator } from 'zustand';
import { devtools, persist } from 'zustand/middleware';
import { firebaseStorage } from '../storages/firebase.storage';

interface PersonState {
  firstName: string;
  lastName: string;

  // setFistName: (value: string) => void;
  // setLastName: (value: string) => void;
}

interface Actions {
  setFirstName: (firstName: string) => void;
  setLastName: (lastName: string) => void;
}

type PersonStore = PersonState & Actions;

const storeAPI: StateCreator<
  PersonStore,
  [['zustand/devtools', never], ['zustand/persist', unknown]]
> = (set) => ({
  firstName: '',
  lastName: '',
  setFirstName: (value: string) =>
    set({ firstName: value }, false, 'setFirstName'),
  setLastName: (value: string) =>
    set({ lastName: value }, false, 'setLastName'),
});

export const usePersonStore = create<PersonStore>()(
  devtools(
    persist(storeAPI, {
      name: 'person-storage', // el name que usa sessionStorage arriba
      storage: firebaseStorage,
    })
  )
);
```

### 3.13 Custom Middleware - Logger

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
│   ├── stores
│   │   ├── bears
│   │   │   └── bears.store.ts
│   │   ├── middlewares 👈🏼👀👇🏻
│   │   │   └── logger.middleware.ts
│   │   ├── person
│   │   │   └── person.store.ts
│   │   └── storages
│   │       ├── firebase.storage.ts
│   │       └── session.storage.ts
│   └── vite-env.d.ts
├── tailwind.config.js
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

Primero probamos parte de un Middleware, revisando las salidas cambiando los datos de la pestaña Persona.

`src/stores/middlewares/logger.middleware.ts`

```ts
const loggerImpl: any =
  (f: any, name: any) => (set: any, get: any, store: any) => {
    const loggedSet: typeof set = (...a: any[]) => {
      set(...(a as Parameters<typeof set>));
      // console.log(...(name ? [`${name}:`] : []), get());
      console.log(get());
    };

    const setState = store.setState;
    store.setState = (...a: any[]) => {
      setState(...(a as Parameters<typeof setState>));
      console.log(
        ...(name ? [`${name}:`] : []),
        store.getState()
      );
    };

    return f(loggedSet, get, store);
  };

export const logger = loggerImpl as unknown as any;
```

`src/stores/middlewares/logger.middleware.ts`

```ts
// Copy from documentation
import {
  StateCreator,
  StoreMutatorIdentifier,
} from 'zustand';

type Logger = <
  T,
  Mps extends [StoreMutatorIdentifier, unknown][] = [],
  Mcs extends [StoreMutatorIdentifier, unknown][] = []
>(
  f: StateCreator<T, Mps, Mcs>,
  name?: string
) => StateCreator<T, Mps, Mcs>;

type LoggerImpl = <T>(
  f: StateCreator<T, [], []>,
  name?: string
) => StateCreator<T, [], []>;

const loggerImpl: LoggerImpl =
  (f, name) => (set, get, store) => {
    const loggedSet: typeof set = (...a) => {
      set(...(a as Parameters<typeof set>));
      console.log(...(name ? [`${name}:`] : []), get());
    };
    const setState = store.setState;
    store.setState = (...a) => {
      setState(...(a as Parameters<typeof setState>));
      console.log(
        ...(name ? [`${name}:`] : []),
        store.getState()
      );
    };

    return f(loggedSet, get, store);
  };

export const logger = loggerImpl as unknown as Logger;
// Copy from documentation
```

`src/stores/person/person.store.ts`

```ts
import { create, type StateCreator } from 'zustand';
import { devtools, persist } from 'zustand/middleware';
import { firebaseStorage } from '../storages/firebase.storage';
import { logger } from '../middlewares/logger.middleware';

interface PersonState {
  firstName: string;
  lastName: string;

  // setFistName: (value: string) => void;
  // setLastName: (value: string) => void;
}

interface Actions {
  setFirstName: (firstName: string) => void;
  setLastName: (lastName: string) => void;
}

type PersonStore = PersonState & Actions;

const storeAPI: StateCreator<
  PersonStore,
  [['zustand/devtools', never], ['zustand/persist', unknown]]
> = (set) => ({
  firstName: '',
  lastName: '',
  setFirstName: (value: string) =>
    set({ firstName: value }, false, 'setFirstName'),
  setLastName: (value: string) =>
    set({ lastName: value }, false, 'setLastName'),
});

export const usePersonStore = create<PersonStore>()(
  logger( // 👈🏼👀👇🏻 After testing, we remove the logger.
    devtools(
      persist(storeAPI, {
        name: 'person-storage', // el name que usa sessionStorage arriba
        storage: firebaseStorage,
      })
    )
  )
);
```

`src/stores/bears/bears.store.ts`

```ts
import { create } from 'zustand';
import { persist } from 'zustand/middleware';

interface Bear {
  id: number;
  name: string;
}

interface BearState {
  blackBears: number;
  polarBears: number;
  pandaBears: number;

  bears: Bear[];

  totalBears: () => number;

  increaseBlackBears: (by: number) => void;
  increasePolarBears: (by: number) => void;
  increasePandaBears: (by: number) => void;

  doNothing: () => void;
  addBear: () => void;
  clearBears: () => void;
}

export const useBearStore = create<BearState>()(
  persist(
    (set, get, store 👈🏼👀) => ({
      blackBears: 10,
      polarBears: 5,
      pandaBears: 1,

      bears: [{ id: 1, name: 'Oso #1' }],

      totalBears: () => {
        console.log(store); 👈🏼👀

        return (
          get().blackBears +
          get().polarBears +
          get().pandaBears +
          get().bears.length
        );
      },

      increaseBlackBears: (by: number) =>
        set((state) => ({
          blackBears: state.blackBears + by,
        })),
      increasePolarBears: (by: number) =>
        set((state) => ({
          polarBears: state.polarBears + by,
        })),
      increasePandaBears: (by: number) =>
        set((state) => ({
          pandaBears: state.pandaBears + by,
        })),

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
    }),
    {
      name: 'bears-store',
    }
  )
);
```

[Zustand common-recipes](https://zustand.docs.pmnd.rs/guides/advanced-typescript#common-recipes)

### 3.14 Código fuente de la sección

Código fuente de la sección por si lo llegan a necesitar.

[Github - Fin sección 3 - Middlewares](https://github.com/Klerith/zustand-mini-curso/tree/fin-seccion-03)

## 4. Tareas - Drag & Drop - Inmutabilidad con Immer

### 4.1 Introducción a la sección

### 4.2 Temas puntuales de la sección

En esta sección aprenderemos a trabajar con objetos anidados dentro de nuestro store, con el objetivo de apreciar claramente él benefició de utilizar la función **produce** o mejor aún, el middleware **immer,** para poder mutar el estado y generar uno nuevo basado en esa mutación.

Puntualmente veremos:

1. Drag & Drop (sin dependencias)
2. Uso de Store con objetos anidados
3. Middlewares
4. Funciones adicionales
5. UUID
6. Mutaciones vs Clonaciones
7. Tipado en TypeScript
8. Entre otras cosas

### 4.3 Continuación de la sección

Si estás en tu propio código fuente no necesitas comentar la línea `storage: firebaseStorage,` en:

`src/stores/person/person.store.ts`

```ts
import { create, type StateCreator } from 'zustand';
import { devtools, persist } from 'zustand/middleware';
import { firebaseStorage } from '../storages/firebase.storage';
import { logger } from '../middlewares/logger.middleware';

interface PersonState {
  firstName: string;
  lastName: string;

  // setFistName: (value: string) => void;
  // setLastName: (value: string) => void;
}

interface Actions {
  setFirstName: (firstName: string) => void;
  setLastName: (lastName: string) => void;
}

type PersonStore = PersonState & Actions;

const storeAPI: StateCreator<
  PersonStore,
  [['zustand/devtools', never], ['zustand/persist', unknown]]
> = (set) => ({
  firstName: '',
  lastName: '',
  setFirstName: (value: string) =>
    set({ firstName: value }, false, 'setFirstName'),
  setLastName: (value: string) =>
    set({ lastName: value }, false, 'setLastName'),
});

export const usePersonStore = create<PersonStore>()(
  // logger(
  devtools(
    persist(storeAPI, {
      name: 'person-storage', // el name que usa sessionStorage arriba
      // storage: firebaseStorage, 👈🏼👀
    })
  )
  // )
);
```

Si estás usando el código fuente de Fer, es necesario que comentes esa línea para evitar errores.

### 4.4 TaskStore e interfaces

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
│   ├── interfaces 👈🏼👀👇🏻
│   │   └── task.interface.ts
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
│   ├── stores
│   │   ├── bears
│   │   │   └── bears.store.ts
│   │   ├── middlewares
│   │   │   └── logger.middleware.ts
│   │   ├── person
│   │   │   └── person.store.ts
│   │   └── storages
│   │       ├── firebase.storage.ts
│   │       └── session.storage.ts
│   ├── tasks 👈🏼👀👇🏻
│   │   └── task.store.ts
│   └── vite-env.d.ts
├── tailwind.config.js
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

`src/interfaces/task.interface.ts`

```ts
export interface Task {
  id: string;
  title: string;
  status: TaskStatus;
}

export type TaskStatus = 'open' | 'in-progress' | 'done';
```

`src/tasks/task.store.ts`

```ts
import { create, StateCreator } from 'zustand';
import { Task } from '../interfaces/task.interface';

interface TaskState {
  tasks: Record<string, Task>;
}

const storeApi: StateCreator<TaskState> = (set) => ({
  tasks: {
    'ABC-1': { id: 'ABC-1', title: 'Task 1', status: 'open' },
    'ABC-2': {
      id: 'ABC-2',
      title: 'Task 2',
      status: 'in-progress',
    },
    'ABC-3': { id: 'ABC-3', title: 'Task 3', status: 'open' },
    'ABC-4': { id: 'ABC-4', title: 'Task 4', status: 'open' },
  },
});

export const useTaskStore = create<TaskState>()(storeApi);
```

`src/pages/02-objects/jiraPage.tsx`

```ts
import { JiraTasks } from '../../components';
import { useTaskStore } from '../../tasks/task.store';

export const JiraPage = () => {
  const tasks = useTaskStore((state) => state.tasks);

  console.log(tasks);

  return (
    <>
      <h1>Tareas</h1>
      <p>Manejo de estado con objectos de Zustand</p>
      <hr />

      <div className='grid grid-cols-1 md:grid-cols-3 gap-4'>
        <JiraTasks title='Pendientes' value='pending' />

        <JiraTasks title='Avanzando' value='in-progress' />

        <JiraTasks title='Terminadas' value='done' />
      </div>
    </>
  );
};
```

### 4.5 Obtener tareas por estado

`src/tasks/task.store.ts`

```ts
import { create, StateCreator } from 'zustand';
import type {
  Task,
  TaskStatus,
} from '../interfaces/task.interface';

interface TaskState {
  tasks: Record<string, Task>;
  getTaskByStatus: (status: TaskStatus) => Task[];
}

const storeApi: StateCreator<TaskState> = (set, get) => ({
  tasks: {
    'ABC-1': { id: 'ABC-1', title: 'Task 1', status: 'open' },
    'ABC-2': {
      id: 'ABC-2',
      title: 'Task 2',
      status: 'in-progress',
    },
    'ABC-3': { id: 'ABC-3', title: 'Task 3', status: 'open' },
    'ABC-4': { id: 'ABC-4', title: 'Task 4', status: 'open' },
  },
  getTaskByStatus: (status: TaskStatus) => {
    const tasks = get().tasks;

    return Object.values(tasks).filter(
      (task) => task.status === status
    );
  },
});

export const useTaskStore = create<TaskState>()(storeApi);
```

`src/pages/02-objects/jiraPage.tsx`

```ts
import { useShallow } from 'zustand/shallow';
import { JiraTasks } from '../../components';
import { useTaskStore } from '../../tasks/task.store';

export const JiraPage = () => {
  const pendingTasks = useTaskStore(
    useShallow((state) => state.getTaskByStatus('open'))
  );
  const inProgressTasks = useTaskStore(
    useShallow((state) =>
      state.getTaskByStatus('in-progress')
    )
  );
  const doneTasks = useTaskStore(
    useShallow((state) => state.getTaskByStatus('done'))
  );

  console.log({ pendingTasks, inProgressTasks, doneTasks });

  return (
    <>
      <h1>Tareas</h1>
      <p>Manejo de estado con objectos de Zustand</p>
      <hr />

      <div className='grid grid-cols-1 md:grid-cols-3 gap-4'>
        <JiraTasks title='Pendientes' value='pending' />

        <JiraTasks title='Avanzando' value='in-progress' />

        <JiraTasks title='Terminadas' value='done' />
      </div>
    </>
  );
};
```

### 4.6 Mostrar las tareas apropiadamente

Estructura:

```bash
```

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕


### 4.7

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕


### 4.8

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕


### 4.9

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕


### 4.10

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕


### 4.11

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕

### 4.12

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕

### 4.13

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕




### 4.14

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕


### 4.15

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕


### 4.16

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕


### 4.17

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕

### 4.18

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕




### 4.19

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕



### 4.20

``

```ts
```

``

```ts
```

👈🏼👀
👈🏼👀👇🏻
📌
➕






```
```


```
```
⚙️
👈🏼👀
👈🏼👀👇🏻
📌
➕