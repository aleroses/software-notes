# Git y GitHub

## Enlaces y recursos:

- [Infografías en Twitter (X)](https://twitter.com/alerxses)
- [Notas en GitHub](https://github.com/aleroses/Platzi/blob/master/DW/1-basico/5-git-github/git-github.md)
- [Descargar Infografías](https://www.dropbox.com/scl/fo/9dwgw4vt77378wngci80w/AL3k_3O6Z_qZr6xTrveXpek?rlkey=rp0b5qs86uq50ghn6v9hbd7de&st=7fowehsc&dl=0)
- [Ver carpeta Infografías](https://www.dropbox.com/scl/fo/54d69ya3y99x2vqvh7vfn/AD7TJBg8vbU9MXXAxvaM_Ug?rlkey=elhrjjzgnry3obgv9qrmw8muk&st=p7znvypq&dl=0)

## 1. ¿Qué es Git?

Sistema de control de versiones.

## 2. GitHub

Red social para desarrolladores que permite guardar y compartir tus proyectos.

## 3. ¿Por qué usarlo?

- Para tener control de tus avances.
- Para poder retroceder en caso de errores.
- Para tener diferentes versiones de un proyecto.

## 4. CLI

Interfaz de línea de comandos.

- cd
- ls
- pwd
- touch
- mkdir
- rm -rf
- clear

## 5. Configuración

```bash
- git config --list
- git config --global user.name "Ale Roses"
- git config --global user.email "aleroses@mail.com"

# Configurar un repositorio como local
- git config --local user.email "email"
```

## 6. Primer repo con Git

```bash
- mkdir git-tests
- cd git-tests

# Inicializar un nuevo repo
- git init 👈👀
```

Git crea una nueva carpeta oculta llamada ".git". Esta carpeta contiene toda la información necesaria para que Git funcione.

- Historial de versiones
- Ramas
- Archivos de configuración
- Otros elementos internos

```bash
- ls -al
- code .

# Información sobre el estado actual del repositorio
- git status 👈👀🔴🟢
```

## 7. Analizar cambios

```bash
- git show algo.txt
- git log algo.txt
- git diff 1342342424242 43242423424
```

📌 Si solo hacemos commit sin añadir un comentario nos aparecerá un editor llamado Vim, para este caso necesitas saber lo siguiente:

Para escribir: **Esc + i**
Dejemos un comentarios, esto es muy importante
Para salir: **Esc + shift + zz**

## 8. **Staging**

Zona de preparación.

![stag](https://i.postimg.cc/cLss2WDG/10-Ciclo-b-sico-de-trabajo-en-Git.png)

## 9. Ramas

![branch](https://i.postimg.cc/m23LmkyS/11-1-Qu-es-un-Branch-rama-y-c-mo-funciona-un-Merge-en-Git.png)

## 10. Volver en el tiempo

Paso 01:

```bash
- git log
- git checkout 83d73c4a2eb79az10a40b1309a algo.txt
- git status

# Con esto el cambio hecho con checkout se vuelve permanente.
- git add .
- git commit -am "mensaje"
```

Paso 02:

```bash
# Habiendo usado git checkout opción 1, la opción 2 nos regresa a la versión más reciente registrada en el repositorio, a la ultima versión antes de haber hecho checkout.
git checkout master algo.txt
```

## 11. Flujo de trabajo básico con un repositorio remoto

En caso de cambiar de computador.

![Flujo basico](https://i.postimg.cc/7P0wLhdy/14-1-Esquema-del-Flujo-de-trabajo-b-sico-con-un-repositorio-remoto.png)

## 12. Introducción a las ramas o branches de Git

![Branch](https://i.postimg.cc/qMr060H6/15-2-Introducci-n-a-las-ramas-o-branches-de-Git.png)

```bash
- git branch nameBranch
- git checkout nameBranch

# Crea y cambia de rama
- git checkout -b nameBranch
```

📌 Cada vez que estés en una rama no olvidar realizar `add` y `commit -am` a los cambios realizados en cada rama correspondiente.

## 13. Fusión de ramas con Git merge

![Merge](https://i.postimg.cc/0Nzq1yDF/16-2-Fusi-n-de-ramas-con-Git-merge.png)

```bash
- git checkout master
- git merge development

# Eliminar ramas
- git branch -D nameBranch
```

Master / Amo

## 14. Uso de GitHub

Creamos un nuevo repositorio.

```bash
- git remote add origin url
- git remote -v

# Comando super importante 👀👇🔥
- git pull origin master --allow-unrelated-histories

# Enviar cambios
- git pull origin master
```

✨Para cambiar el nombre de un repositorio remoto, usar el siguiente comando:

```bash
# Change remote name from 'origin' to 'destination'
$ git remote rename origin destination
```

[Uso de GitHub](https://github.com/aleroses/software-notes/blob/master/DW/1-basico/005-git-github/git-github.md#19-uso-de-github)

## 15. Llaves públicas y privadas

Las llaves públicas y privadas nos ayudan a cifrar y descifrar nuestros archivos de forma que los podamos compartir sin correr el riesgo de que sean interceptados por personas con malas intenciones.

![ssh](https://i.postimg.cc/G2Yw9gMj/21-1-Configura-tus-llaves-SSH-en-local.png)

## 16. Configura tus llaves SSH en local

```bash
# Usamos Email de GitHub
- git config -l
- git config --global user.email "algo@gmail.com"

# Generar llave
- ssh-keygen -t rsa -b 4096 -C "algo@gmail.com"
# Alternativa
- ssh-keygen -t ed25519 -C "your_email@example.com"

# Ver las llaves
C:\Users\aleroses\.ssh

# Revisar encender el servidor de llaves SSH de tu computadora
- eval $(ssh-agent -s)

# Agregar llave privada al servidor 📌 ~ alt + 126:
- ssh-add ~/.ssh/id_rsa
```

[Configuración](https://github.com/aleroses/software-notes/blob/master/DW/1-basico/005-git-github/git-github.md#21-configura-tus-llaves-ssh-en-local)

## 17. Conexión a GitHub con SSH

Añadir llave pública en GitHub, para esto necesitas copias la llave pública de tu computadora:

`C:/users/oneuser/.ssh`

1. Ir al perfil de GitHub :octocat:
   1. Settings
   2. SSH and GPG Keys
   3. New SSH Key 🟩
   4. Title: Laptop de educación de Platzi
   5. Key: Pegar llave
   6. Add SSH key
2. Obtener URL SSH
   1. En GitHub :octocat:
   2. Your repositores
   3. Hyperblog
   4. Code: 🟩 Clone
   5. SSH -> Copiar

```bash
# Actualizar URL de HTTPS a SSH
- git remote -v
- git remote set-url origin url-ssh-repo-de-github

# Si es la primera vez que añades una URL utiliza el comando: Ver tema: 19 y 21
- git remote add origin url
```
