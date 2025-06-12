# Monorepo

sui components

```bash
mkdir monorepo
cd monorepo
npm init -y
npm install @s-ui/mono
mkdir packages
code .
```

En `packages`:

```bash
cd packages
mkdir a b
cd a
npm init -y
cd ../b
npm init -y
```

Ahora en la raíz:

```json
{
  "name": "monorepo",
  "version": "1.0.0",
  "main": "index.js",
  "workspaces": ["packages/*"], 👈👀
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "@s-ui/mono": "^2.45.0"
  },
  "devDependencies": {},
  "description": ""
}
```

`monorepo/packages/a/package.json`

```json
{
  "name": "a",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "react": "17" 👈👀
  }
}

```

`monorepo/packages/b/package.json`

```json
{
  "name": "b",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "react": "17" 👈👀
  }
}
```

`monorepo/`

```bash
# Instala React
npm i
```

Dentro de `node_modules` veremos:

```bash
.
├── node_modules
│   ├── a -> ../packages/a
│   ├── add-stream
│   ├── ansi-colors
│   ├── ansi-regex
│   ├── ansi-styles
│   ├── react 👈👀👇
│   │   ├── build-info.json
│   │   ├── cjs
│   │   │   ├── react.development.js
│   │   │   ├── react-jsx-dev-runtime.development.js
│   │   │   ├── react-jsx-dev-runtime.production.min.js
│   │   │   ├── react-jsx-dev-runtime.profiling.min.js
│   │   │   ├── react-jsx-runtime.development.js
│   │   │   ├── react-jsx-runtime.production.min.js
│   │   │   ├── react-jsx-runtime.profiling.min.js
│   │   │   └── react.production.min.js
│   │   ├── index.js
│   │   ├── jsx-dev-runtime.js
│   │   ├── jsx-runtime.js
│   │   ├── LICENSE
│   │   ├── package.json
│   │   ├── README.md
│   │   └── umd
│   │       ├── react.development.js
│   │       ├── react.production.min.js
│   │       └── react.profiling.min.js
│   └── yargs-parser
├── package.json
├── package-lock.json
└── packages
    ├── a
    └── b
```

Al hacer modificaciones y querer hacer releases debemos hacer commits semánticos:

```bash
└── packages
    ├── a
    │   ├── index.js 👈👀
    │   └── package.json
    └── b
        ├── index.js 👈👀
        └── package.json
```

En `a/index.js`:

```js
console.log("Message a");
```

En `b/index.js`:

```js
console.log("Message b");
```

`monorepo/package.json`

```bash
{
  "name": "monorepo",
  "version": "1.0.0",
  "main": "index.js",
  "workspaces": ["packages/*"],
  "scripts": {
    "co": "sui-mono commit" 👈👀
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "@s-ui/mono": "2" 👈👀
  },
  "devDependencies": {},
  "description": ""
}
```

Añadimos un `.gitignore`

```bash
.
├── .gitignore 👈👀
├── node_modules
├── package.json
├── package-lock.json
└── packages
```

```js
node_modules
package-lock.json
```

Ejecutamos:

```bash
git init
git add .
npm run co

> monorepo@1.0.0 co
> sui-mono commit

? Type of change that you're committing … 
  feat     · Add a new feature
  fix      · Submit a bug fix
  docs     · Documentation changes
  refactor · Neither fixes a bug nor adds a feature. Code styling.
  perf     · Change that improves performance.
  test     · Add or modify tests only.
▸ chore    · Changes to the build process or auxiliary tools. 👈👀
  release  · Publish a new version of a package.
? 
Denote the SCOPE of this change: … 
  packages/a
  packages/b
▸ Root 👈👀
? Write a SHORT, IMPERATIVE tense description of the change:
 ‣ Setup project 👈👀
? Provide a LONGER description of the change (optional). Use "|" to break new line:
 ‣ 🔥 Just press enter. 👈👀
? List any ISSUES CLOSED by this change (optional). E.g.: #31, #34:
 ‣ 🔥 Just press enter. 👈👀
 Are you sure you want to proceed with the commit above? (Y/n) ‣ true 👈👀
```

Hacemos cambios en los archivos:

`packages/a/index.js`

```js
console.log("Message a v2");
```

