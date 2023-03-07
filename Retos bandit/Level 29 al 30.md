# Bandit Level 29 → Level 30

## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

## Datos de acceso al nivel
bandit29
bbc96594b4e001778eee9975372716b2

## Solucion

```bash

bandit29@bandit:~$ mkdir /tmp/plop123
bandit29@bandit:~$ cd /tmp/plop123
bandit29@bandit:/tmp/plop123$ git clone ssh://bandit29-git@localhost/home/bandit29-git/repo
Cloning into 'repo'...
bandit29-git@localhost password: 

remote: Counting objects: 16, done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0)
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/plop123$ cd repo/
bandit29@bandit:/tmp/plop123/repo$ cat README.md 
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/plop123/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/dev
  origin/master
  origin/sploits-dev
bandit29@bandit:/tmp/plop123/repo$ git checkout dev
Branch dev set up to track remote branch dev from origin.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/plop123/repo$ cat README.md 
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: 5b90576bedb2cc04c86a9e924ce42faf
```


## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| |  |

## Referencias