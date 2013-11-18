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

    $ git branch # lsta los branch
    $ git branch <branch_name> # crea un nuevo branch
    $ git branch -b <branch_name> # crea un nuevo branch y cambiamos a este
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

    $ cd /home/projects/
    $ mkdir websitepro
    $ cd websitepro

    $
