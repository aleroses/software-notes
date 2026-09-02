# Commands

## React

```bash
# Crear un proyecto con CRA:
npx create-react-app my-app
npm start
```

## Renombrar una carpeta

```bash
# Renombrar una carpeta:
mv nombre_actual nuevo_nombre
```

## Eliminar un programa 

```bash
# Verificar antes de eliminar un programa
dpkg -l | grep <nombre_del_programa>

# Eliminar el programa y sus archivos asociados
sudo apt remove --purge <nombre_del_programa>
sudo apt autoremove --purge <nombre_del_programa>

# También en Debian:
sudo apt purge --auto-remove google-chrome-stable
```

## Instalar un programa

```bash
sudo apt install ./google-chrome-stable_current_amd64.deb
```

## Abrir el administrador de archivos

```bash
# Instalar nemo
sudo apt-get install nemo

# Abrir derectorio actual
nemo

# Abrir directorio de inicio
nemo ~
```

---

## Ordenar carpetas por tamaño

```bash
du -h --max-depth=1 "/path" | sort -h
```

## Ver la calidad de video

```bash
# Información general del archivo
ffprobe -hide_banner nombre_video.mp4

# Solo resolución del video: ancho=640, alto=360 → calidad 360p.
ffprobe -v error -select_streams v:0 -show_entries stream=width,height -of csv=s=x:p=0 nombre_video.mp4
ffprobe -v error -select_streams v:0 -show_entries stream=width,height -of csv=p=0 archivo.mp4


# Bitrate del video: a mayor bitrate, mayor calidad en general
ffprobe -v error -select_streams v:0 -show_entries stream=bit_rate -of default=nw=1:nk=1 nombre_video.mp4

# FPS (cuadros por segundo)
ffprobe -v error -select_streams v:0 -show_entries stream=r_frame_rate -of default=noprint_wrappers=1:nokey=1 nombre_video.mp4

# Resumen corto
ffprobe -v error -show_format -show_streams nombre_video.mp4
```

Más detalles:

```bash
ffprobe -hide_banner -show_format -show_streams "name.mkv"
ffprobe -v error -select_streams v:0 -show_entries stream=codec_name,profile,width,height,bit_rate,avg_frame_rate,color_space,color_transfer,color_primaries -of default=noprint_wrappers=1:nokey=0 "name.mkv"

ffprobe -v error -show_entries format=size,duration,bit_rate -of default=noprint_wrappers=1:nokey=0 "name.mp4"
ffprobe -v error -select_streams a:0 -show_entries stream=codec_name,channels,bit_rate,language -of default=noprint_wrappers=1:nokey=0 "name.mp4"
```

## Detectar y borrar automáticamente los videos con calidad ≤ 480p:

### Buscar y listar los videos de ≤ 480p

```bash
find /path/path -type f -name "*.mp4" -o -name "*.mkv" | while read -r f; do
    res=$(ffprobe -v error -select_streams v:0 -show_entries stream=height -of csv=p=0 "$f")
    if [ "$res" -le 480 ]; then
        echo "$f → ${res}p"
    fi
done
```

### Eliminar automáticamente los de ≤ 480p

```bash
find /path/path -type f \( -name "*.mp4" -o -name "*.mkv" \) | while read -r f; do
    res=$(ffprobe -v error -select_streams v:0 -show_entries stream=height -of csv=p=0 "$f")
    if [ "$res" -le 480 ]; then
        # echo "Eliminando: $f (${res}p)"
        rm "$f"
    fi
done
```

### Mover a otra carpeta para revisar antes de borrar

Rutas escapando espacios con \

```bash
mkdir -p /path/path/path\ path/path/path\ path/path/baja_calidad
find /path/path/path\ path/path/path\ path/path/path -type f \( -name "*.mp4" -o -name "*.mkv" \) | while read -r f; do
    res=$(ffprobe -v error -select_streams v:0 -show_entries stream=height -of csv=p=0 "$f" | tr -d '[:space:]')
    if [ "$res" -le 480 ]; then
        # echo "Moviendo: $f (${res}p)"
        mv "$f" /path/path/path\ path/path/path\ path/path/baja_calidad
    fi
done
```

Rutas con comillas:

