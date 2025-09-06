Instalar Dock
- sudo apt update
- sudo apt install plank
- sudo apt-add-repository ppa:ricotz/docky
- sudo apt-get install plank

- sudo apt install fonts-terminus xfonts-terminus materia-gtk-theme papirus-icon-theme fonts-jetbrains-mono git

https://www.xfce-look.org/browse/

Ant themes
- Ant-Bloody.tar.xz

Gruvbox Plus Icon Pack

En la terminal:
- cd Downloads/
- tar -xf Ant-Bloody.tar.xz
- tar -xf gruvbox-plus-icon-pack.5.0.1.tar.gz
- sudo cp -r Ant-Bloody /usr/share/themes
- sudo cp -r Gruvbox-Plus-Dark/ /usr/share/icons/
- cd ~

https://github.com/diws1/xfce
- git clone https://github.com/diws1/xfce
- cd xfce/

Configurar Panel
- Click derecho
- Panel
- Panel Preferences
- Items
- + Add
- Whisker Menu ------
- + Add
  - Mover al inicio
- Applications Menu
  - Remove
- Separator ------
- + Add
  - Mover segundo
- repetir una vez mas
- Status Tray Plugin
  - Remove
- Notifications Plugins
  - Mover debajo de un separador
- Action Buttons
  - Remove

Ir al boton de menu 
- Log Out: Clic derecho añadir al panel
- Appearance: Añadir al panel
- File Manager: Añadir al panel
- Chrome / Firefox 
- Terminal

Mover desde el segundo Launcher hasta los separadores del inicio.

Clic derecho sobre el Panel
- Panel
- Panel Preferencies
- Panel 2
- Display
- Mode: Deskbar
- Lock panel: Desmarcar 
  - Mover a la izquierda
- Lock panel: Marcar 
- Items
- Añadir dos separadores y los items que necesites


Vamos a la carpeta xfce clonada
- View
- Show Hidden Files
- Renombrar las carpetas 
  - config
  - icons
  - wallpapers

Abrir terminal
- cd config/
- cd gtk-3.0/
- cp gtk.css ~/.config/gtk-3.0/
- cd ~/
- clear
- cd .config/gtk-3.0/
- sudo nano gtk.css

Panel 1 preferences
- Display
- Row size(pixeles): 22
- Ajustar según tus gustos
- Length (pixels): 1015

- Appearance
- Style: Solid Color
- Color
  - + #1b1b1b
  - arrastrar al minimo
- Icons
- Fixed icon size (pixels): 13px
- style: none

Panel 1 
- Hora: Click derecho
- propiedades
- Layout: Time Only
- Font: Terminus (TTF) medium
- Format: Custom Format
- %I:%M %p

Panel 2
- Row size 27

- Appearance
- Solid color
- 1b1b1b
- alminimo
- icons
- Fixed icon size (pixels): 20


Buscamos Appearance
- Style
- Material-dark-compact

- Icons
- Papirus-Dark

- Fonts: Default Font
- JetBrains Mono Regular
- Default Monospace font
- JetBrains Mono regular

Window Manager
- Theme
- Ant-Blood
- Title font
- JetBrains Mono Medium

Comando
xfce4-panel -r

## Eliminar Plank
- plank --quit
- sudo apt remove plank


sudo apt remove --purge fonts-terminus xfonts-terminus materia-gtk-theme papirus-icon-theme fonts-jetbrains-mono git


sudo rm -r /usr/share/themes/Ant-Bloody



sudo rm -r /usr/share/icons/Gruvbox-Plus-Dark



https://www.youtube.com/watch?v=VBaS1nZdnOo