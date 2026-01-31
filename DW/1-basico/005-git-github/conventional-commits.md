# Conventional Commits

## 🥇 Commitizen

Commitizen es una herramienta de línea de comandos (CLI) y utilidad de código abierto que guía a los desarrolladores a través del proceso de confirmación (commit) en Git, asegurando mensajes consistentes y estructurados siguiendo las convenciones de [Conventional Commits](https://www.viewnext.com/que-es-conventional-commit/). Automatiza la creación de mensajes de cambio y la gestión de versiones, mejorando la legibilidad del historial.

### Instalación

```bash
npm install -D commitizen cz-conventional-changelog
```

### Configuración

En tu `package.json`:

```json
{
  "config": {
    "commitizen": {
      "path": "cz-conventional-changelog"
    }
  }
}
```

### Uso

En vez de `git commit`, usas:

```bash
npx cz
```

Y te saldrá algo como:

```
? Select the type of change (feat, fix, refactor, etc)
? What is the scope of this change? (ui, game, components)
? Write a short description
```

🔥 **Ideal para aprender y no equivocarte nunca**.

---

## 🥈 Commitlint + Husky

👉 Evita que alguien haga commits mal escritos (aunque seas tú 😅).

### Instalación

```bash
npm install -D @commitlint/config-conventional @commitlint/cli husky
```

### Configurar commitlint

Crea `commitlint.config.cjs`:

```js
export default {
  extends: ['@commitlint/config-conventional'],
};
```

### Activar Husky

```bash
npx husky install
```

En `package.json`:

```json
{
  "scripts": {
    "prepare": "husky install"
  }
}
```

### Hook para commits

```bash
npx husky add .husky/commit-msg "npx --no -- commitlint --edit $1"
```

❌ Si escribes:

```bash
git commit -m "update stuff"
```

🚫 Te lo bloquea.

---

## 🥇 Combo PERFECTO

Usa **ambos**:

- ✍️ **Commitizen** → te ayuda a escribir bien
    
- 🛑 **Commitlint + Husky** → te obliga a cumplir la regla
    

Este combo es 🔥🔥🔥.

---

## 🧪 Ejemplo de flujo real

```bash
git add .
npx cz
```

Seleccionas:

```
feat
ui
add galaxy background animation
```

Resultado:

```bash
feat(ui): add galaxy background animation

# Other
chore(package.json): configure commitizen
```

Limpio. Profesional. GitHub-ready 😎

---

## 🧠 Extra: estándar para tu README (opcional)

```md
## Commit Convention

This project follows the Conventional Commits specification.

Examples:
- feat(ui): add reusable button component
- fix(game): prevent invalid moves
- refactor(components): simplify modal logic
```

