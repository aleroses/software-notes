# Configuración 

- Indenticator

## Abrir archivo `settings.json`

- `Ctrl` + `,` (coma)
 - Open settings: Esquina derecha superior
	 - Icono hoja con esquina doblada y con flecha ↪📄

## Quitar scroll horizontal 

```json
{
  "editor.wordWrap": "on", //👈👀
}
```

Si no quieres configurar esto, solo usa control z cada vez que quieras tener todo en una sola vista sin necesidad de hacer scroll. 

## Configurar indentación del código 

Estilo de sangrado. 
```json
{
  "editor.tabSize": 2, //👈👀
}
```

Presiona `F1` busca la opción `Indent Using Spaces` y elige `2`. También puedes acceder desde la parte inferior del editor, aparece `Space: 4` le das clic y cambias a `2`. 

Adicional puedes buscar `Convert Indentation to Spaces` para que cada indentación hecha con el tabulador se transforme a espacios, en este caso a 2 espacios. Esto nos ayuda a que no se distorsione el código cuando lo subamos a GitHub. 

## Cambiar terminal  

```json
{
  "terminal.integrated.defaultProfile.windows": "Git Bash", //👈👀
}
```

Otra opción 
```json
{
  "terminal.integrated.defaultProfile.windows": "PowerShell" //👈👀
}
```

Para ver la terminal usar:  
- `Ctrl` + `ñ`

También:   
- View: Ver
- Terminal 

## Mover a la derecha barra de actividades

```json
{
  "workbench.sideBar.location": "right", //👈👀
}
```

## Eliminar Mini map 

```json
{
  "editor.minimap.enabled": false, //👈👀
}
```

## Ocultar Scrollbar  

```json
{
  "editor.scrollbar.vertical": "auto", //👈👀
  "editor.overviewRulerBorder": false, //👈👀
  "editor.hideCursorInOverviewRuler": true, //👈👀
}
```

## Ocultar Debugging 🔴

```json
{
  "editor.glyphMargin": false, //👈👀
}
```

## Ocultar Line Numbers

```json
{
  "editor.lineNumbers": "off", //👈👀
}
```

En caso de necesitar los números ocasionalmente, puedes instalar la extensión [Line Numbers Toggle](https://marketplace.visualstudio.com/items?itemName=yay.lntoggle)

Usando `Ctrl + Shift + L` podrás cambiar entre `off / on` fácilmente.

## Ocultar Documentación Emergente MDN

```json
{
  "editor.parameterHints.enabled": false //👈👀
}
```

Tambien puedes buscar `pop-up` dentro de la configuración y desactivar la casilla:

⚙ `Editor > Parameter Hints: Enabled`

- [ ] Enables a pop-up that shows parameter documentation and type information as you type. 

## Ocultar Barra de Actividades 

```json
{
  "workbench.activityBar.location": "hidden", //👈👀
}
```

Atajos para acceder a la barra de actividades: 
- `Ctrl` + `Shift` + `E` 
	- `Ctrl` + `B`: Abrir y ocultar 
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
  "workbench.sideBar.location": "right",
  "editor.minimap.enabled": false,
  "editor.scrollbar.vertical": "auto",
  "editor.overviewRulerBorder": false,
  "editor.hideCursorInOverviewRuler": true,
  "editor.glyphMargin": false,
  "editor.lineNumbers": "off",
  "editor.parameterHints.enabled": false,
  "workbench.activityBar.location": "hidden",

  "editor.cursorBlinking": "expand",
  "breadcrumbs.enabled": false,
  "editor.stickyScroll.enabled": true,
  "editor.cursorSmoothCaretAnimation": "on",
  "editor.linkedEditing": true,

  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },

  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",

  "prettier.arrowParens": "always",
  "prettier.bracketSameLine": false,
  "prettier.bracketSpacing": true,
  "prettier.embeddedLanguageFormatting": "auto",
  "prettier.htmlWhitespaceSensitivity": "css",
  "prettier.insertPragma": false,
  "prettier.jsxSingleQuote": true,
  "prettier.printWidth": 80,
  "prettier.proseWrap": "preserve",
  "prettier.quoteProps": "as-needed",
  "prettier.requirePragma": false,
  "prettier.semi": true,
  "prettier.singleAttributePerLine": false,
  "prettier.singleQuote": true,
  "prettier.tabWidth": 2,
  "prettier.trailingComma": "es5",
  "prettier.useTabs": false,
  "prettier.vueIndentScriptAndStyle": false,
  "workbench.secondarySideBar.defaultVisibility": "visible"
}
```