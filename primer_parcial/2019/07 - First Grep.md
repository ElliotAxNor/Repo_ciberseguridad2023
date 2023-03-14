# First Grep

## Descripcion
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Pistas
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solucion

```bash
axelliot-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
--2023-03-13 23:50:35--  https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: 'file'

file                                                     100%[==================================================================================================================================>]  14.21K  --.-KB/s    in 0s      

2023-03-13 23:50:35 (454 MB/s) - 'file' saved [14551/14551]

axelliot-picoctf@webshell:~$ ls
README.txt  file  strings
axelliot-picoctf@webshell:~$ cat file | grep pico
picoCTF{grep_is_good_to_find_things_5af9d829}
axelliot-picoctf@webshell:~$ 
```

# Bandera
picoCTF{grep_is_good_to_find_things_5af9d829}

## Notas adicionales
 | comando | descripcion |
|---------|-------------|
|wget | Descarga y guarda archivos de la red por medio de un link |
| strings | Obtener los caracteres legibles de un archivo binario no legible, es decir, utilizada para extraer cadenas de texto imprimibles de archivos binarios. |
| grep |  obtener los caracteres legibles de un archivo binario no legible, es decir, utilizada para extraer cadenas de texto imprimibles de archivos binarios. |

## Referencias
[Learn Grep and Regular Expressions with examples - Linux Tutorial (ryanstutorials.net)](https://ryanstutorials.net/linuxtutorial/grep.php)
