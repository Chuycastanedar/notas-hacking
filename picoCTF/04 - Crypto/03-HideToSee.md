
## Descripción

How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/239/atbash.jpg).

## Solución

Inicio descargando el archivo de imagen .jpg usando el comando wget.

Al abrir la imagen observamos una pista muy importante que es el cifrado atbash, el cuál abordaremos posteriormente.

Al analizar la imagen con distintas herramientas como exiftool, zsteg y binwalk entre otras no logramos encontrar absolutamente nada. 
Haremos uso de la herramienta steghide previamente instalada, mediante la cual extraemos el archivo contenido en la imagen:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ steghide --extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
```
Leemos el archivo encriptado:
```bash
──(kali㉿kali)-[~/Downloads]
└─$ cat encrypted.txt       
krxlXGU{zgyzhs_xizxp_1u84w779}
```
Recordamos el cifrado atbash, pues esta cadena de caracteres corresponde a la bandera encriptada mediante este cifrado.

Usamos cyberchef con la operación Atbash Cipher y obtenemos la bandera:
`picoCTF{atbash_crack_1f84d779}`


## Notas adicionales

- Atbash cipher: Es un cifrado básico que consiste en invertir el alfabeto y sustituir cada caracter por el de su misma posición.
- Por ejemplo la a con la z, b con la y y así sucesivamente...

## Referencias

https://es.wikipedia.org/wiki/Atbash

https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfMXU4NHc3Nzl9