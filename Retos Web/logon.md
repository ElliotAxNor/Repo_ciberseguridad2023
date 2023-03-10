# Reto logon

## Descripcion
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573/` ([link](https://jupiter.challenges.picoctf.org/problem/44573/)) or http://jupiter.challenges.picoctf.org:44573

## Pistas
Hmm it doesn't seem to check anyone's password, except for Joe's?

## Solucion
Para este reto modificamos las cookies del sitio: entrando con cualquier usuario y contraseña (todo es valido), inspeccionamos las cookies con un plujin que previamente instalamos (Cookie Editor), y modificamos value a True dentro de la carpeta admin.

```bash

```

# Bandera
picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}

## Notas adicionales
 | comando | descripcion |
|---------|-------------|
| |  |

## Referencias