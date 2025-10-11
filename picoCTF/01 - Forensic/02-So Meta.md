
## Descripción

Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).

## Solución

Descargo mi archivo imagen en un directorio con wget.
Utilizaremos la herramienta exiftool, la cual nos ayuda a analizar los metadatos en este caso de esta imagen que se nos da.
`exiftool pico_img.png`
Se nos despliega la lista de metadatos y en el nombre del autor encontramos la bandera: `picoCTF{s0_m3ta_d8944929}`


## Notas adicionales

- Metadatos: Son datos que proporcionan información acerca de otros datos.
- Hay metadatos descriptivos, estructurales, administrativos, de referencia, estadísticos, legales, etc.
- Ayudan al usuario a descubrir información relevante y a descubrir recursos.

- En una imagen pudieramos encontrar cuando se tomó la foto, donde se tomó, corrdenadas de geolocalización, con que dispositivo se tomó, etc.


## Referencias

https://es.wikipedia.org/wiki/Metadatos