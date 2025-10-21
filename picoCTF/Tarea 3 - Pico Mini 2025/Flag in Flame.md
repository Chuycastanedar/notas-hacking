
## Descripción

The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log. Download the encoded data here: [Logs Data](https://challenge-files.picoctf.net/c_amiable_citadel/1139fe6db834706f6db733413ff652f41951589576e1c4ddf082b8ecccce1454/logs.txt). Be prepared—the file is large, and examining it thoroughly is crucial .


## Solución

Inicio descargando el archivo de datos que se me da haciendo uso del comando wget y el link.

Pruebo a ver su contenido con un cat:
```bash
──(kali㉿kali)-[~/Downloads]
└─$ cat logs.txt 
```

Rápido me doy cuenta que el contenido se encuentra en base 64, por lo que lo decodifico y lo guardo en un nuevo archivo.
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ base64 -d logs.txt > cadena.txt 
```
Exploro el contenido decodificado y veo que corresponde a un archivo PNG:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ cat cadena.txt 
�PNG

```
Cambio la extensión del archivo a png:
``` bash
──(kali㉿kali)-[~/Downloads]
└─$ mv cadena.txt cadena.png 
```
Abro mi archivo con el comando open y observo una imagen en la que hay una cadena de carcateres, vuelvo a decodificarla de base 64 usando cyberchef y obtengo la bandera.
`picoCTF{forensics_analysis_is_amazing_24d16895}`


## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#input=MTU0ODAxMjk0ODI5Mzg2MjM2OTY4MTMzOTQzMTk