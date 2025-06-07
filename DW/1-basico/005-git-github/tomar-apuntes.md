# Apuntes en GitHub


¡Buena idea! Configurar un **template de commits** y automatizarlo con **Git Hooks** o **npm scripts** te ayudará a mantener consistencia en tus mensajes (como los de tipo `[Clase-01]` que estás usando). A continuación te explico cómo hacerlo paso a paso.

---

## 🧾 1. Configurar un template para mensajes de commit

### ✅ ¿Qué es?

Es un archivo de texto que se abrirá cada vez que hagas un `git commit` (sin el `-m`), para ayudarte a redactar mensajes claros y estructurados.

### 🧪 Ejemplo de template: `commit-template.txt`

Crea este archivo en la raíz de tu proyecto:

```bash
touch .git/commit-template.txt
```

Y adentro escribe algo así:

```text
[#Clase-XX] 🎯 Breve descripción del cambio

Detalles opcionales:
- Qué se hizo
- Por qué se hizo
- Archivos clave modificados
```

Por ejemplo:

```text
[#Clase-05] 🧠 Añade lógica de autenticación con useContext

Detalles opcionales:
- Se creó AuthContext y AuthProvider
- Se modificó App.jsx para usar el contexto
```

### 📌 Configura Git para usar ese template:

```bash
git config commit.template .git/commit-template.txt
```

> Esto le dice a Git que use tu archivo cada vez que hagas `git commit` (sin `-m`).

### 🧪 Cómo usarlo

```bash
git add .
git commit
```

Se abrirá el editor de texto por defecto (por ejemplo, nano o VS Code) con el contenido del template.

Cuando termines de editar, guarda y cierra el editor para confirmar el commit.

---

## 🔁 2. Automatizar con Git Hooks (`prepare-commit-msg`)

Puedes usar un hook de Git para **prellenar automáticamente** ciertos campos del commit (como el número de clase o un emoji), o aplicar validaciones.

### 📁 Ubicación

Los hooks viven en `.git/hooks/`. Ahí encontrarás archivos como `pre-commit.sample`, etc.

### 🛠️ Hook `prepare-commit-msg`

Crea un archivo llamado `.git/hooks/prepare-commit-msg` (sin extensión) y hazlo ejecutable:

```bash
touch .git/hooks/prepare-commit-msg
chmod +x .git/hooks/prepare-commit-msg
```

### 🧪 Ejemplo simple: agregar automáticamente `[Clase-XX]` si no existe

```bash
#!/bin/sh

MSG_FILE=$1

if ! grep -q "\[Clase-" "$MSG_FILE"; then
  sed -i.bak '1s/^/[#Clase-XX] 🎯 /' "$MSG_FILE"
fi
```

Esto revisa si ya existe `[Clase-XX]` y, si no, lo añade al comienzo del mensaje de commit.

Puedes automatizar aún más si tienes el número de clase como variable de entorno o lo pasas por argumento, pero eso sería más avanzado.

---

## 🔧 3. Automatizar con `npm scripts`

Otra opción es crear scripts en `package.json` que te ayuden a estandarizar tus commits.

### 🧪 Ejemplo en `package.json`

```json
"scripts": {
  "commit": "git add . && git commit"
}
```