```bash
mkdir -p "./baja_calidad/"

find "./" -type f \( -name "*.mp4" -o -name "*.mkv" \) | while read -r f; do
    res=$(ffprobe -v error -select_streams v:0 -show_entries stream=height -of csv=p=0 "$f" | tr -d '[:space:]')
    if [ "$res" -le 480 ]; then
        # echo "Moviendo: $f (${res}p)"
        mv "$f" "./baja_calidad/"
    fi
done
```

### Tabla de referencia de resoluciones de video más comunes

| Nombre / Calidad    | Resolución Horizontal (16:9 aprox.) | Resolución Vertical (9:16 aprox.) |
| ------------------- | ----------------------------------- | --------------------------------- |
| **144p** (muy baja) | 256x144                             | 144x256                           |
| **240p** (baja)     | 426x240                             | 240x426                           |
| **360p** (SD)       | 640x360                             | 360x640                           |
| **480p** (SD)       | 854x480                             | 480x854                           |
| **720p (HD)**       | 1280x720                            | 720x1280                          |
| **1080p (Full HD)** | 1920x1080                           | 1080x1920                         |
| **1440p (2K)**      | 2560x1440                           | 1440x2560                         |
| **2160p (4K)**      | 3840x2160                           | 2160x3840                         |

## Reproducir una lista de videos

Tengo esta lista de videos de una serie y se puede reproducir todo usando un comando.

```bash
ale ❯ tree -L 4
.
├── playlist.m3u
├── Young Sheldon (2017) Season 1 S01
│   ├── Young Sheldon (2017) - S01E01 - Pilot.mkv
│   ├── ...
│   └── Young Sheldon (2017) - S01E22 - Vanilla.mkv
├── Young Sheldon (2017) Season 2 S02
│   ├── Young Sheldon (2017) - S02E01 - A High-Pitched.mkv
│   ├── ...
│   └── Young Sheldon (2017) - S02E22 - A Swedish.mkv
├── Young Sheldon (2017) Season 3 S03
│   ├── Young Sheldon (2017) - S03E01 - Quirky.mkv
│   ├── ...
│   └── Young Sheldon (2017) - S03E21 - A Secret.mkv
├── Young Sheldon (2017) Season 4 S04
│   ├── Young Sheldon (2017) - S04E01 - Graduation.mkv
│   ├── ...
│   └── Young Sheldon (2017) - S04E18 - The Wild.mkv
├── Young Sheldon (2017) Season 5 S05
│   ├── Young Sheldon (2017) - S05E01 - One Bad.mkv
│   ├── ...
│   └── Young Sheldon (2017) - S05E22 - A Clogged.mkv
├── Young Sheldon (2017) Season 6 S06
│   ├── Young Sheldon (2017) - S06E01 - Four Hundred.mkv
│   ├── ...
│   └── Young Sheldon (2017) - S06E22 - A Tornado.mkv
└── Young Sheldon (2017) Season 7 S07
    ├── Young Sheldon (2017) - S07E01 - A Wiener.mkv
    ├── ...
    └── Young Sheldon (2017) - S07E14 - Memoir.mkv

8 directories, 142 files
```

Comando:

```bash
cd "/media/jellyfin/shows/young-sheldon"
find . -type f -iname "*.mkv" | sort > playlist.m3u
mpv --playlist=playlist.m3u --save-position-on-quit
```

Crea el archivo `playlist.m3u` y reproduce todo. Para retomar la reproducción otro día se debe ejecutar este comando:

```bash
cd "/media/jellyfin/shows/young-sheldon"
mpv --playlist=playlist.m3u --save-position-on-quit
```

## Comprimir carpetas

### `.zip`

```bash
zip -r "Course_Book.zip" "Course Book"
```

- `zip` → comando para comprimir.
    
- `-r` → comprime recursivamente todo el contenido de la carpeta.
    
- Entre **comillas** el nombre, porque puede que tus carpetas tengan espacios y puntos.
    
- Puedes cambiar el nombre del `.zip` a como quieras (yo lo puse con guiones bajos para que sea más limpio).


### `.rar`

Primero asegúrate de instalarlo:

```bash
sudo apt install rar unrar -y
```

```bash
rar a "Course_Book.rar" "Course Book"
```

- `rar a` → crea un archivo `.rar` (el `a` significa _add_).
    
- Entre comillas el nombre del `.rar` y la carpeta de origen (por los espacios).
    
- El `.rar` se genera en el directorio actual.
    

