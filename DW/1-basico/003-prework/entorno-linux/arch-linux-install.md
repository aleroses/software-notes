# Arch Linux Install

## 1. Descargar y verificar ISO

Entramos a la web oficial y nos vamos a Download.
- [Web Arch Linux](https://archlinux.org/)
- [Download Arch Linux](https://archlinux.org/download/)

Buscamos el Mirrow más cercano a tu locación para hacer la descarga, en caso de no estar tu país elige uno de **Worldwide** por ejemplo `rackspace.com`.

En **Index of /archlinux/iso/2025.07.01** necesitamos:

- `archlinux-2025.07.01-x86 64.iso`
- `sha256sums.txt`

Para validar la ISO nos vamos a la terminal:

```bash
# Windows: CMD
cd Downloads
dir 
## Copia el nombre del archivo
## archlinux-2025.07.01-x86_64.iso
certutil -hashfile archlinux-2025.07.01-x86_64.iso sha256
```

El **hash** que aparece debe ser el mismo al del archivo `sha256sums.txt` que se muestra en la web.

```
# Linux
cd ~/Descargas
sha256sum archlinux-2025.07.01-x86_64.iso
```

Ahora compara con el valor que aparece en el archivo `sha256sums.txt`. Si ambos coinciden, entonces la ISO es original y no fue alterada.

Para una verificación automática del archivo `sha256sums.txt`, puedes usar este método:

```bash
# Linux
## Descarga el archivo
wget https://mirror.rackspace.com/archlinux/iso/2025.07.01/sha256sums.txt
## También
grep archlinux-2025.07.01-x86_64.iso sha256sums.txt | sha256sum -c
## Compara
sha256sum -c sha256sums.txt
# Aparece
archlinux-2025.07.01-x86_64.iso: OK
archlinux-x86_64.iso: OK
```

📌 Nota: Si no estás en Linux puedes usar Git para usar los comandos anteriores.

## 2. Ventoy - Bootable USB drive

[Ventoy](https://www.ventoy.net/en/index.html) permite tener varias ISOs en un solo USB. Para usarlo solo arrastra la imagen ISO dentro del USB y listo.

También puedes usar [BalenaEtcher](https://etcher.balena.io/):
- Inserta una unidad USB
- Flash from file
- Selecciona el archivo ISO
- Select target: Selecciona el USB
- Flash!
- Espera, cierra y listo.

## 3. Crear partición desde Windows

Te vas a la barra inferior y das clic derecho **Administrador de discos**.

Disco 0: Dentro de la partición que deseas dividir (C:)
- Clic derecho 
- Reducir volumen
- Tamaño del espacio que desea reducir, en MB: 204800 (200 GB x 1024)
- Queda 200,00 GB No asigando.

## 4. Reiniciar y bootear

En ocasiones es **F2**, pero busca el botón específico para entrar a la **Bios**.

Mueve la unidad USB a la parte superior y guarda cambios.

Dentro de GNU GRUB:
- Arch Linux install medium (x86_64, x64 UEFI)

```bash
# Aumentar tamaño de letra
setfont ter-132n

# Cambiar layout a español
loadkeys es

# Conectar por WiFi
iwctl
device list
```

Si `iwctl` (de iwd) no te funciona, asegúrate de que tu WiFi está activada y visible:

```bash
iwctl
device list
# Salir
exit

# Verificar si el WiFi está bloqueado
rfkill list
# Mira si tu interfaz WiFi aparece (wlan0)
ip link
systemctl status iwd

# Si la red está bloqueada:
rfkill unblock wifi

# Reintenta
iwctl
device list
station wlan0 scan
station wlan0 get-networks
station wlan0 connect TU_SSID
```

Reemplaza `wlan0` por tu interfaz real si es diferente, puedes verla con `ip link`

```bash
# Levantar la interfaz WiFi
ip link set wlan0 up
iwctl
device list
station wlan0 scan
station wlan0 get-networks
station wlan0 connect TU_SSID
exit
# Verificar conexión
ping archlinux.org
```