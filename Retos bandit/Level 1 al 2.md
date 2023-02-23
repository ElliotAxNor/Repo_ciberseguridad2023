# Bandit Level 1 -> Level 2


## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory
## Datos de acceso al nivel
ssh bandit1@bandit.labs.overthewire.org -p 2220
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
## Solucion
```bash
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ cat /home/bandit1/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```
## Notas adicionales

## Referencias