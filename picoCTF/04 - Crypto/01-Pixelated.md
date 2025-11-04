
## Descripción

I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled2.png)


## Solución

Inicio descargando los archivos de imagen png dentro de un directorio, usando el comando wget.

Las imágenes por si solas no muestran mas de que pixeles sin sentido.
Al analizar el sitio web wikipedia que nos proporcionan en las pistas veo que se trata de una técnica de criptografía visual, donde una imagen es digamos dividida y al momento de unirla con la otra parte podemos desencriptar el mensaje contenido.

Haremos uso de la herramienta ImageMagick previamente instalada. Unimos ambas imagenes y obtenemos otra imagen con la bandera:
``` bash
┌──(kali㉿kali)-[~/Downloads]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite flag.png

┌──(kali㉿kali)-[~/Downloads]
└─$ open flag.png
```

`picoCTF{da8fcef8}`


## Notas adicionales

- ImageMagick: Suite de herramientas de línea de comandos que nos permite interactuar con imágenes para distintos fines.

## Referencias

https://en.wikipedia.org/wiki/Visual_cryptography

https://imagemagick.org/