### Comprimir con contraseña en `.rar`

Para crear los `.rar` **con contraseña** usas la opción `-p`.

```bash
rar a -p1234 "Course_Book.rar" "Course Book"
```

- `-p1234` → establece la contraseña `1234`.
    
- Si no pones la contraseña junto (`-p` sin nada), el sistema te la pedirá al momento.
    
- Al descomprimir (`unrar x archivo.rar`) pedirá la contraseña `1234`.
    
- Si alguien abre el `.rar` con un gestor de archivos, tampoco podrá extraer sin la clave.
    

### Ocultar listado de archivos dentro del `.rar`

Cuando creas un `.rar` con contraseña, tienes **dos opciones de protección**:

1. Proteger **solo la extracción** (lo que ya hicimos con `-p1234`)
	- El `.rar` se crea normalmente.
    
	- Si alguien abre el archivo `.rar` (por ejemplo, con el explorador de archivos), podrá **ver la lista de archivos que contiene**, pero **no podrá extraerlos** sin la contraseña.
    
	
	Ejemplo:
	
	```
	English_Book_2016-Audio.rar
	 ├── 01_track.mp3
	 ├── 02_track.mp3
	 └── 03_track.mp3
	```
	
	👉 Aquí la lista de nombres se ve, pero no se pueden abrir ni extraer los archivos sin la clave.

2. Proteger **también el listado de archivos** (`-hp1234`)
	- Con esta opción, el `.rar` queda totalmente cifrado.
	    
	- **No se puede ver ni siquiera qué archivos contiene** hasta ingresar la contraseña.
	    
	- Si alguien intenta abrirlo, solo verá un archivo “vacío” o pedirá contraseña directamente.
	    
	
	Ejemplo:
	
	```
	English_Book_2016-Audio.rar
	 └── (contenido oculto hasta poner contraseña)
	```

#### 📌 Comandos

- Solo proteger la extracción (lo que ya probamos):
    

```bash
rar a -p1234 archivo.rar carpeta/
```

- Proteger también el listado de archivos:
    

```bash
rar a -hp1234 archivo.rar carpeta/
```

### Comprimir varias carpetas en `.zip`

Si todas tus carpetas están en un mismo directorio, puedes hacer:

```bash
for d in */; do
    zip -r "${d%/}.zip" "$d"
done
```

🔎 Explicación:

- `for d in */; do ... done` → recorre todas las carpetas del directorio actual.
    
- `"${d%/}.zip"` → crea un `.zip` con el mismo nombre de la carpeta.
    
- `-r` → incluye todo el contenido recursivamente.
    

### Comprimir varias carpetas en `.rar`

Primero asegúrate de tener instalado `rar`:

```bash
sudo apt install rar -y
```

Luego:

```bash
for d in */; do
    rar a "${d%/}.rar" "$d"
done
```

🔎 Igual que con `.zip`, pero genera un `.rar` por carpeta.

Si quieres que los nombres tengan guiones:

```bash
for d in */; do
    name="${d%/}"                # quitamos la barra final
    clean_name=$(echo "$name" | tr ' ' '_')   # reemplazamos espacios por "_"
    rar a "${clean_name}.rar" "$d"
done
```

```bash
for d in */; do
    name="${d%/}"                                # nombre de la carpeta
    clean_name=$(echo "$name" | tr ' ' '_' | tr '[:upper:]' '[:lower:]')  # espacios → "_" y todo en minúsculas
    rar a -r "${clean_name}.rar" "$name"
done
```

```bash
# Pasa de esto:
01 English grammar in use/
02 Practice book level 1/

# A esto:
01_English_grammar_in_use.rar
02_Practice_book_level_1.rar
```

### Si quieres proteger cada `.rar` con contraseña

```bash
for d in */; do
    rar a -p1234 "${d%/}.rar" "$d"
done
```

- Esto pondrá la contraseña `1234` a cada `.rar`.
    
- Si quieres que también oculte la lista de archivos: usa `-hp1234` en lugar de `-p1234`.
    
## Extraer archivos

### 1. Extraer en la misma carpeta

```bash
# Para rar
unrar x "material cambridge.rar"

# Para zip
unzip "material cambridge.zip"
```

- `x` → extrae manteniendo la estructura de carpetas.
    
- El contenido quedará en un subdirectorio (si el `.rar` lo tiene) o directamente en la carpeta actual.
    

