
## Descripción

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/1b70cffdd2f05427fff97d13c496963f/dolls.jpg)

## Solución

Inicio descargando el archivo usando el comando wget y el link.
Pruebo a verificar los metadatos con el comando `exiftool` pero no encuentro nada interesante.
Probando con un `Strings -n 10 dolls.jpg` al parecer vemos otra imagen dentro. Con binwalk confirmamos que al parecer existe un PNG y dentro de el existe un zip con otro archivo de imagen.

Haciendo uso de binwalk extraemos dicho archivo. 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ binwalk -e dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383938, name: base_images/2_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

```

Al finalizar nos dejará una carpeta a la que debemos de entrar con el comando cd, encontraremos otro arhivo de imagen al cual tendremos que aplicarle exactamente el mismo proceso y repetir unas 2 o 3 veces más.

Podemos ir verificando con el comando: `binwalk nombre del archivo`, hasta que el archivo que obtengamos no sea uno de imagen si un una flag.txt. Lo leemos con un cat y obtenemos la bandera.
`picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}`


## Notas adicionales


## Referencias