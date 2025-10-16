
## Descripción

Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/920731987787c93839776ce457d5ecd6/dds1-alpine.flag.img.gz)

## Solución

Inicio descargando el archivo de imagen de disco con el comando wget. Veo la extensión .gz por lo que lo desenpaqueto: `gzip -d dds1-alpine.flag.img.gz `

De acuerdo a la descripción del reto investigué acerca de srch_strings. Encuentro que es una herramienta para ayudarnos a buscar cadenas de texto imprimibles en archivos, y que la opción -a nos ayuda a escanear el archivo entero y no solo la sección.

Reviso las pistas y veo que me menciona dos retos que realicé anteriormente en los cuales aprendí sobre el comando grep y el pipe.

Intento realizar una búsqueda en mi archivo de imagen de disco desenpaquetado usando la herramienta srch_strings con su opción -a, uso un pipe para unir al comando grep e intento buscar la coincidencia de la bandera picoCTF; encuentro la bandera:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ srch_strings -a dds1-alpine.flag.img| grep picoCTF
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_564ff1a0}
```

## Notas adicionales

- srch_strings - Display printable strings in files.
- -a: Scan the entire file, not just the data section.

## Referencias

https://manpages.debian.org/jessie/sleuthkit/srch_strings.1.en.html

