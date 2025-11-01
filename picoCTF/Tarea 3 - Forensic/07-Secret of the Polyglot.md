
## Descripción

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/98/flag2of2-final.pdf).

## Solución

Inicio descargando el archivo en un directorio con el comando wget.

Observo que se trata de un pdf, el cual abro con el comando open y me encuentro con un documento con una cadena de caracteres que identifico como el fragmento final de la bandera.

Copeo esta cadena y la pego en algún lugar seguro. Luego utilizo la herramienta exiftool para analizar la información de dicho archivo, dentro de la cual encuentro que se categoriza al archivo como de tipo png:
```bash
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
```

Cambio la extension de mi archivo a png: 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ mv flag2of2-final.pdf foto.png
```

Abro mi imagen con el comando open y obtengo una foto que contiene el fragmento inicial que junto al anterior completan la bandera.

## Notas adicionales


## Referencias