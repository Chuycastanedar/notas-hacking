
## Descripción

Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.

## Solución

Descargamos el archivo en un directorio con el comando wget.
Al examinar que formato tiene el archivo con el comando file, veremos que es un formato WAV de audio.
De acuerdo al nombre del reto y pistas si investigamos al respecto veremos que la forma en que el Apollo 11 envió archivos de imagen de la luna fue por medio de un formato de tipo audio, codificada ahí la imagen.
Si buscamos un decodificador en línea nos encontramos con un repositorio que cuenta con ello, por lo que clonamos el repositorio con el comando: `git clone` en la ruta /opt.
Entramos a la carpeta sstv/ con el comando cd y ejecutamos el instalador con: `python3 setup.py install`.
Ya que instalamos nos regresamos al directorio en el que descargamos nuestro archivo y ejecutamos el comando para decodificar el audio: `sstv -d message.wav - o result.png`.
Al finalizar obtendremos un archivo con el nombre que asignamos result.png, en la imagen observaremos la bandera.
`picoCTF{beep_boop_im_in_space}`


## Notas adicionales

- sstv herramienta para decodificar el audio en formato Scottie en este caso a imagen.

## Referencias

https://github.com/colaclanth/sstv