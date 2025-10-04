
## Descripción

This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Solución

Descargo el archivo en un directorio haciendo uso del comando wget.
Al aplicarle un file logro ver que lo detecta como un PNG a pesar de tener extensión .txt, pues este esta firmado como un PNG. Al ver esto aplico un mv y lo renombro con la extensión .png.
Solamente intento abrir el archivo con un open y ya veo que encuentro la bandera dentro de la imagen.
`picoCTF{now_you_know_about_extensions}`

## Notas adicionales

- Muchos formatos de archivos parecieran ser texto, pero en realidad contener otro tipo de información como una imagen PNG por ejemplo.
- mv: Comando que nos sirve también para renombrar la extensión.

## Referencias


