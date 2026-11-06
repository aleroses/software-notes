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

## Crear y eliminar repositorios

```bash
git init
git status
git add . && git commit -m "First commit"

# Crear remoto 🔥👀👇🏼 --private
gh repo create project-tutorial --public --source=.
git push origin maste

gh repo view aleroses/project-tutorial
gh repo view aleroses/project-tutorial --web
```

```bash
# Delete remoto
gh repo delete aleroses/project-tutorial # type
gh auth refresh -h github.com -s delete_repo
gh repo delete aleroses/project-tutorial # type
```

## Issues

```bash
gh issue --help
gh issue list
```

```bash
# Create
gh issue create
  # first issue
  # Test issue 

# Delete
gh issue delete --help
gh issue delete 1
```

## Pull Request

```bash
gh pr --help
gh pr list

```

## Escenario de colaboración

**Mantener cada Pull Request por debajo de las 400 líneas** y organizado en pisos lógicos y dependientes.

### ¿Por qué lo necesitas en tu caso?

1. **Evitas el bloqueo:** Si intentaras meter todo en una sola rama gigante o esperaras a que aprueben tu primer PR (`viewer-intake`) para empezar lo siguiente, te quedarías con los brazos cruzados. `gh-stack` te permite seguir programando el siguiente componente (`viewer-tabs`) tomando como base tu propio avance actual sin tocar `master` todavía.
    
      
    
2. **Respetas el límite de los PRs:** Como cada piso del stack se evalúa de manera independiente contra su rama inferior, el revisor solo verá tus nuevos cambios (por debajo de las 400 líneas), facilitando que te aprueben el código rápido.
    
      
    
3. **Automatiza la complejidad:** Sin la extensión, tendrías que crear ramas intermedias a mano, hacer rebase manual de cada una y cambiar la base de los PRs en la web de GitHub cada vez que modifiques algo abajo. `gh-stack` hace ese encadenamiento y sincronización automáticamente con comandos como `gh stack sync`.
    
      
    

### Resumen operativo de cómo usarlo en tu día a día

- **Piso 1 (Ya casi listo):** Tu agente te indicó adoptar la rama actual que ya tiene los cambios de la interfaz mediante:
    
      
    
    Bash
    
    ```
    gh stack init viewer-intake
    gh stack view --short
    gh stack submit
    ```
    
- **Piso 2 (Lo siguiente):** Cuando estés listo para la siguiente parte (por ejemplo, las pestañas) sin esperar aprobación previa, solo ejecutas:
    
      
    
    Bash
    
    ```
    gh stack add viewer-tabs
    ```
    
    Haces tus commits de ese bloque y luego subes ese nuevo piso con:
    
      
    
    Bash
    
    ```
    gh stack submit
    ```
    
    Este segundo PR apuntará automáticamente a `viewer-intake` y no a `master`.



## Paso 5. Cuando mezcles

Para mezclar solo el piso de abajo, en GitHub mezclas ese pull request, o en local:

```bash
# Esto lo hace **el mantenedor o dueño del repositorio original**
gh stack merge
```

y eliges el pull request de `viewer-intake`. Lo de arriba no entra. Mezclar el piso de arriba mezcla también todo lo que tiene debajo.

Después de que el piso de abajo (`viewer-intake`) ya ha sido aprobado y fusionado (`merged`) en el `master` del proyecto original:

```bash
# Puedes estar parado en cualquiera de tus ramas de trabajo de la pila
gh stack sync
```

- Trae los cambios nuevos del `master` oficial, apoya otra vez cada piso en el de abajo y empuja. 
- Actualice tu siguiente piso (`viewer-tabs`) para que ahora su base sea directamente `master` y no la rama anterior que ya desapareció.

Si hubo rebase, el empuje de esas ramas es `--force-with-lease`. No toca `master` con force. Si hay conflicto, no insiste: dejas `sync` y sigues con `gh stack rebase`, resuelves y `gh stack rebase --continue`.

`gh stack down` baja un piso, `up` sube uno, `trunk` vuelve a `master`, `view --short` enseña la pila.

## Qué no hacer

- No apilar `front` ni `viewer-page`.
    
- No usar `gh stack add -m`: eso crea un commit por ti. Los commits los haces tú, uno por componente.
    
- No meter el grupo siguiente en `viewer-intake` si con eso el pull request pasa de 400 líneas. Ese grupo es otra rama y otro `submit`.
















que hace https://edifileconverter.com/edi

lista de funcionalidades y cuáles tenemos

mcp añadir issues


linear

diferencia entre issue create