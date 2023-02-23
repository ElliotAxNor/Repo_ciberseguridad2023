# Bandit Level 0 -> Level 1

## Objetivo
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Datos Acceso
ssh bandit0@bandit.labs.overthewire.org -p 2220

## Solucion
```bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
bandit0@bandit:~$
```

## Notas adicionales

 
 | comando | descripcion |
|---------|-------------|
| cat | muestra el contenido de un archivo |
| ls | listar archivos |



## Referencias