# Instalar Debian (Dual Boot)

Ver [DEBIAN 12 + WINDOWS 11 | Instalación y configuración en Dual Boot](https://www.youtube.com/watch?v=UjBymf01Q0Q)

## Descargar ISO

Entra en [Debian](https://www.debian.org/)

More/Debian is an OS/Download/Download mirrors
Official USB/CD/DVD images of the "stable" release

DVD/USB

The following links point to image files which are up to 4.7 GB in size.

- amd64
- debian-13.1.0-amd64-DVD-1.iso

Comprobamos si es una ISO Original:

- SHA256SUMS

Entramos en PowerShell:

```bash
Get-FileHash 'C:/Users/username/ruta/debian..1.iso'
```

Comparamos con el que aparece en la web.

## Ventoy

Descargamos la herramienta para crear el USB booteable [Ventoy](https://www.ventoy.net/en/)

- Downloads
- ventoy-1.1.07-windows.zip
- Download Latest Version

> Nota: Antes de ejecutar Ventoy2Disk debes tener conectado un USB.

Descomprime y ejecuta `Ventoy2Disk` selecciona el USB con el que vas a trabajar y por ultima dale en Instalar.

Ahora solo arrasta la ISO descargada dentro del USB.

Tutorial de uso [USB MULTIBOOT: VENTOY](https://www.youtube.com/watch?v=DU6lKRYodmE)

## Crear espacio en Disco

Desde Windows entra a:

- `Crear y formatear particiones del disco duro`.
- Clic derecho sobre la unidad `C` o `D`
- Reducir volumen
- Tamaño del espacio que desea reducir
  - Escribe la cantidad en MB

## Bios

Entramos a la Bios usando `F2` con el USB conectado.

- Desactiva Secure Boot: Disabled
- Prioridad de arranque USB partition 2
- Guarda y reinicia

## Instalación de Debian

1. Graphical install
2. Language: English
3. Ubicación: Otros / ...
4. Layout keyboard
5. Nombre de la Máquina: Ghost
6. Nombre de dominio: Vacio
7. Clave de superusuario (root)
8. Nombre completo
9. Nombre de usuario para la cuenta: ale
10. Elija una contraseña para el nuevo usuario

## Método de particionado

Particionado de Discos

### Manual:

Busca el espacio que liberaste de tu partición C o D. En este espacio libre se crearan las particiones para Linux.

- 320 GB  Espacio Libre (Ejemplo) Dale enter
- Ha seleccionado particionar el dispositivo completo.
  - Sí

> Nota: Solo pueden haber 4 particiones primarias.

### EFI: fat32 /boot/efi gpt

- Escoge el espacio libre
- Crear una partición nueva
- Nuevo tamaño de partición:
  - 300 MB: EFI principio
  - Utilizar como: `Partición del sistema EFI`
  - Se ha terminado de definir la partición

---

#### Sección de dudas con EFI (Solo ignora)

##### 1. Si tienes Windows instalado

* No borres la partición EFI existente.
* En el instalador de Debian, selecciona “Particionado manual”.
* Busca una partición pequeña de tipo **FAT32**, tamaño **100–500 MB**, generalmente montada en `/dev/nvme0n1p1` o `/dev/sda1`.
* Selecciónala, elige:

  * “Usar como: sistema de archivos EFI (FAT32)”
  * “Punto de montaje: /boot/efi”
  * **No la formatees** (importante).

##### 2. Si no tienes partición EFI

* Crea una nueva:

  * Tamaño: 512 MB
  * Tipo: FAT32
  * Punto de montaje: `/boot/efi`
  * Marca “Espacio reservado para el sistema EFI” o “boot, esp”.

---

### Swap (no recomendado en SSD)

- Escoge el espacio libre
- Crear una partición nueva
- Nuevo tamaño:
  - 2/4 GB: swap primaria principio
  - Utilizar como: `Área de intercambio swap`
  - Se ha terminado de definir la partición

> Nota: Crear un archivo swap es preferible. Ver zram.

## / ext4
  
- Escoge el espacio libre
- Crear una partición nueva
- Nuevo tamaño:
  - 7 GB: Primaria Principio
  - Utilizar como: `Sistema de ficheros ext4 transaccional`
  - Punto de montaje: `/ - Sistema de ficheros raíz`
  - Se ha terminado de definir la partición

> Nota: `/` (raíz) | Sistema operativo y programas.

### /home ext4

- Escoge el espacio libre
- Crear una partición nueva
- Nuevo tamaño:
  - Dejar el tamaño restante primaria
  - Utilizar como: `Sistema de ficheros ext4 transaccional`
  - Punto de montaje: `/home - directorios personales de los usuarios`
  - Se ha terminado de definir la partición

Para culminar:

- Finalizar el particionado y escribir los cambios
- Desea escribir los cambios en los discos?
  - Si

> Nota: `/home` | Archivos personales, configuraciones, descargas, etc.

### Data?

- Elige el disco secundario
punto de montaje /usr
introducir manualmente
/data (ejemplo)
Se ha terminado de definir la partición
Finalizar el particionado y escribir los cambios en el disco

Si

## Ultimos pasos

País de la réplica de Debian:

- Estados Unidos
- deb.debian.org

Participar en las encuestas sobre uso de los paquetes?

- No.

Elegir los programas a instalar:

- [ x ] Entorno de escritorio Debian
- [ x ] GNOME
- ...
- [ x ] Utilidades estándar del sistema (Quitas todo menos esto)

> Nota: Si no quieres que GNOME te instale muchas cosas que no vas a usar quita:  
> `Entorno de escritorio Debian` y también  
> `GNOME` usando la `Barra espaciadora`.

## Terminar la instalación

La instalación se ha completa, solo quita el USB y continua.

## Grub

Si no quitaste las opciones:

- [ x ] Entorno de escritorio Debian
- [ x ] GNOME

Ya tienes todo listo para usar Debian, pero si quitaste esas opciones debes hacer lo siguiente:

- Entra en Debian GNU/Linux

```bash
portatil login: ale
Password: *****************

su
Password: *****************

# Actualizar paquetes (debes estar como root):
apt update && apt upgrade -y

# Instalar Gnome Core y gdm3:
apt install -y gnome-core gdm3

# Reiniciar la máquina:
/usr/sbin/reboot
```

## Modificar Sudo

```bash
su
Password: *****************

apt install -y htop
htop

# Ajustar el PATH para instalar paquetes .deb en Debian 12:
su
nano ~/.bashrc
```

Escribimos al final del archivo:

```bash
export PATH=$PATH:/usr/local/sbin:/usr/sbin:/sbin
```

Ahora:

- `Ctrl + O`: Guardar
- Enter
- `Ctrl + X`: Salir

```bash
# Aplicar los cambios
source ~/.bashrc

nano ~/.profile
```

Escribimos al final del archivo:

```bash
export PATH=$PATH:/usr/local/sbin:/usr/sbin:/sbin
```

Ahora:

- `Ctrl + O`: Guardar
- Enter
- `Ctrl + X`: Salir

```bash
# Aplicar los cambios
source ~/.profile
```

```bash
# Configurar el usuario:
apt install -y sudo

usermod -aG sudo nombreusuario
visudo
nombreusuario ALL=(ALL:ALL) ALL
exit
```

https://github.com/aleroses/software-notes/blob/master/DW/1-basico/003-prework/entorno-windows/remove-linux-dualboot.md
