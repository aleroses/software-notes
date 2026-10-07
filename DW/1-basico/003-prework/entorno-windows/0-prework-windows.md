# Curso de Prework: Configuración de Entorno de Desarrollo en Windows

> Ricardo Celis

## **1.** Qué es el navegador?

Funciona gracias a https  

- HTML
- CSS
- JS

Versiones de Google Chrome

- Canary
- **Dev**
- Stable

Edge y sus DevTools

Navegador Firefox Developer Edition

Ver extensiones para Google Chrome [[vsc-chrome]]

## **2.** Descarga e instala un navegador web: Chrome Dev

[Enlace de Descarga](https://www.google.com/intl/es_us/chrome/dev/)

## **3.** Manejo básico de las DevTools

Podemos entrar a los settings de Chrome y cambiar el idioma: No olvides darle a **Relaunch** para efectuar cambios.

[Chrome settings](chrome://settings/languages)

Podemos instalar extensiones útiles: 

- Toggle JavaScript 
- Dev tools
- Lighthouse

[Chrome web store](https://chromewebstore.google.com/?hl=es)

Herramientas de desarrollador 
- Ctrl + Shift + i

## Quiz

### ¿Qué provee la herramienta Windows Subsystem for Linux?

- La transición entre plataformas Windows y Linux

### ¿Cómo se denomina la extensión que permite conectar y desconectar rápidamente el JavaScript en tu página web?

- Toggle JavaScript

### ¿Qué hace la herramienta Google Lighthouse?

- Automáticamente comprueba la calidad de las páginas web

### ¿Qué plataformas se unifican con Windows Subsystem for Linux?

- Windows y Linux

## **4.** Instalando VSCode

[Visual Studio Code](https://code.visualstudio.com/)  

[[atajos]]

## **5.** Extensiones Visual studio code

Para abrir el panel de extensiones también puedes usar `Ctrl + Shift + X`

- Prettier - Code formatter
- Color Highlight
- Highlight Matching Tag
- ESLint
- CSS Peek
- Live server
- Path intellisense
- Auto rename tag
- Material Icon theme
- Code Spell Checker
- WSL 👈👀 Instalar previo instalación de WSL
- Node Require
- Remote development

### Cómo usar Live Server en proyectos reales de HTML y CSS

En vsc: Clic derecho sobre html - Run Live Server   


## **6.** ¿Qué es Windows Subsystem for Linux?

El Subsistema de Windows para Linux permite a los desarrolladores ejecutar un entorno de GNU/Linux, incluida la mayoría de herramientas de línea de comandos, utilidades y aplicaciones, directamente en Windows, sin modificar y sin la sobrecarga de una máquina virtual tradicional o una configuración de arranque dual.

[Fuente](https://learn.microsoft.com/es-es/windows/wsl/about)

Verificar w10: CMD: `winver`     
Versión 2004 (Compilation SO 19041, 450) mínimo   

## **7.** Configurar Windows 11 para soportar la instalación de WSL

Entramos a la tienda de Windows y descargamos: 

- Windows Terminal

### Instalación de Windows Subsystem for Linux

Seguir pasos:   
[Documentación](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

Power Shell:   
Clic derecho ejecutar como administrador 👈👀
`wsl --install`

![Powershell](https://i.postimg.cc/g2dYkFxJ/1-wsl-install.png)

> Si ejecutar Power Shell sin ser Administrador te dará el siguiente error: 
**La operación solicitada requiere elevación**   

### En caso de conflictos o errores 

Power Shell: Abrir como administrador 

```bash
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform //all /norestart
```

Buscamos nuestro Windows Terminal 🔽 y elijes ubuntu, en caso de errores googlea el error.

## **8.** Ubuntu en WSL

### Instalar Ubuntu tienda Microsoft

![Ubuntu](https://i.postimg.cc/jSbsdW8P/7-canonical-ubuntu.png)   
Reiniciar pc  

![Config Ubuntu](https://i.postimg.cc/Y2ncK9V2/7-config.png)

UNIX username: Ubuntu
Ubuntu

🔥 **Configuración de Ubuntu 22.04.1 LTS**     
Usar las flechas y luego enter   

![Idioma](https://i.postimg.cc/JtwZdFyB/7-config-ubuntu-22lts.png)    
Done

![Password](https://i.postimg.cc/MTFy1Hq5/7-config-ubuntu-22lts-password.png)     
Done

![Montaje](https://i.postimg.cc/Y0LQR7SH/7-montaje.png)     
Done

![Completed](https://i.postimg.cc/xCCvkMDq/7-completed.png)    
Done


📌 Error:     
- Paso 01: https://answers.microsoft.com/en-us/insider/forum/all/how-to-enable-the-windows-subsystem-for-linux/16e8f2e8-4a6a-4325-a89a-fd28c7841775  
	- **Habilitar el modo de desarrollador en Windows 10** 
	- Características de windows 
	- Reiniciar 
- Paso 02: https://www.youtube.com/watch?v=7P039GotVyY
	- `0x80370102` The virtual machine could not be started because a required feature is not installed.
	- https://made4geek.com/error-0x80370102-the-virtual-machine-could-not-be-started-because-a-required-feature-is-not-installed-wsl-2-code-example/

### Configuración de Ubuntu en WSL

- pwd: muestra posición actual con posiciones anteriores
- cd : change directory, retrocede al Home
	- cd ..: retrocede una posición 
	- cd /
	- cd ~
	- cd /home/Ubuntu: me lleva a esa posición
	- cd ../..
	- cd mnt: Cambiar de disco o partición    
		Desde aquí puedo cambiar al disco C o D
	- cd d
- ls: muestra solo posición actual


Para acceder al disco c
- cd /
- pwd
- ls
- cd mnt
- ls
- cd c
- ls
- cd Users
- ls
- cd usuario/Desktop
- ls

📌 alt + 126 = ~


Crear carpeta de trabajo:       
- cd ~    
	Todos los proyectos deben estar dentro de ubuntu
- sudo mkdir personalProjects    
	sudo otorga permisos admin
- ls    
- mkdir proyectoDemoCursoPrework    
	Crea una carpeta
- ls   
- touch index.html    
	Crea un archivo
- ls   
- mv index.html proyectoDemoCursoPrework   
	Primero coloca el archivo a mover y luego la carpeta destino
- ls
- mv proyectoDemoCursoPrework personalProjects
- ls
- cd personalProjects
- ls
- cd proyectoDemoCursoPrework
- code .
- code .

## **9.** Instalación de VirtualBox

[Descargar VirtualBox](https://www.virtualbox.org/wiki/Downloads)   

Windows hosts 👈👀

[Descargar Ubuntu](https://releases.ubuntu.com/)

## **10.** Instalando Ubuntu en una máquina virtual

Buscar un tutorial actualizado :3

Ver nota de Obsidian [[1-virtual-box#Instalación]]

## **11.** Comandos básicos de la terminal

Abrir Ubuntu Terminal      
- cd ~
- ls
- cd personalProjects
- ls
- cd proyectoDemoCursoPrework
- ls
- code .

Hacer algunas cosas en html y activar el server
con click derecho

- cat index.html 
	Muestra el contenido de los archivos
- man cat
	Para revisar el manual de uso de cat
- q para salir

- cd ~    


## **12.** Instalación de Node

- sudo apt-get update      
	Gestor de paquetes para instalar
	Contraseña   
	Cargar   
- sudo apt-get update   
- sudo apt-get upgrade    
	Para aplicar las actualizaciones
- y

Instalar algo nuevo   
- sudo apt install nodejs
	- Y
- node -v
- sudo apt install npm
	- y

Actualizar nodejs
- sudo npm install -g n
- sudo n latest
- reset

### Cómo configurar tu primer proyecto en React.js

- clear     
	Limpiar terminal
- cd personalProjects
- ls
- npx create-react-app test    
	Instala archivos y elimina el instalador
- cd test
- npm start

Abrir otra terminal    
Si queremos detener la ejecución del live server : control c
- code .

Entramos a la carpeta dentro de Visual     
-> src -> App.js -> Editamos -> Guardar control s

Volvemos a encender el server

Dentro de VS - Terminal -> new terminal
- npm start

En caso algún error en la terminal de Linux:    
- sudo chown -R ubuntu ~/personalProjects

## **13.** Instalación de Python

- sudo apt install software-properties-common
- sudo add-apt-repository ppa:deadsnakes/ppa
- sudo apt update
- sudo apt install python3.8 
- python3 --version
- clear
- python3
- num1 = 1.99
- num2 = 2.01
- suma = num1 + num2
- print('El resultado: {0} y {1}: {2} '.format(num1, num2, sum))

## Quiz

### ¿Qué se usa para instalar Ubuntu sin problemas?

- Windows Subsystem for Linux

### ¿Qué hace el comando `dism.exe /online /enable-feature -- featurename: virtual machine platform con la opción all no-restart`?

- Habilita la plataforma de Windows para máquinas virtuales

## **14.** Instalando Git

Para borrar necesitas estar en su ubicación exacta

Borrar un repositorio / directorio      
- rm nombreArchivo.extension 

Borrar carpeta vacía    
- rm -d nombreCarpetaVacia

Borrar directorio con contenido    
- cd ..
- rm -rf test
- ls

Si revisamos nuestro Visual la carpeta ya no estará 
Así que el paso que sigue es:   
- File
- close folder

🔥 Instalar Git   
- cd ..
- clear
- git --version

En caso no tenerlo instalado:   
- sudo apt-get update
- instala
- sudo apt-get upgrade
- sudo apt install git

También:
- sudo apt-get install git-all

Ver notas en Obsidian de la instalación:     
[[git-github#5. Instalando Git en Linux]]

Crear cuenta [GitHub](https://github.com/)

## **15.** Vinculando nuestra llave SSH en GitHub

En la terminal    
- clear
- ssh-keygen -t rsa -b 4096 -C correo GitHub    
	Enter
	Contraseña de Ubuntu
- eval "$(ssh-agent -s)"     
	Ver agente corriendo
- clear  
- ssh-copy-id `GitHub-email`
- /usr/bin/ssh-copy-id: INFO: 
	Source of key(s) to be installed: "/home/ubuntu/.ssh/id_rsa.pub"
- cd ~/.ssh
- ls
- cat id_rsa.pub

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDTkPJTn4inOyC8oRKMNFi73M/CIqExdruf9h5KiH0UvdzNAfjzohJDLJ6cdgx6rDtJVEa7AEoDB08r5xMcmwrVPJeDP6Robldc3053WxtO2w9zgoFtm41/rDMNT6uP6sjh6bI7kgz1hLRGbZ0sWNKZH/vnagVLSXoVRY/R1RFAe/cfrTJRg5j8e4b3nw/mGlsOX3PN7GwmBpVM4M7dzka/oPJiwSV6/jVy1m3JtSgvOn7xoupmSRh3kG1mM1KFsURwVa6iaBUuo0rPb60oOZgwyD5awnKOVRw5gNzNpl7noqdrlWP4YHmQT3g5eTAsxU4pDF6qlVBLGo+mS82voTo9XIeFzd9S+G6bmtdb0J+W83D/qdTCQyP9hh/JAdJFiQM5LyjnVFYPRXu+kkGEl54VlRd3ZY8j+9JrHzmNWoR44cjz1+WilrqfDHMgcyqRdSHA2+vL8ad1u1i9LmHe8ZhYF5BB7yfLXuYBKJ6UaPwI1c0rsBJDrp5qdQByUhV0URLPPNk4c3/4WdEHIy+H1RQkxfJIWAtaDbemZYjwDkz7zfmtW11nH0AaysvEvT/sV081r5gGmyl1ACOnzPYsWt16jypUaq9lzbJD6zG75EyZK4F/7mxjJQg0T14jbaZ4Ubxlzit8wUv4qe7tHwJtGcJQgTyOKrfr0pcK9Ux5f7UDqQ== aleroses@outlook.com

- Copiar clave

Vamos a GitHub   
- Entrar en avatar o foto de cuenta
- Settings
- SSH and GPG keys
- New SSH key
- Copiar key / llave 
- Title: Llave curso Prework
- Add SSH key
- No me pidio contraseña :v

Ver apuntes de Git y GitHub    
[[git-github#22. Conexión a GitHub con SSH]]

### Forma mas actual 

```bash
- ssh-keygen -t ed25519 -C "ale@mail.com"
- Enter :3
- passphrase: opcional dar enter
- eval "$(ssh-agent -s)"
- ssh-add ~/.ssh/id_ed25519
- Enter passphrase: Si no creaste uno solo dale enter

# Copiar el public key del SSH
- cat ~/.ssh/id_ed25519.pub
ssh-ed25529 sfsadfsalklljlsdffdsfkkfjsl 👈👀
```

El correo que aparece al crear las llaves debe ser el mismo con el que creaste tu cuenta en GitHub.

#### Agregar key en GitHub

- Settings 
- SSH and GPG keys
	- SSH keys: New SSH key
	- Title: New NameWSL
	- Key: pegamos la llave
	- ✅ Add SSH key

## **16.** Subir tu primer repositorio

```bash
En la terminal ver nombre de proyecto:  
- ls
- cd personalProjects
- ls

Configurar Git 👈👀
- git config --global user.email "aleroses@outlook.com"
- git config --global user.name "Ubuntu user"
- git config --edit --global

Ahora sí...
- git init
- git add .
- git commit -m "first commit"
- clear
```

En GitHub    
- Repositories - New
- Repository name -> MyWeb
- Description -> Repositorio para pruebas de configuración SSH 
- Public
- Creating repository

```bash
# Creamos la conexión remota
- git remote add origin git@github.com.blablabla
- git remote -v

# Revisar si tu rama se llama main o master
- git push origin master
```

Hacer pequeños cambios en el html y enviemos cambios a GitHub.

```bash
# En la terminal   
- git status
- git add .
- git commit -m "Nuevo cambio"
- git push origin master
```

Actualizar GitHub y ver los cambios     
- Entramos en index.html
- Hay dos commit

Ver resumen de Git y GitHub en Obsidian    
[[git-github#19. Uso de GitHub]]

## Quiz

### ¿Cómo se agregarán todos los archivos al repositorio?

- `git add .`

### ¿Cuál es el primer comando para iniciar un repositorio de GitHub?

- `git init`

### ¿Qué comando agrega todos los archivos al repositorio?

- `git add`

### ¿Cómo inicializamos nuestro primer repositorio de GitHub?

- Hacemos `git init`

## **17.** Power toys

[Power Toys](https://learn.microsoft.com/en-us/windows/powertoys/)

También lo puedes descargar desde la tienda de Windows. 

## Quiz

### ¿Cuál de las siguientes opciones no es una forma de layout?

- Esquema

### ¿Qué características podemos añadir en Fancy Zones?

- Prioridad y cuadrícula

### ¿Qué combinación de teclas nos permite abrir el Editor de Fancy Zones?

- Win + Shift + Ñ

### ¿Cuál es uno de los parámetros para ajustar las zonas de apresamiento de Fancy Zones?

- Margen

### ¿Cómo se llama el conjunto de utilidades que podemos instalar en Windows para mejorar nuestra experiencia y aumentar nuestra productividad?

- PowerToys

## Examen 📌

<details>
	<summary>Haz clic para ver los resultados 👀</summary>
	<br/>

1. ¿Qué es Ubuntu?

	- 📌 Una distribución Linux, es de las más usadas, tiene una terminal potente y fácil de comenzar a utilizar

2. ¿Por qué la virtualización puede ser más lenta que soluciones integradas como WSL2?

	- 📌 Debido a que al virtualizar estamos reservando recursos para que sean ejecutados por la máquina virtual y además estamos corriendo el software encargado de la virtualización misma, esto puede ser intensivo de RAM, disco duro, y procesador

3. ¿Cuáles son algunos de los principales usos de Python?

	- 📌 Desarrollo backend, Data Science, IA, entre otros

4. ¿Qué es GitHub?

	- 📌 Un sitio web creado para que diferentes desarrolladoras y equipos de trabajo puedan subir sus repositorios de Git y manejar de forma eficiente y colaborativa, en la nube su proceso de desarrollo

5. ¿Qué es VSCode?

	- 📌 Visual Studio Code (VS Code) es un editor de código fuente desarrollado por Microsoft, es código abierto, y es multiplataforma, además es el que usarás en el resto de cursos de desarrollo web

6. ¿Por qué es importante saber utilizar Git?

	- 📌 Porque es el sistema de control de versiones usado por de facto en la industria tech, nos permite al usarlo con un sitio como Github o similares colaborar y trabajar en equipo

7. ¿Quíén fue el creador de Git?

	- 📌 Linus Torvalds, el mismo creador de Linux

8. ¿Qué es una terminal?

	- 📌 Un software que nos permite interactuar directamente con nuestra computadora a través de comandos y texto, tal como lo hacemos tradicionalmente a través de ventanas, íconos, menús y botones en Windows

9. ¿Para qué nos sirve utilizar WSL2?

	- 📌 WSL2 nos permite tomar todas las grandes ventajas y facilidades que siempre han existido de desarrollar en Linux, como sus terminales, sin tener que acostumbrarnos a un Sistema Operativo distinto a que usamos día a día, quizás tienes videollamadas, y en Ubuntu por ejemplo puede ser difícil compartir audio, video, etc. Así que esta fue la forma de Microsoft de ser un sistema útil para desarrollar software que tradicionalmente se hacía en Linux dando la practicidad de Windows

9. Node.js es:

	- 📌 Un intérprete de JavaScript, que nos permitirá ejecutar JavaScript en nuestra terminal y no solo en el navegador, se utiliza principalmente para servidores

11. ¿Qué es Virtual Box?

	- 📌 Un software de virtualización que nos permitirá instalar distintos sistemas operativos virtualizando el entorno en el que estamos, compartiendo recursos con la máquina host

12. ¿Por qué razón utilizamos Google Chrome?

	- 📌 Por ser el navegador más utilizado, es importante visualizar nuestros proyectos web como los verán la gran mayoría de usuarios

13. ¿Qué es WSL2?

	- 📌 Windows Subsystem for Linux2, un subsistema en Windows que ejecuta el kernel completo de Linux, permitiéndonos ejecutar cualquier distribución de Linux que necesitamos directamente en Windows

14. ¿Para qué nos sirven las DevTools?

	- 📌 Para facilitar el desarrollo de nuestros proyectos web, buscar y corregir errores, entender el rendimiento de nuestro sitio

15. ¿Qué es Git?

	- 📌 Git es un sistema de control de versiones y manejo de repositorios, nos permite manejar el progreso en el desarrollo de nuestro software, probar cosas nuevas, regresar a versiones anteriores, y demás
</details>
