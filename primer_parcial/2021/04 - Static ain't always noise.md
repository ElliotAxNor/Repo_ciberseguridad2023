# Static ain't always noise

## Descripcion
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static)? This [BASH script](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh) might help!

## Pistas


## Solucion

```bash
axelliot-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static
--2023-03-14 01:35:41--  https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                                                   100%[==================================================================================================================================>]   8.18K  --.-KB/s    in 0s      

2023-03-14 01:35:41 (241 MB/s) - 'static' saved [8376/8376]

axelliot-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh
--2023-03-14 01:35:56--  https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                                                 100%[==================================================================================================================================>]     785  --.-KB/s    in 0s      

2023-03-14 01:35:56 (555 MB/s) - 'ltdis.sh' saved [785/785]

axelliot-picoctf@webshell:~$ ls
README.txt  ende.py  file  flag  ltdis.sh  static  strings  warm
axelliot-picoctf@webshell:~$ ls -la
total 848
drwxr-xr-x 2 axelliot-picoctf axelliot-picoctf   4096 Mar 14 01:35 .
drwxr-xr-x 3 root             root                 30 Mar  2 18:36 ..
-rw------- 1 axelliot-picoctf axelliot-picoctf   1355 Mar 14 01:31 .bash_history
-rw-r--r-- 1 axelliot-picoctf axelliot-picoctf    220 Mar  2 18:36 .bash_logout
-rw-r--r-- 1 axelliot-picoctf axelliot-picoctf   3771 Mar  2 18:36 .bashrc
-rw-r--r-- 1 axelliot-picoctf axelliot-picoctf    807 Mar  2 18:36 .profile
-rw------- 1 axelliot-picoctf axelliot-picoctf     51 Mar  2 18:44 .python_history
-rw-rw-r-- 1 axelliot-picoctf axelliot-picoctf    178 Mar 14 01:35 .wget-hsts
-rw-r--r-- 1 root             root               4443 Mar 14 01:35 README.txt
-rw-rw-r-- 1 axelliot-picoctf axelliot-picoctf   1328 Mar 16  2021 ende.py
-rw-rw-r-- 1 axelliot-picoctf axelliot-picoctf  14551 Oct 26  2020 file
-rw-rw-r-- 1 axelliot-picoctf axelliot-picoctf     34 Mar 16  2021 flag
-rw-rw-r-- 1 axelliot-picoctf axelliot-picoctf    785 Mar 16  2021 ltdis.sh
-rw-rw-r-- 1 axelliot-picoctf axelliot-picoctf   8376 Mar 16  2021 static
-rw-rw-r-- 1 axelliot-picoctf axelliot-picoctf 776032 Oct 26  2020 strings
-rwxrwxrwx 1 axelliot-picoctf axelliot-picoctf  10936 Mar 16  2021 warm
axelliot-picoctf@webshell:~$ chmod 777 ltdis.sh 
axelliot-picoctf@webshell:~$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
axelliot-picoctf@webshell:~$ ls
README.txt  ende.py  file  flag  ltdis.sh  static  static.ltdis.strings.txt  static.ltdis.x86_64.txt  strings  warm
axelliot-picoctf@webshell:~$ cat static.ltdis.strings.txt | grep pico
   1020 picoCTF{d15a5m_t34s3r_f6c48608}
axelliot-picoctf@webshell:~$ 
```

# Bandera
picoCTF{d15a5m_t34s3r_f6c48608}

## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| |  |

## Referencias