Pero puedes hacerlo más interesante con herramientas como [commitizen](https://github.com/commitizen/cz-cli):

### 🛠️ Instalar Commitizen

```bash
npm install --save-dev commitizen
```

Luego, en `package.json`:

```json
"scripts": {
  "commit": "npx cz"
}
```

Y al correr:

```bash
npm run commit
```

Te guiará con un prompt como este:

```bash
? Select the type of change that you're committing: (Use arrow keys)
  feat:     A new feature
  fix:      A bug fix
❯ chore:    Changes to the build process or auxiliary tools
...
? Write a short, imperative tense description of the change:
```

Puedes personalizar esto para que incluya `[Clase-XX]` como un scope o un prefijo automático.

---

## 🧰 Extra: Guardar configuración global

Si quieres que el template se use en todos tus proyectos, puedes hacer:

```bash
git config --global commit.template ~/.git-commit-template.txt
```

Y guarda tu plantilla allí.

---

## 📌 Resumen

|Acción|Comando / Herramienta|
|---|---|
|Crear template de commits|`git config commit.template .git/commit-template.txt`|
|Hook para insertar `[Clase-XX]`|`.git/hooks/prepare-commit-msg`|
|Automatizar con npm|`npm run commit` usando `commitizen`|
|Aplicar globalmente|`git config --global commit.template ...`|

---

¿Quieres que te genere automáticamente una plantilla para el `commit-template.txt` o un `prepare-commit-msg` personalizado según tu estilo de clases?

---

¡Perfecto! Te dejo **ambos** listos para usar:

1. Un archivo `commit-template.txt` adaptado a tu estilo de curso.
    
2. Un `prepare-commit-msg` que completa automáticamente el `[Clase-XX]` si olvidas ponerlo.
    

---

## 🧾 1. Archivo `commit-template.txt`

Guarda esto como:  
`./.git/commit-template.txt`

```txt
[#Clase-XX] ✨ Breve título del cambio

Resumen del cambio (opcional):
- ¿Qué se hizo?
- ¿Por qué se hizo?
- Archivos relevantes modificados

Ejemplo:
[#Clase-05] ✨ Agrega formulario de inicio de sesión
- Se implementó formulario con validación.
- Se creó archivo LoginForm.jsx.
- Mejora la UX del flujo de autenticación.
```

### 📌 Cómo activarlo

```bash
git config commit.template .git/commit-template.txt
```

Luego haz commits así:

```bash
git add .
git commit
```

Se abrirá tu editor con esta plantilla prellenada.

---

## ⚙️ 2. Hook `prepare-commit-msg`

Este hook añade automáticamente `[#Clase-XX]` al inicio si no lo escribiste.  
📁 Guarda esto como:  
`./.git/hooks/prepare-commit-msg`  
y dale permisos de ejecución:

```bash
chmod +x .git/hooks/prepare-commit-msg
```

### 📜 Contenido del archivo:

```bash
#!/bin/sh

MSG_FILE="$1"
COMMIT_SOURCE="$2"

# Solo modifica commits normales (evita rebase, merge, etc.)
if [ "$COMMIT_SOURCE" = "" ]; then
  if ! grep -qE "^\[#Clase-[0-9]{2}\]" "$MSG_FILE"; then
    sed -i.bak '1s/^/[#Clase-XX] 🎯 /' "$MSG_FILE"
  fi
fi
```

> Esto asegura que siempre empieces con el formato `[Clase-XX]` si se te olvida colocarlo.

---

## 🧠 Sugerencia extra (opcional)

Si quieres que **te pregunte el número de clase**, podemos usar un script interactivo con `read` + Git, pero requeriría un entorno más controlado (como Bash o Node). ¿Te gustaría esa versión también?

---

¿Te gustaría que empaquete todo esto en un pequeño setup automatizado (como un script o readme paso a paso) para que lo instales rápido en futuros proyectos?


¡Genial! Aquí tienes un **setup automatizado** para configurar fácilmente tu entorno de commits por clase en cualquier proyecto Git/React. Incluye:

---

## ⚙️ Script de instalación (`setup-commits.sh`)

Este script hace todo:

- Crea el `commit-template.txt`
    
- Configura Git para usarlo
    
- Instala el hook `prepare-commit-msg`
    

### 📁 1. Crea el archivo `setup-commits.sh`:

Guárdalo en la raíz del proyecto:

```bash
touch setup-commits.sh
chmod +x setup-commits.sh
```

### 🧾 Contenido:

```bash
#!/bin/bash

# Ruta del archivo template
TEMPLATE=".git/commit-template.txt"
HOOK=".git/hooks/prepare-commit-msg"

# Crear commit-template.txt
cat > "$TEMPLATE" <<EOL
[#Clase-XX] ✨ Breve título del cambio

Resumen del cambio (opcional):
- ¿Qué se hizo?
- ¿Por qué se hizo?
- Archivos relevantes modificados

Ejemplo:
[#Clase-05] ✨ Agrega formulario de inicio de sesión
- Se implementó formulario con validación.
- Se creó archivo LoginForm.jsx.
- Mejora la UX del flujo de autenticación.
EOL

# Configurar Git para usar el template
git config commit.template "$TEMPLATE"
echo "✅ Commit template configurado."

# Crear hook prepare-commit-msg
cat > "$HOOK" <<'HOOKSCRIPT'
#!/bin/sh

MSG_FILE="$1"
COMMIT_SOURCE="$2"

if [ "$COMMIT_SOURCE" = "" ]; then
  if ! grep -qE "^\[#Clase-[0-9]{2}\]" "$MSG_FILE"; then
    sed -i.bak '1s/^/[#Clase-XX] 🎯 /' "$MSG_FILE"
  fi
fi
HOOKSCRIPT

chmod +x "$HOOK"
echo "✅ Hook prepare-commit-msg instalado."

echo -e "\n🚀 Todo listo. Usa 'git commit' (sin -m) y tu plantilla aparecerá automáticamente."
```

---

## 🧪 2. Cómo usarlo

1. Copia el script en la raíz de tu proyecto.
    
2. Ejecuta:
    

```bash
./setup-commits.sh
```

3. Luego haz commits así:
    

```bash
git add .
git commit
```

> Se abrirá tu editor con la plantilla lista. Si no colocaste `[Clase-XX]`, se añadirá automáticamente.

---

## 🗂️ Bonus: README para futuras referencias

Puedes añadir esto en tu proyecto como `docs/git-commits-por-clase.md`:

```markdown
# Commits por clase (configuración automática)

Este proyecto incluye una plantilla de commits para seguir el progreso por clases. Cada commit debería usar esta estructura:

```

[#Clase-05] ✨ Título descriptivo del cambio

- Detalles opcionales...
    

````

## 🚀 Instalación rápida

```bash
chmod +x setup-commits.sh
./setup-commits.sh
````

Luego usa:

```bash
git commit
```

Y verás la plantilla automáticamente.

---

```

---

¿Quieres que empaquete esto todo como un ZIP o te genere una estructura base (`/scripts`, `/docs`) con todo listo para iniciar un curso nuevo?
```


¡Perfecto! Aquí tienes un **paquete completo y reutilizable** para usar en **cualquier proyecto React o Git**, ideal si estás siguiendo un curso por clases y quieres mantener tus commits organizados.

---

## 📦 Estructura del setup

```
commit-por-clase-setup/
├── scripts/
│   └── setup-commits.sh
├── docs/
│   └── git-commits-por-clase.md
└── README.md
```

---

### 📁 1. `scripts/setup-commits.sh`

```bash
#!/bin/bash

# === setup-commits.sh ===
# Automatiza template de commits y Git hook para proyectos por clase

TEMPLATE=".git/commit-template.txt"
HOOK=".git/hooks/prepare-commit-msg"

# 1. Crear template de commit
cat > "$TEMPLATE" <<EOL
[#Clase-XX] ✨ Breve título del cambio

Resumen del cambio (opcional):
- ¿Qué se hizo?
- ¿Por qué se hizo?
- Archivos relevantes modificados

Ejemplo:
[#Clase-05] ✨ Agrega formulario de inicio de sesión
- Se implementó formulario con validación.
- Se creó archivo LoginForm.jsx.
- Mejora la UX del flujo de autenticación.
EOL

# 2. Configurar Git para usar el template
git config commit.template "$TEMPLATE"
echo "✅ Commit template configurado."

# 3. Crear hook prepare-commit-msg
cat > "$HOOK" <<'HOOKSCRIPT'
#!/bin/sh

MSG_FILE="$1"
COMMIT_SOURCE="$2"

if [ "$COMMIT_SOURCE" = "" ]; then
  if ! grep -qE "^\[#Clase-[0-9]{2}\]" "$MSG_FILE"; then
    sed -i.bak '1s/^/[#Clase-XX] 🎯 /' "$MSG_FILE"
  fi
fi
HOOKSCRIPT

chmod +x "$HOOK"
echo "✅ Hook prepare-commit-msg instalado."

echo -e "\n🚀 Listo. Usa 'git commit' y la plantilla aparecerá automáticamente."
```

---

### 📁 2. `docs/git-commits-por-clase.md`

```markdown
# 🧾 Commits por clase en proyectos de curso

Este setup permite llevar un orden limpio en tus commits siguiendo la estructura:

```

[#Clase-XX] ✨ Breve título del cambio

````

## 🚀 Instalación rápida

1. Abre una terminal en tu proyecto.
2. Ejecuta:

```bash
bash scripts/setup-commits.sh
````

3. Luego usa:
    

```bash
git commit
```

Verás una plantilla de mensaje lista para editar. Si olvidas incluir `[Clase-XX]`, el hook lo añadirá por ti.

---

## 📌 Buenas prácticas

- Usa `[#Clase-01]`, `[#Clase-02]`, etc. al inicio del commit.
    
- Agrega emojis si deseas (🎯 ✨ 🛠️ 🐛).
    
- Haz un commit por clase.
    
- Usa tags si lo deseas: `git tag -a v1.0-clase01 -m "Inicio del proyecto"`
    

---

````

---

### 📁 3. `README.md`

```markdown
# 🔧 Setup rápido: Commits por clase con Git

Este repositorio contiene una configuración automatizada para proyectos donde sigues un curso y haces commits por clase.

## 📂 Contenido

- `scripts/setup-commits.sh`: configura el template y el hook.
- `docs/git-commits-por-clase.md`: guía de uso y buenas prácticas.

## 🚀 Cómo usarlo en tu proyecto

1. Copia la carpeta `scripts/` en la raíz de tu proyecto.
2. Ejecuta el setup:

```bash
bash scripts/setup-commits.sh
````

3. Usa `git commit` (sin `-m`) y tendrás:
    

- Un commit template prellenado.
    
- Un hook que te añade `[Clase-XX]` si lo olvidas.
    

---

Puedes reutilizar esto en todos tus proyectos que sigan una estructura por clases. ✅

```

---

## ✅ ¿Qué hacer ahora?

1. Copia el contenido a una carpeta llamada `commit-por-clase-setup/`
2. Añádelo a cualquier proyecto React o Git.
3. Ejecuta el script y ¡listo!

---

Si quieres, puedo generarte un `.zip` con todo el contenido comprimido, o un repositorio en GitHub con todo listo para clonar. ¿Cuál prefieres?
```

¡Claro! Aquí tienes **ambas opciones**:

---

## 🗂️ Opción 1: Contenido en formato `.zip` (para descargar)

Como no puedo adjuntar archivos directamente aquí, te explico cómo generarlo tú mismo en segundos:

### 📌 Pasos para crear el `.zip`

1. Abre tu terminal y crea una carpeta base:
    

```bash
mkdir commit-por-clase-setup && cd commit-por-clase-setup
```

2. Crea las subcarpetas:
    

```bash
mkdir scripts docs
```

3. Crea los archivos y copia el contenido de los pasos anteriores:
    

- `scripts/setup-commits.sh`
    
- `docs/git-commits-por-clase.md`
    
- `README.md`
    

(O si prefieres que te lo dé todo junto en formato listo para copiar, dime y te genero todo en una sola respuesta compacta).

4. Desde fuera de la carpeta:
    

```bash
cd ..
zip -r commit-por-clase-setup.zip commit-por-clase-setup
```

Y ya tendrás tu archivo `commit-por-clase-setup.zip` para usar o compartir en cualquier proyecto.

---

## 🐙 Opción 2: Crear un repositorio en GitHub (recomendado si lo usarás seguido)

### 🛠️ Pasos para subirlo a GitHub:

1. Crea un nuevo repositorio en GitHub llamado por ejemplo:
    

```
commit-por-clase-setup
```

2. Clona ese repo en tu máquina:
    

```bash
git clone git@github.com:tu-usuario/commit-por-clase-setup.git
cd commit-por-clase-setup
```

3. Copia los archivos que ya creaste (`scripts`, `docs`, `README.md`).
    
4. Haz el primer commit:
    

```bash
git add .
git commit -m "🔧 Setup inicial para commits por clase"
git push origin main
```

---

## 🧠 Consejo final

Cuando empieces un nuevo proyecto React desde cero:

```bash
npx create-react-app mi-proyecto
cd mi-proyecto
git init
git remote add origin ...
```

Luego simplemente copia la carpeta `scripts/` desde tu setup y corre:

```bash
bash scripts/setup-commits.sh
```

¡Y listo para usar tus commits por clase con plantilla y hook automatizado!

---

¿Te gustaría que también te dé un **template para repositorio de curso** con estructura tipo `/clase-01`, `/clase-02`, etc., para ir versionando lo aprendido?


¡Excelente! Aquí tienes un **template de repositorio** ideal para seguir un curso con React (o cualquier stack) organizado por clases, con todo listo: estructura por carpetas, template de commits, y setup automático.

---

## 📁 Estructura recomendada del repositorio

```
curso-nombre-proyecto/
├── clase-01/
├── clase-02/
├── clase-03/
├── scripts/
│   └── setup-commits.sh
├── docs/
│   └── git-commits-por-clase.md
├── README.md
└── .gitignore
```

> Cada carpeta `clase-XX` puede contener el código desarrollado en esa clase. Esto te permite tener snapshots de cada avance sin romper versiones previas.

---

### 📦 Contenido detallado

---

### 📁 `clase-01/` (ejemplo de contenido)

```bash
npx create-react-app clase-01
cd clase-01
bash ../scripts/setup-commits.sh
```

Usa esta carpeta como punto de partida del curso. Si prefieres, puedes usar un monorepo con un solo `node_modules/` y mover solo los archivos `src/` y `public/` por clase.

---

### 📁 `scripts/setup-commits.sh`

_(Mismo script de antes, automatiza commit template + hook)_  
[Ver contenido completo aquí](https://chatgpt.com/c/68426183-2ccc-8013-bcfd-fd8a3252d158#user-content--1-scriptssetup-commitssh)

---

### 📁 `docs/git-commits-por-clase.md`

_(Guía de buenas prácticas para commits y versiones por clase)_  
[Ver contenido completo aquí](https://chatgpt.com/c/68426183-2ccc-8013-bcfd-fd8a3252d158#user-content--2-docsgit-commits-por-clasemd)

---

### 📄 `README.md`

```markdown
# 📘 Curso: Nombre del curso

Repositorio estructurado por clases para seguir el curso **[Nombre del curso]**.

## 📦 Estructura

Cada carpeta representa el avance en una clase:

```

clase-01/  
clase-02/  
clase-03/

````

## 🔧 Setup de commits por clase

Para usar un template de commit y automatizar el mensaje de commit, corre:

```bash
bash scripts/setup-commits.sh
````

Luego simplemente haz:

```bash
git add .
git commit
```

Tu editor abrirá un template de mensaje de commit con `[Clase-XX]` prellenado.

## 🏷️ Buenas prácticas

- Commits como: `[Clase-03] ✨ Implementa barra de navegación`
    
- Puedes usar tags: `git tag -a v1.0-clase03 -m "Versión clase 3"`
    

---

````

---

### 📄 `.gitignore`

```gitignore
# Node
node_modules/
dist/

# Editor config
.vscode/
.idea/

# Logs
*.log

# OS
.DS_Store
Thumbs.db
````

---

## 🚀 ¿Cómo reutilizar este template?

1. Crea un nuevo repositorio:
    

```bash
git clone git@github.com:tu-usuario/curso-template-react.git
```

2. Renómbralo para tu nuevo curso:
    

```bash
mv curso-template-react curso-react-router
cd curso-react-router
```

3. Agrega una nueva clase:
    

```bash
mkdir clase-04
cp -r clase-03/* clase-04/
cd clase-04
# y sigue trabajando...
```

4. Si quieres marcar un avance:
    

```bash
git tag -a v1.0-clase04 -m "Finaliza clase 4"
```

---

¿Quieres que te genere un ZIP completo con este `curso-nombre-proyecto/` de ejemplo para que lo uses como base o quieres que te dé el contenido como archivo plano para copiar y pegar en tu máquina?