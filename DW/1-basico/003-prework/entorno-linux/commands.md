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

