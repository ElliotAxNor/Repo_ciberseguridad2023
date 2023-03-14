# Tab, Tab, Attack

## Descripcion
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/fe16c756149cfa85f23e73cd9dbd6a25/Addadshashanammu.zip)

## Pistas
After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Solucion

```bash
axelliot-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/fe16c756149cfa85f23e73cd9dbd6a25/Addadshashanammu.zip
--2023-03-14 01:47:50--  https://mercury.picoctf.net/static/fe16c756149cfa85f23e73cd9dbd6a25/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip                                     100%[==================================================================================================================================>]   4.41K  --.-KB/s    in 0s      

2023-03-14 01:47:50 (1.58 GB/s) - 'Addadshashanammu.zip' saved [4520/4520]

axelliot-picoctf@webshell:~$ ls
Addadshashanammu.zip  README.txt  ende.py  file  flag  ltdis.sh  static  static.ltdis.strings.txt  static.ltdis.x86_64.txt  strings  warm
axelliot-picoctf@webshell:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
axelliot-picoctf@webshell:~$ ls -R Addadshashanammu
Addadshashanammu:
Almurbalarammi

Addadshashanammu/Almurbalarammi:
Ashalmimilkala

Addadshashanammu/Almurbalarammi/Ashalmimilkala:
Assurnabitashpi

Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi:
Maelkashishi

Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi:
Onnissiralis

Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis:
Ularradallaku

Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku:
fang-of-haynekhtnamet
axelliot-picoctf@webshell:~$ cd Addadshashanammu/
axelliot-picoctf@webshell:~/Addadshashanammu$ cd Almurbalarammi/
axelliot-picoctf@webshell:~/Addadshashanammu/Almurbalarammi$ cd Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
axelliot-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
axelliot-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ cat fang-of-haynekhtnamet | grep fang-of-haynekhtnamet 
grep: (standard input): binary file matches
axelliot-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ strings fang-of-haynekhtnamet | grep fang-of-haynekhtnamet 
fang-of-haynekhtnamet.c
axelliot-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ strings fang-of-haynekhtnamet | grep pico                  
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_76266e38}
axelliot-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ 
```

# Bandera
picoCTF{l3v3l_up!_t4k3_4_r35t!_76266e38}

## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| |  |

## Referencias