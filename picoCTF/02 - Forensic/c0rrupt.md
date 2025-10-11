
## Descripción

We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Solución

Iniciamos descargando el archivo con el comando wget y el vínculo. De acuerdo a la pista que nos indica que reparemos el encabezado, intentamos ver el que tipo de archivo es con el comando file y veremos que no está identificado como un archivo válido aparentemente.

Si vemos el encabezado nos podremos dar cuenta que hay algunos indicios de que es un PNG, como por ejemplo por los chunks que al aprecer también están dañados.
Los archivos tienen cierto formato, en el caso del PNG existe un tipo específico con unos bytes en el encabezado que determinann que es este tipo de archivo. 
Abriremos el archivo con un editor hexadecimal y corregimos los bytes del inicio com oun PNG. Verificamos y sigue siendo data. Después del encabezado vienen los chunks, los cuales cambiaremos también usando el editor hexadecimal, y al guardar veremos que el archivo efectivamente ya es reconocido como un PNG.
Lo abrimos y veremos que ya si se detecta, sin embargo aún existen errores.
Vamos a instalar una herramienta llamada pngcheck que nos ayudará a verificar la integridad de nuestro archivo, usamos el comando `sudo apt install pngcheck`.
Encuentra un error de redundancia cíclica en un chunk, por lo que abrimos el editor hexadecimal nuevamente para verificar que sucede y de acuerdo al chunk y la documentación, se especifica un tamaño muy grande por lo que lo modificamos.
Al editar estas cosas, probamos a abrir la imagen con el comando open y encontraremos que efectivamente ya tenemos la bandera.

## Notas adicionales

- Herramienta pngcheck para verificar la integridad de los archivos PNG.

## Referencias
