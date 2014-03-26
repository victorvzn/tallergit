Taller GIT & GITHUB
===================

Resumen de comandos y ejemplos

## Configuración de Git

    $ git config --global user.name "Victor Villazon"
    $ git config --global user.email "victor@vizonideas.com"

## Instalar SSH Key para vincular nuestro computador local con github

    $ ssh-keygen

      Generating public/private rsa key pair.
      Enter file in which to save the key (/home/you/.ssh/id_rsa)

      Enter passphrase (empty for no passphrase): [Password]
      Enter same passphrase again: [Repeat password]

      Your identification has been saved in /home/you/.ssh/id_rsa.
      Your public key has been saved in /home/you/.ssh/id_rsa.pub.
      The key fingerprint is:
      01:02:f3:34:c5:85:d6:37:d1:1d:a0:18:3d:00:e8:bd emailname@email.com

    $ cd .ssh
    $ nano id_rsa.pub
      --- Copiar estos dígitos en la configuración de github,
      --- Account Settings > SSH Keys
      --- Add SSH Key and paste

    ** Comprobamos si estamos vinculados con github

    $ ssh -T git@github.com

    Hi username! You've successfully authenticated, but GitHub does not
    provide shell access.


## Repositorio local

    $ git init
    $ git add [.|<file(s)_name>]
    $ git commit -m "message_text"
    $ git commit -amend
    $ git log
    $ git log -oneline
    $ git reset HEAD <file(s)_name>
    $ git reset --mixed <commit_id>
    $ git reset --hard <commit_id> # Reset de commit sin retorno
    $ git status
    $ git show <commit_id> # Lista los cambios en este commit
    $ git diff # cambios actuales en wl working área
    $ dig diff --cached # cambios en el staging área
    $ git diff HEAD cambios en ambas áreas

    #
    $ git tag v1.0

    # Herramienta para ver todo el historial de commits
    $ gitk

    # Ramas (branches)

    $ git branch # lista los branch disponibles
    $ git branch <branch_name> # crea un nuevo branch
    $ git branch -b <branch_name> # crea un nuevo branch y cambiamos a este
    $ git branch -d <branch_name> # eliminamos un brach existente
    $ git checkout <branch_name> # cambiamos de branch

    # Merge

    $ git merge

## Repositorio remoto

    $ git clone <url_repository>
    $ git remote -v
    $ git push origin master
    $ git

## Verificar versión de git.

    $ git --version

## Ayuda y descripcion de cada comando.

    $ git --help
    $ git --help status

## Como colaborar en un proyecto en github (pull request)

    # 1. Fork some repository with the button FORK (MAIN REPOSITORY)
    
    # 2. Localy create a directory for your repository
    $ mkdir collaborations
    
    # 3. Clone the repository (REPOSITORY LOCALY FORKED)
    $ git --version
    $ git clone https://github.com/victorzn/tallergit
    
    # 4. Verify the conection with the repository
    $ cd tallergit
    $ git remote -v
    origin  https://github.com/victorzn/tallergit.git (fetch)
    origin  https://github.com/victorzn/tallergit.git (push)

    # 5. we connect to the repository original
    $ git remote add https://github.com/Sfotipy/sfotipy.git
    origin  https://github.com/victorzn/tallergit.git (fetch)
    origin  https://github.com/victorzn/tallergit.git (push)
    upstream    https://github.com/vizonideas/tallergit.git (fetch)
    upstream    https://github.com/vizonideas/tallergit.git (push)

    # 6. We update the master branch localy with the origin repository
    $ git pull -r upstream master

    # 7. We created a branch to avoid losing changes
    $ git checkout -b my-collaborations

    # 8. Now we can start to make changes and we make a commit to the repository forked
    $ touch pony.txt
    $ git status
    # Untracked files:
    #   pony.txt

    $ git add -A
    $ git commit -m "I added the pony.txt file"
    $ git push origin master
    username:
    password:

## Tricks

01 - Aviso de cambios al servidor
Settings/Service Hooks >> WebHook URL
Example URL: https://domain.com/update-github/
Script on server: git pull origin master

## Herramientas online

    GITHUB / GITLAB


## Ejercicio


Ejercicio 01: Creamos repositorio localmente.

    $ cd /home/projects/
    $ mkdir websitepro
    $ cd websitepro

    $ git init

Ejercicio 02: Creamos un archivo para llevar el control de sus cambios.

    $ touch demo.txt
    $ nano demo.txt
      primera línea

    $ git status
    $ git add demo.txt
    $ git commit -m "MASTER: Revisión inicial"
    $ git status

Ejercicio 03: Subimos los cambios al servidor remoto con push.

    $ git remote add origin https://github.com/victorzn/tallergit.git
    $ git remote -v

    $ git push origin master


Ejercicio 04: Clonamos un repositorio remoto ya exitente y trabajamos sobre este mismo.

    $ cd /home/projects/
    $ git clone https://github.com/victorzn/tallergit.git

    $ git remote -v
    $ git remote add origin https://github.com/victorzn/tallergit.git

    $ git push origin master


Ejercicio 05: Creamos una Rama (branch), nos movemos a esta y hacemos push al servidor remoto.

    $ git branch funcionalidad_n
    $ git checkout funcionalidad_n

    $ git push origin funcionalidad_n


Ejericio 06: Actualizamos nuestro repositorio local al commit mas nuevo.

    $ git pull


Ejercicio 07: Fusionamos la rama 'funcionalidad_n' al branch activo '*master'.

    $ git branch
      funcionalidad_n
      *master

    $ git merge funcionalidad_n

    Nota: Git hará el merge automáticamente, pero si hay conflicto tenemos que resolver el problema nosotros mismos
         editando los archivos que nos muestra git.


Ejercicio 08: Resolvemos conflictos de merge entre ramas (branches).

    1. Editamos los archivos con conflictos que nos muestra git manualmente.

    $ nano demo.txt

    2. Marcamos como fusionados los archivos con conflictos.

    $ git add demo.txt

    3. (Opcional) Revisamos los cambios realizados con:

    $ git diff <source_branch> <target-branch>

    4. Fusionamos los cambios

    $ git merge funcionalidad_n


Ejercicio 09: Creamos etiquetas para establecer una versión estable de nuestro repositorio.

    $ git log
      commit 741b6b0b6ddfb2374fcc4efaa6772e80dbc2c0ac

    $ git tag 1.0.0 741b6b0b6d

Ejercicio 10:



-------


