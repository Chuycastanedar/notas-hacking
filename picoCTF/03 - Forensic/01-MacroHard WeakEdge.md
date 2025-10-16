
## Descripción

I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/3944a59474f9f676942282c50b9c3675/Forensics%20is%20fun.pptm)

## Solución

Iniciamos descargando el archivo que se nos da con el comando wget.

Vemos con el comando file que es un tipo de archivo Microsoft PowerPoint 2007. Desenpaquetamos el archivo con: `unzip nombreDelArchivo`, y al observar vemos que obtenemos una gran cantidad de archivos, por lo que haremos uso de la herramienta visual studio code para buscar más facilmente en la estructura de archivos la bandera.

Descargamos el VS Code si aún no lo tenemos, e instalamos.
Abrimos el directorio de los archivos desenpaquetados de nuestro archivo y al buscar un poco encontramos un archivo llamado hidden, dentro del cual observamos una cadena larga de caracteres al parecer en base 64.

Copiamos y nos dirigimos a cyberchef, usamos from base 64 y al convertirla nos encontraremos con la bandera.
`picoCTF{D1d_u_kn0w_ppts_r_z1p5}`


## Notas adicionales

- Podemos desenpaquetar un pptm con el comando unzip.


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)