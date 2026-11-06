# Github CLI

[Tutorial](https://www.youtube.com/watch?v=oZRFOkLUZdk)

## Instalación en Debian

[Github CLI](https://cli.github.com/)

```bash
(type -p wget >/dev/null || (sudo apt update && sudo apt install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
	&& cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& sudo mkdir -p -m 755 /etc/apt/sources.list.d \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```

```bash
sudo apt update
sudo apt install gh
```

[Installing gh on Linux and BSD](https://github.com/cli/cli/blob/trunk/docs/install_linux.md#debian)

## Login y Logout

```bash
gh auth login

? Where do you use GitHub? GitHub.com  
! Did you know that expiring tokens can be requested with --expiring? Read more at https://gh.io/gh-expiring-tokens  
? How would you like to authenticate GitHub CLI? Login with a web browser  
? What is your preferred protocol for Git operations on this host? SSH  
? Upload your SSH public key to your GitHub account? /home/ale/.ssh/id_ed25519.pub  
? Title for your SSH key: Oxedi  
  
! One-time code (F761-CDFC)🔥 copied to clipboard  
Press Enter to open https://github.com/login/device in your browser...    
✓ Authentication complete.  
- gh config set -h github.com git_protocol ssh  
✓ Configured git protocol  
✓ SSH key already existed on your GitHub account: /home/ale/.ssh/id_ed25519.pub  
✓ Logged in as aleroses
```

```bash
gh auth status

github.com  
 ✓ Logged in to github.com account aleroses (keyring)  
 - Active account: true  
 - Git operations protocol: ssh  
 - Token: gho_************************************  
 - Token scopes: 'admin:public_key', 'gist', 'read:org', 'repo'
```

```bash
gh auth logout
```

```bash
gh config --help
gh config list
```

## Crear y eliminar un Gist

[gist.github.com/aleroses](https://gist.github.com/aleroses)

```bash
cd gh-gist

# Create
gh gist create fibonacci.js --web
gh gist create fibonacci.js -w

# Delete
gh gist list # Copiar hash

gh gist delete 783046fe2cd4123b94b8a63509b4614e  
? Delete "fibonacci.js" gist? Yes  
✓ Gist "fibonacci.js" deleted
```

Crear varios Gist con descripción:

```bash
gh gist create prog01.py prog02.py -d "My first python program"
```

Por defecto se crean como secretos.

## Listar Gist

```bash
gh gist list
gh gist list --help
gh gist list --limit 2
gh gist list --public
gh gist list --secret
gh gist list --public --limit 2

# Listar repositorios
gh repo list
```

## Crear repositorios

```bash
git init
git status
git add . && git commit -m "First commit"

gh repo create project-tutorial --public --source=.
git push origin maste
```

```bash

```

```bash

```

```bash

```

```bash

```

que hace https://edifileconverter.com/edi

lista de funcionalidades y cuáles tenemos

mcp añadir issues


linear