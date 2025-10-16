
## Descripción

Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory. [Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz) Access checker program: `nc saturn.picoctf.net 53038`****

## Solución

Inicio descargando el archivo con el comando wget en un directorio.
Veo la extensión .gz por lo que lo desenpaqueto: `gzip -d disk.img.gz `

Hacemos uso de una herramienta llamada mmls que nos permite ver información de las particiones de disco.

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)

```

Aquí ya ubicamos el tamaño de la partición linux que se nos pedirá al conectarnos. Simplemente copeamos el comando para conectarnos, respondemos el tamano de la partición y obtendremos la bandera.
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ nc saturn.picoctf.net 53038
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}

```


## Notas adicionales

- Sleuthkit: Es una herramienta open source para análisis forense digital, es parte de Autopsy. 
- Es una colección de herramientas de línea de comando y una librería en c que permite analizar las imágenes de discos y recuperar información de ellas.

## Referencias

https://www.sleuthkit.org/