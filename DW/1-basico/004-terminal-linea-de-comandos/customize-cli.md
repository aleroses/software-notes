# Personalizar Interfaz de Línea de Comandos

## Prompt en Linux

### Bash Shell

Pasos para personalizar el prompt de "Konsole" en Debian. [Ohmyposh](https://ohmyposh.dev/docs/installation/linux)c

```bash
sudo apt update && sudo apt upgrade
sudo apt install curl

# Check your shell
echo $0
echo $SHELL

# Install Ohmyposh
curl -s https://ohmyposh.dev/install.sh | bash -s

# Verify that the binary works
/home/ghost/.local/bin/oh-my-posh --version
27.4.0 # 👈🏼👀

# Replace "ghost" with your username.
```

Añade ese directorio a tu `PATH`.

```bash
# Edit your file
vim ~/.bashrc
```

Ingresa esto al final del archivo, respeta el siguiente orden:

```bash
# Add local bin to PATH
export PATH=$PATH:$HOME/.local/bin

# Initialize oh-my-posh prompt
eval "$(oh-my-posh init zsh --config ~/.cache/oh-my-posh/themes/bubbles.omp.json)"

# Replace “bubbles” with whatever theme you like
```

En Vim pega usando `i` - `Ctrl + Shift + V`, guarda y cierra el archivo con `Esc` - `:wq`.

> Nota: Cambia `bubbles` por el tema que a ti te guste. Ver [Themes](https://ohmyposh.dev/docs/themes)

```bash
# Apply changes without closing the terminal
source ~/.bashrc

# Verify that which oh-my-posh displays:
which oh-my-posh

/home/ghost/.local/bin/oh-my-posh # 👈🏼👀
```

Instala fuentes necesarias:

```bash
# You can select "Meslo"
oh-my-posh font install
oh-my-posh font install meslo
```

Selecciona la fuente dentro de "Konsole".

1. Crea un nuevo perfil:  
	- Entra en `Settings/Manage Profiles/+New..`
	- Dale un nombre `ghost`
	- Apply + Ok
2. Cambia de perfil:  
	- Switch Profile: `ghost`
3. Edita el perfil actual  
	- Edit Profile "ghost"
	- Appearance
	- Choose
	- Escoge alguno que te guste: `MesloLGL Nerd Font Mono`
	- Apply + Ok

### Zsh Shell

```bash
sudo apt update && sudo apt upgrade
# Install Zsh
sudo apt install zsh
zsh --version

# ☠️ Make Zsh your default shell ☢️
chsh -s $(which zsh)

# Restart your computer 
sudo reboot

# Check your shell
echo $0
echo $SHELL

sudo apt install curl
```

Añade esta línea en tu `~/.zshrc`:

```bash
# Add local bin to PATH
export PATH="$PATH:$HOME/.local/bin"

# Initialize Oh My Posh for Zsh
eval "$(oh-my-posh init zsh --config $HOME/.cache/oh-my-posh/themes/clean-detailed.omp.json)"
```

```bash
source ~/.zshrc
which oh-my-posh
```

Igual que en `Bash` instala las fuentes: 

```bash
oh-my-posh font install
oh-my-posh font install meslo
```

Añadelo en la terminal que estés usando en mi caso en "Konsole".

```bash
```

👈🏼👀