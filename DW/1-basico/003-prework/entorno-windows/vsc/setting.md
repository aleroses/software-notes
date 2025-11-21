# Configuración 

- Indenticator

## Abrir archivo `settings.json`

- `Ctrl` + `,` (coma)
 - Open settings: Esquina derecha superior
	 - Icono hoja con esquina doblada y con flecha ↪📄

## Quitar scroll horizontal 

```json
{
  "editor.wordWrap": "on",
}
```

Si no quieres configurar esto, solo usa `Ctrl + Z` cada vez que quieras tener todo en una sola vista sin necesidad de hacer scroll. 

## Configurar indentación del código 

Estilo de sangrado.

```json
{
  "editor.tabSize": 2,
}
```

Presiona `F1` busca la opción `Indent Using Spaces` y elige `2`. También puedes acceder desde la parte inferior del editor, aparece `Space: 4` le das clic y cambias a `2`. 

Adicional puedes buscar `Convert Indentation to Spaces` para que cada indentación hecha con el tabulador se transforme a espacios, en este caso a 2 espacios. Esto nos ayuda a que no se distorsione el código cuando lo subamos a GitHub. 

## Cambiar terminal  

```json
{
  "terminal.integrated.defaultProfile.windows": "Git Bash",
}
```

Otra opción:

```json
{
  "terminal.integrated.defaultProfile.windows": "PowerShell",
}
```

Si estás usando Oh My Posh:

```json
{
  "terminal.integrated.fontFamily": "MesloLGM Nerd Font",
}
```

Para ver la terminal usar:

- `Ctrl` + `Ñ`
- `Ctrl` + `J`

También:   
- View: Ver
- Terminal 

## Mover a la derecha barra de actividades

```json
{
  "workbench.sideBar.location": "right",
}
```

## Eliminar Mini map 

```json
{
  "editor.minimap.enabled": false,
}
```

## Ocultar Scrollbar  

```json
{
  "editor.scrollbar.vertical": "auto",
  "editor.overviewRulerBorder": false,
  "editor.hideCursorInOverviewRuler": true,
}
```

## Ocultar Debugging 🐞

```json
{
  "editor.glyphMargin": false,
}
```

## Ocultar Line Numbers

```json
{
  "editor.lineNumbers": "off",
}
```

En caso de necesitar los números ocasionalmente, puedes instalar la extensión [Line Numbers Toggle](https://marketplace.visualstudio.com/items?itemName=yay.lntoggle)

Usando `Ctrl + Shift + L` podrás cambiar entre `off / on` fácilmente.

> Nota: Puedes ver exactamente la línea donde estás ubicado en la **Barra de Estados** que se encuentra en la parte inferior. Si no ves algo como `Ln 131, Col 20` asegúrate de dar clic derecho sobre esta barra y activar `Editor Selection`.

## Ocultar Documentación Emergente MDN

```json
{
  "editor.parameterHints.enabled": false,
}
```

También puedes buscar `pop-up` dentro de la configuración y desactivar la casilla:

⚙ `Editor > Parameter Hints: Enabled`

- [ ] Enables a pop-up that shows parameter documentation and type information as you type. 

## Ocultar Barra de Actividades 

```json
{
  "workbench.activityBar.location": "hidden",
}
```

## Cambiar tamaño de fuente

```json
{
  "editor.fontSize": 12,
}
```

## Atajos para acceder a la barra de actividades: 

- `Ctrl` + `B`: Abrir y ocultar 
- `Ctrl` + `Shift` + `E` 
- `Ctrl` + `Shift` + `F` 
- `Ctrl` + `Shift` + `G` 
- `Ctrl` + `Shift` + `D` 
- `Ctrl` + `Shift` + `X`

Agente IA:

- `Ctrl + Alt + I` Abrir y ocultar 

[🔥 Tutorial: Cómo configurar VSCode](https://www.youtube.com/watch?v=HiVnGgYudLY)

## Otros 

```json
{
  "editor.cursorBlinking": "expand",
  "breadcrumbs.enabled": false,
  "editor.stickyScroll.enabled": true,
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.linkedEditing": true
}
```

[🔥 Tutorial: ¡Cambiar configuraciones de Visual Studio Code!](https://www.youtube.com/watch?v=uyEUVgNMvGI)

## Autocompletar Elementos JSX 

```json
{
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  }
}
```

[🔥 Tutorial: Configurar autocompletado JSX](https://www.youtube.com/watch?v=jIjws68ATY8)

## Resumen

Esta es la misma configuración de arriba más la configuración de Prettier ver [[prettier]].

```json
{
  "editor.wordWrap": "on",
  "editor.tabSize": 2,
  "editor.minimap.enabled": false,
  "editor.scrollbar.vertical": "auto",
  "editor.overviewRulerBorder": false,
  "editor.hideCursorInOverviewRuler": true,
  "editor.glyphMargin": false,
  "editor.lineNumbers": "off",
  "editor.parameterHints.enabled": false,

  "editor.cursorBlinking": "expand",
  "editor.stickyScroll.enabled": true,
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.linkedEditing": true,
  "editor.formatOnSave": true,
  // "editor.fontSize": 12,
  "editor.bracketPairColorization.independentColorPoolPerBracketType": true,
  "breadcrumbs.enabled": false,
  "files.autoSave": "afterDelay",

  "reactSnippets.settings.importReactOnTop": false,
  "workbench.sideBar.location": "right",
  "workbench.activityBar.location": "hidden",
  "workbench.secondarySideBar.defaultVisibility": "visible",
  "workbench.iconTheme": "material-icon-theme",
  "workbench.colorTheme": "Tokyo Night",

  "workbench.colorCustomizations": {
    "editorBracketHighlight.foreground1": "#fafafa",
    "editorBracketHighlight.foreground2": "#9F51B6",
    "editorBracketHighlight.foreground3": "#F7C244",
    "editorBracketHighlight.foreground4": "#F07850",
    "editorBracketHighlight.foreground5": "#97c26c",
    "editorBracketHighlight.foreground6": "#C497D4",
    "editorBracketHighlight.unexpectedBracket.foreground": "#fb6165"
  },

  "window.zoomLevel": -1,

  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },

  "terminal.integrated.fontFamily": "MesloLGM Nerd Font",
  "editor.defaultFormatter": "esbenp.prettier-vscode",

  "prettier.arrowParens": "always",
  "prettier.bracketSameLine": false,
  "prettier.bracketSpacing": true,
  "prettier.embeddedLanguageFormatting": "auto",
  "prettier.htmlWhitespaceSensitivity": "css",
  "prettier.insertPragma": false,
  "prettier.jsxSingleQuote": true,
  "prettier.printWidth": 62,
  "prettier.proseWrap": "preserve",
  "prettier.quoteProps": "as-needed",
  "prettier.requirePragma": false,
  "prettier.semi": true,
  "prettier.singleAttributePerLine": false,
  "prettier.singleQuote": true,
  "prettier.tabWidth": 2,
  "prettier.trailingComma": "es5",
  "prettier.useTabs": false,
  "prettier.vueIndentScriptAndStyle": false
}
```