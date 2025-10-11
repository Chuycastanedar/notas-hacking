## Descripción

The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.`ssh -p 54680 ctf-player@mimas.picoctf.net`Use password: `84b12bae`

## Solución

Primero usamos `*` para ver todo lo que esta en la actual ruta, encontramos algo llamado `blargh` el cual contiene el archivo de la bandera, pero al no poder acceder a un `cat` o algo similar, no se puede acceder para ver su contenido.

```bash

SansAlpha$ *

bash: blargh: command not found

SansAlpha$ /

bash: /: Is a directory

SansAlpha$ */

bash: blargh/: Is a directory

SansAlpha$ /*

bash: /bin: Is a directory

SansAlpha$ */*

bash: blargh/flag.txt: Permission denied

```

Encontramos también el directorio `bin` donde hay ejecutables, pero al intentar hacer coincidir el comando `cat` no resulta, pues comparte la cantidad de caracteres con otros.

```bash

SansAlpha$ /*/*

/bin/[: missing ']'

SansAlpha$ /*/???

E: Invalid operation /bin/awk

```

Pero al probar mas caracteres aparecen dos interesantes que son las herramientas que convierten a base 64 y 32.

Intentamos hacer coincidir el formato con el sufijo 64 y enviarle la ruta al archivo de la bandera, pero aparece otro archivo que coincide, lo descartamos haciendo uso de `[!]` que nos permite especificar en el formato que no debe tener un `_` en su cuarto carácter.

```bash

SansAlpha$ /*/??????

/bin/base32: extra operand '/bin/base64'

Try '/bin/base32 --help' for more information.

SansAlpha$ /*/????64 */*

/bin/base64: extra operand '/bin/x86_64'

Try '/bin/base64 --help' for more information.

SansAlpha$ /*/???[!_]64 */*

/bin/base64: extra operand 'blargh/flag.txt'

Try '/bin/base64 --help' for more information.

SansAlpha$ /*/???[!_]64 */????.???

cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV9iMGQ1ZTg1NX0=

```

revertimos  la `base64`

```bash

┌──(kali㉿kali)-[~/pico]

└─$ echo cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV9iMGQ1ZTg1NX0= | base64 -d

return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_b0d5e855}

```

## Notas

  

Standard Wildcards:

- El asterisco (`*`) puede ser usado para representar cualquier cantidad de caracteres

- El signo de pregunta `?` puede representar un character simple, numero o letra.

- La combinación `[!]` es el contrario a `[]` que te permite hacer coincidir los caracteres, entonces esta hace no coincidir los caracteres contenidos dentro.

## Referencias

[Wildcards](https://tldp.org/LDP/GNU-Linux-Tools-Summary/html/x11655.htm)