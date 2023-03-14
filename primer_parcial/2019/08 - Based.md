# Based

## Descripcion
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

## Pistas
I hear python can convert things.
It might help to have multiple windows open.

## Solucion

Para descifrar las palabras se uso la herramienta cyberchef.org 
```bash
axelliot-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
animation
Please give the 01100001 01101110 01101001 01101101 01100001 01110100 01101001 01101111 01101110 as a word.
...
you have 45 seconds.....

Input:
animation
Please give me the  146 141 154 143 157 156 as a word.
Input:
falcon
Please give me the 6c69676874 as a word.
Input:
light
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}
^C
axelliot-picoctf@webshell:~$
```

# Bandera
picoCTF{learning_about_converting_values_b375bb16}

## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| |  |

## Referencias
[CyberChef](https://cyberchef.org/)
