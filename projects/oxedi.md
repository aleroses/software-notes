# Oxedi

## Compilar

```bash
bash crates/oxedi_wasm/scripts/install_tools.sh

wasm-bindgen --version && wasm-opt --version

make wasm

python3 -m http.server 8001 --directory viewer

# echo escribe el texto "frontend-notes/", y los operadores `>>` adjuntan esa línea al final del archivo oculto
echo "frontend-notes/" >> .git/info/exclude
# El archivo `exclude` funciona exactamente igual que un `.gitignore`, pero de forma **local y privada** para tu máquina (no se comparte con el repositorio remoto ni con otros desarrolladores).
```

## Pull Request

No hagas ningun cambio. Solo dime que nombre de rama le pondrias a la rama con la que voy a hacer pull request en github? tengo viewer-tokens pero quiza no aplique.


viewer-redesign

315d6d2

```bash
# Anota el hash del commit listo, ej. a1b2c3d
git log --oneline front

# Debe estar limpio (si no: commit o git stash)
git status

git switch master

# Rama nueva, nace de master
git switch -c viewer-tokens

# Copia SOLO ese commit (puedes poner varios hashes)
git cherry-pick a1b2c3d

# Abre un PR desde GitHub hacia el repo del autor
git push -u origin viewer-tokens

# Vuelves al laboratorio
git switch front
```

## Master igual que el del autor

```bash
# Una sola vez
git remote add upstream https://github.com/javillegasna/oxedi.git

# Descarga todo su historial, ramas y commits más recientes a tu computadora (verificas)
git fetch upstream

# 
git switch master

# Fusiona los cambios que trajo el comando `fetch` desde el `master` del repositorio original (`upstream/master`) hacia tu propio `master` local
git merge --ff-only upstream/master
# fast-forward only: Le indica a Git que solo haga la mezcla si se trata de una línea de tiempo directa y lineal. Si detecta que tú hiciste cambios locales que chocan con los del autor, el comando se detiene por seguridad para que no sobrescribas nada por error.
```

También:

```bash
# Descárga todo: ramas, commits y etiquetas
git fetch origin

git switch master

# Toma una rama específica de todo lo que trajiste y mézclala con la rama en la que estoy parado.
git merge --ff-only origin/master
# --ff-only es la protección: o avanza sin mezclar nada, o se detiene con un error y no cambia nada.

git switch front
```

Luego

```bash
git config pull.rebase true

git pull
git push
```

`git config pull.rebase true`

Cuando tu rama y la del remoto tienen cada una commits que la otra no tiene, `git pull` tiene que reconciliarlas, y hay dos formas:

- **Merge:** crea un commit extra que une las dos historias.
- **Rebase:** levanta tus commits locales, actualiza tu rama al punto del remoto y los vuelve a poner encima. La historia queda en línea recta, sin commit de unión.

Esa configuración le dice a Git que use rebase por defecto en este repo (queda guardada en `.git/config`; con `--global` valdría para todos). Dos cosas a saber:

- **Cambia el hash de tus commits.** Tu `dff59ef` ahora es otro (el de `98486c8` o similar). Es normal.
- **Solo es seguro con commits que aún no subiste.** Reescribir commits que otros ya descargaron causa problemas. Aquí no pasa nada, porque `front` es solo tuya.



```bash
python3 -m http.server 8001 --directory viewer

# Escucha en `0.0.0.0`, es decir, en todas las conexiones de tu computadora. Cualquier otro dispositivo en tu misma red conectado a tu WiFi podría entrar a `http://tu-ip:8001`.

python3 -m http.server 8001 --bind 127.0.0.1 --directory viewer

# Solo escucha en el modo “local”: únicamente tu computadora puede abrirla.
```

