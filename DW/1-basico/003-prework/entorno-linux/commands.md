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