### 2. Extraer en otra carpeta específica

```bash
# Para rar
unrar x "material cambridge.rar" "/ruta/de/destino/"

# Para zip
unzip "material cambridge.zip" -d "/ruta/de/destino/"
```

Ejemplo:

```bash
unrar x "material cambridge.rar" "~/Downloads/extracto/"
```

### 3. Si tiene contraseña

```bash
unrar x "material cambridge.rar"

unzip "material cambridge.zip"
```

Te pedirá la contraseña en la terminal.  
(En tu caso, si lo hiciste con `-p1234`, pones `1234`).

### 4. Ver el contenido sin extraer

```bash
unrar l "material cambridge.rar"

unzip -l "material cambridge.zip"
```

---

## ImageMagick

**ImageMagick** es una herramienta **de línea de comandos** (CLI) que sirve para **crear, editar, convertir y optimizar imágenes**.  
Admite **más de 200 formatos** (PNG, JPG, GIF, SVG, PDF, etc.) y es muy usada por desarrolladores, diseñadores y servidores web.

👉 Puedes:

- Cambiar tamaño (resize)
- Convertir de formato (jpg → webp, etc.)
- Optimizar o comprimir
- Aplicar efectos o filtros
- Procesar imágenes por lotes (muchas a la vez)

---

## ⚙️ Instalación

### 🔸 En Debian / Ubuntu / Linux Mint:

```bash
sudo apt install imagemagick -y
```

### 🔸 En macOS (con Homebrew):

```bash
brew install imagemagick
```

### 🔸 En Windows:

- Descarga el instalador desde 👉 [https://imagemagick.org/script/download.php](https://imagemagick.org/script/download.php)
    
- Durante la instalación, **marca la opción “Add to PATH”**.

## Uso básico

El comando principal es **`convert`** o, en versiones nuevas, **`magick`**.

> 🔸 En sistemas modernos, se usa así:  
> `magick [entrada] [opciones] [salida]`

### 1. Redimensionar una imagen

Por ejemplo, para crear versiones **responsive** (como querías para desktop, tablet y móvil):

```bash
magick imagen.png -resize 1024x494 imagen-desktop.png
magick imagen.png -resize 768x371 imagen-tablet.png
magick imagen.png -resize 480x232 imagen-mobile.png
```

💡 Si solo pones un valor (por ejemplo `-resize 480`), mantiene la proporción automáticamente:

```bash
magick imagen.png -resize 480 imagen-mobile.png
```

### 2. Convertir de formato

```bash
magick imagen.png imagen.webp
magick imagen.jpg imagen.png
```

Esto es útil para **optimizar tu web**, ya que formatos como `.webp` o `.avif` pesan mucho menos que `.png` o `.jpg`.

### 3. Comprimir una imagen

Reducir tamaño del archivo sin cambiar sus dimensiones:

```bash
magick imagen.png -quality 85 imagen-optimizada.jpg
```

_(El valor 85 es el porcentaje de calidad, ideal entre 70 y 90 para web.)_

### 4. Procesar varias imágenes a la vez

Por ejemplo, reducir todas las imágenes PNG en una carpeta:

```bash
for file in *.png; do
  magick "$file" -resize 800 "reducidas/$file"
done
```

## 🧰 Comandos útiles

|Acción|Comando ejemplo|
|---|---|
|Ver información de imagen|`identify imagen.png`|
|Crear miniatura|`magick imagen.png -thumbnail 200x200 thumb.png`|
|Agregar texto|`magick imagen.png -pointsize 20 -draw "text 10,50 'Hola'" salida.png`|
|Convertir a blanco y negro|`magick imagen.png -colorspace Gray salida.png`|
|Combinar imágenes|`magick input1.png input2.png +append salida.png`|

## 📦 Consejo para proyectos web

Puedes crear un pequeño script (por ejemplo, `resize.sh`) para generar automáticamente las tres versiones que usarás en HTML con `<picture>`:

```bash
#!/bin/bash
magick $1 -resize 1024 "desktop-$1"
magick $1 -resize 768 "tablet-$1"
magick $1 -resize 480 "mobile-$1"
```

Luego lo ejecutas así:

```bash
bash resize.sh imagen.png
```

Y tendrás:

```
desktop-imagen.png
tablet-imagen.png
mobile-imagen.png
```