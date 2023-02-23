# Bandit Level 12 → Level 13

## Objetivo

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de acceso al nivel
bandit12
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
## Solucion

```bash
bandit12@bandit:~$ cat data.txt | xxd -r | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Wed Jan 11 19:18:38 2023, max compression, from Unix
bandit12@bandit:~$
bandit12@bandit:~$ cat data.txt | xxd -r |zcat | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ cat data.txt | xxd -r |zcat | bzcat | file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Wed Jan 11 19:18:38 2023, max compression, from Unix
bandit12@bandit:~$ cat data.txt | xxd -r |zcat | bzcat | zcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ cat data.txt | xxd -r |zcat | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ cat data.txt | xxd -r |zcat | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ cat data.txt | xxd -r |zcat | bzcat | zcat | tar xO | tar xO | bzcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ cat data.txt | xxd -r |zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file
-
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Wed Jan 11 19:18:38 2023, max compression, from Unix
bandit12@bandit:~$ cat data.txt | xxd -r |zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
| file -
/dev/stdin: ASCII text
bandit12@bandit:~$ cat data.txt | xxd -r |zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:~$
```

## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| |  |

## Referencias