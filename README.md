Taller GIT & GITHUB
===================

Resumen de comandos

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