Ahora solo hacemos una realease de este proyecto.

```bash
git add packages/a/index.js
npm run co

> monorepo@1.0.0 co
> sui-mono commit

? Type of change that you're committing … 
▸ feat     · Add a new feature 👈👀
  fix      · Submit a bug fix
  docs     · Documentation changes
  refactor · Neither fixes a bug nor adds a feature. Code styling.
  perf     · Change that improves performance.
  test     · Add or modify tests only.
  chore    · Changes to the build process or auxiliary tools.
  release  · Publish a new version of a package.
? 
Denote the SCOPE of this change: … 
▸ packages/a 👈👀
  Root
? Write a SHORT, IMPERATIVE tense description of the change:
 ‣ Add more info to the console.log 👈👀
? Provide a LONGER description of the change (optional). Use "|" to break new line:
 ‣ Enter 👈👀
? List any BREAKING CHANGES (optional):
 ‣ Enter 👈👀
? List any ISSUES CLOSED by this change (optional). E.g.: #31, #34:
 ‣ Enter 👈👀
? 

feat(packages/a): Add more info to the console.log 🔥

Are you sure you want to proceed with the commit above? (Y/n) ‣ true 👈👀
```

Ahora podemos ver los commits:

```bash
git log
```

Este el historial de los dos commits hechos anteriormente:

```bash
commit 0f156d8064ae2eabdbd1ed9ac3c45889f302d04d (HEAD -> master)
Author: Ale Rxses <alx.vs@outlook.com>
Date:   Wed Jun 11 18:38:20 2025 -0500

    feat(packages/a): Add more info to the console.log

commit 11fa9d317b1b712746adc188a67ceb8aeb193a38
Author: Ale Rxses <alx.vs@outlook.com>
Date:   Wed Jun 11 17:53:02 2025 -0500

    chore(Root): Setup project
```

Tenemos una manera de ver si tenemos que hacer releases:

```bash
./node_modules/.bin/sui-mon check

# obtenemos:
Releases to do:

 packages/a ─ new MINOR version: 
  > feat(packages/a): Add more info to the console.log
```



Añadimos nuevos cambios en el archivo:

`packages/b/index.js`

```js
console.log("Don't make alerts in real life.");
```

```bash
git add packages/b/index.js
npm run co

> monorepo@1.0.0 co
> sui-mono commit

? Type of change that you're committing … 
▸ feat     · Add a new feature 👈👀
  fix      · Submit a bug fix
  docs     · Documentation changes
  refactor · Neither fixes a bug nor adds a feature. Code styling.
  perf     · Change that improves performance.
  test     · Add or modify tests only.
  chore    · Changes to the build process or auxiliary tools.
  release  · Publish a new version of a package.
? 
Denote the SCOPE of this change: … 
▸ packages/b 👈👀
  Root
? Write a SHORT, IMPERATIVE tense description of the change:
 ‣ Use alert instead console.log 👈👀
? Provide a LONGER description of the change (optional). Use "|" to break new line:
 ‣ Enter 👈👀
? List any BREAKING CHANGES (optional):
 ‣ We are using alert now so we are blocking the UI. Be careful 👈👀
? List any ISSUES CLOSED by this change (optional). E.g.: #31, #34:
 ‣ Enter 👈👀
? 

feat(packages/b): Use alert instead console.log 🔥

BREAKING CHANGES: 🔥
We are using alert now so we are blocking the UI. Be careful 🔥


Are you sure you want to proceed with the commit above? (Y/n) ‣ true 👈👀
```

```bash
./node_modules/.bin/sui-mon check

# obtenemos:
Releases to do:

 packages/a ─ new MINOR version: 
  > feat(packages/a): Add more info to the console.log

 packages/b ─ new MAJOR version: 
  > BREAKING CHANGE - feat(packages/b): Use alert instead console.log
```

Con sui-mono las releases se hacen así:

```bash
./node_modules/.bin/sui-mon release
```

## Enlaces

- [Crea un monorepositorio multipaquete con npm workspaces y releases de paquetes](https://www.youtube.com/watch?v=2QSBXhuqSlI)
- [Monorepo multipaquete con NPM Workspaces](https://www.youtube.com/watch?v=KEkRy4q_0oI)