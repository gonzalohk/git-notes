Generar llave SSH
```sh
ssh-keygen -t rsa -b 4096 -C "goh.acm@gmail.com" (crea la llave publica y privada)
eval $(ssh-agent -s) (saber si el agente ssh esta ejecuntando)
ssh-add ~/.ssh/id_rsa (agregar la llave privada)
```
Iniciar Git
```sh
git int
```
Configuración de Git

```sh
git config
git config --list
git config --list --show-origin
git config --global
git config --global user.name "Gonzalo Osco"
git config --global user.email "goh.acm@gmail.com"
```

Agragar a la zona de preparación (Staging)
```sh
git checkout --File.txt 
git add File.txt
git add .
```

Ver estado
```sh
git status
```

Quitar de la zona de preparación (Staging)
```sh
git rm --cached file.txt
```

Realizar commit
```sh
git commit -m "Este es el pimer commit de este archivo"
git commit -am "Este es el pimer commit de este archivo"
```

Ver el historial de cambios del archivo
```sh
git log
git log file.txt
```

Muestra todos los cambios sobre un archivo
```sh
git show file.txt
```

Comparar versiones
```sh
git diff commit commit
```

Volver a una versión anterior
```sh
git reset commit --hard (borramos todos los cambios y lo que tengamos en staging) 
git reset commit --soft (soft conservamos cambios y lo que tengamos en staging) 
git checkout (commit) file.txt
git checkout (rama) file.txt
```

Ver Cambio en bytes
```sh
git log --stat
```

Crear una rama
```sh
git branch (branchName)
```

Cambiar de rama
```sh
git checkout (branchName)
```

Merge entre branchs
```sh
git merge (branchName)
```

Traer un repositorio externo
```sh
git remote add origin (url)
git remote (muestra el origen)
git remote -v(es verval)
git pull origin master --allow-unrelated-histories (Fuerza la union de las diferentes historias)
git pull origin master (Descarga cambios)
git push (origin) (master) (Sube Cambios)
```
Actualizar remote url
```sh
git remote set-url origin git@github.com:gsuscastellanosSC/hyperblog.git (cambiar url para que sea con ssh)
```

Alias
```sh
git log --all(Muesta toda la historia)
git log --all --graph (Muestra toda la historia con la ineracción de las ramas)
git log --all --graph --decorate --oneline
alias arbolito="git log --all --graph --decorate --oneline"(forma de alias en linux)
```
Tags
```sh
git tag -a v0.1 -m "apendiendo tags en git" (hash del commit) (crear un tag)
git show-ref --tags

git push origin --tags (enviar los tags al repositorio remoto)
git tag -d v0.1   && $ git push origin :refs/tags/v0.1 (Borrar tags)
```
Ramas
```sh
git show-branch --all (¿Cuales branch existen y sus historias)
gitk (igual que la anterior per con gui)
git push origin :[nombre_branch] (Elimina rama remota)
```

Crear y actulizar Fork
```sh
git clone git@github.com:gonzalohk1989/blog.git

git remote add upstream (url-github)
git pull upstream master (trae todos los cabios de master del origen upstream)
```

Cambiar el nombre de una rama
```sh
git branch -m nombre-rama neuvo-nombre-rama
```

Rebase
```sh
git rebase "master" (desde otra rama)
git rebase "otra rama" (desde master)
```

Eliminar una Rama
```sh
git branch -D "otra rama"
```
Stash
```sh
git stash (crea un stash)
git stash list (lista los stash)
git stash pop (carga el stash)
git stash branch english-version (Crear una rama con el stash)
git stash drop (borrar un stash)
```

Limpiar archivos no deseados (untracked)
```sh
git clean --dry-run (ver que se va a borrar)  **Ejecución en seco, como probraban los cohetes y los barcos**
git clean -f (borrar)       
```

Ver logs
```sh
git log --oneline
```
Traer un solo commit de otra rama
```sh
git cherry-pick 3145bab
```
Remendar commits
```sh
git commit --amend (coloca los cambios en el útimo commit realizado)
```

Git Reset y Reflog
```sh
git reflog (Permite ver el log completo)
git reset HEAD@{2}
git reset --hard 3145bab
```
Ver ramas remotas
```sh
git branch -r
git branch -a
```
Buscar en archivos y commits de Git con Grep y log
```sh
git grep -n color (lugares donde uso la palabra color)
git grep -c color (cuanteas veces esta la palabra color)
git log -S "Cabecera" (Busca en los commits la palabra cabecera)
```
Crear alias
```sh
git short log (Ver commits realizados por persona)
git shortlog -sn (Contar commits por persona?)
git shortlog -sn --all (detalle de absolutamente todos los commits)

git config --global alias.stats "shortlog -sn --all --no-merges"
```
Ver detalle de cambios
```sh
git blame blog.html -c (Sobre un archivo)
git blame --help
git blame css/style.css -L5,25
```
This is my test
This is my test2
This is my test3
This is my test4