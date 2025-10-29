# Prettier extension configuration

## Formato predeterminado

Para dar el formato predeterminado de Visual Studio Code podemos usar `Ctrl + Shift + p` o `F1` luego buscar y elegir `Format Document`. Pero si quieres dar algún formato mas avanzado puedes hacer lo siguiente. 

## Instalar Prettier 

Debes buscar en Visual Studio Code la extensión **Prettier** e instalarla sin mas, luego te vas a su [página web](https://prettier.io/) y luego a `Try it online`. 

Aquí puedes configurar como quieres que se vean tus archivos formateados, al terminar solo le das en `Copy config JSON`, vas a tu proyecto y creas un archivo con el nombre `.prettierrc`. 

📌Nota: Para mayor detalle sobre la configuración puedes ver un tutorial donde explican esto. Ver link parte inferior. 

Queda algo así...

```json
{
  "arrowParens": "always",
  "bracketSameLine": false,
  "bracketSpacing": true,
  "embeddedLanguageFormatting": "auto",
  "htmlWhitespaceSensitivity": "css",
  "insertPragma": false,
  "jsxSingleQuote": false, 👈👀 true
  "printWidth": 80,
  "proseWrap": "preserve",
  "quoteProps": "as-needed",
  "requirePragma": false,
  "semi": true,
  "singleAttributePerLine": false,
  "singleQuote": false, 👈👀 true
  "tabWidth": 2,
  "trailingComma": "es5",
  "useTabs": false,
  "vueIndentScriptAndStyle": false
}
```

Este archivo deberás crearlo en cada proyecto, pero si no quieres eso puedes hacer lo siguiente.

## Configurar Prettier en tu editor 

- `Ctrl + ,` coma
- Botón Open Settings (JSON)

Si tienes algo así...

```json
"[html]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
```

Puedes cambiarlo por:

```json
"editor.formatOnSave": true,
"editor.defaultFormatter": "esbenp.prettier-vscode"
```

Como te darás cuenta, también agregamos una línea para formatear el documento al momento de guardar usando `Ctrl + s`.

Ahora, para tener toda nuestra configuración por defecto en Visual Studio Code, debemos copiar la configuración que creamos anteriormente y las pegamos en este mismo archivo. Adicionalmente, solo debemos agregarle `"prettier.xxxxxxx"` y listo, ya puedes eliminar el archivo que creamos previamente. 

```json
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
👇"prettier.arrowParens": "always",👈👀
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
👆"prettier.vueIndentScriptAndStyle": false👈👀
```

> Nota: Si prefieres usar comillas simples `' '` en lugar de comillas dobles `" "` debes cambiar de `false` a `true` estas opciones: `"prettier.jsxSingleQuote": true` y también `"prettier.singleQuote": true`

[🔥Escribe CÓDIGO LIMPIO Automáticamente en Visual Studio Code](https://www.youtube.com/watch?v=ouNMLoyEqZw)