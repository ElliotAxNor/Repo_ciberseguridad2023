# Bandit Level 2 al 3

## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## Datos de acceso al nivel
bandit2
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Solucion
```bash
bandit2@bandit:~$ whoami
bandit2
bandit2@bandit:~$ pwd
/home/bandit2
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```

## Notas adicionales
*  Cuando hay espacios en el nombre hay que delimitarlo
## Referencias