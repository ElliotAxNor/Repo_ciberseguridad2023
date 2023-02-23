# Bandit Level 5 → Level 6

## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

-   human-readable
-   1033 bytes in size
-   not executable

## Datos de acceso al nivel
bandit5
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
## Solucion
```bash
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ find -readable -size 1033c -type f
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| find | permite encontrar archivos en el sistema |
| -readable | indica archivos en el sistema |
| -size | especificar el tamaño |
| -type | para especificar el tipo |

## Referencias
