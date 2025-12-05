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
- 

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

### 2.2 v de la sección

En esta sección tendremos las bases de Zustand, como son:

- Instalaciones
- Configuraciones
- Propiedades computadas
- Objetos anidados
- Actualizaciones de estado
- Configuraciones con TypeScript
- useShallow

Esta sección nos dejará las bases para poder entender el objetivo de este gestor de estado tan poderoso.

### 2.3 

⚙️