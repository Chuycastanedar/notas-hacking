
## Descripción

Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://artifacts.picoctf.net/c/71/disk.img.gz)
- Remote machine: `ssh -i key_file -p 60034 ctf-player@saturn.picoctf.net`

## Solución

Inicio descargando el archivo con el comando wget en un directorio.
Veo la extensión .gz por lo que lo desenpaqueto: `gzip -d disk.img.gz `

Haremos uso de la herramienta Autopsy,  en específico las herramientas de línea de comando Sleuth kit que ya vienen con Kali y que Autopsy también utiliza.

Hacemos uso de una herramienta llamada mmls que nos permcite ver información de las particiones de disco, como esta imagen de diso que tenemos.

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ mmls disk.img                   
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)

```

Estamos busacando una llave SSH por lo que haremos uso de una herramienta llamada fls que nos permite listar los directorios dentro de la imagen. A partir del sector 206848
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ fls -o 206848 disk.img
d/d 458:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 79: proc
d/d 80: dev
d/d 81: tmp
d/d 82: lib
d/d 85: var
d/d 94: usr
d/d 104:        bin
d/d 118:        sbin
d/d 464:        media
d/d 468:        mnt
d/d 469:        opt
d/d 470:        root
d/d 471:        run
d/d 473:        srv
d/d 474:        sys
V/V 33049:      $OrphanFiles

```

Generalmente las llaves SSH se encuentran en el directorio del usuario, por lo que listamos el directorio root con el número del sector que ahí aparece, para luego listar el interior del ssh y encontrar llave pública y privada:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ fls -o 206848 disk.img 470
r/r 2344:       .ash_history
d/d 3916:       .ssh


┌──(kali㉿kali)-[~/Downloads]
└─$ fls -o 206848 disk.img 3916    
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub

```

Haciendo uso de la herramienta icat que lee archivos que están desde una partición vamos a leer la llave SSH y la guardaremos en un archivo:
```bash
(kali㉿kali)-[~/Downloads]
└─$ icat -o 206848 disk.img 2345 > key_file

```
Solamente cambiamos los permisos de dicho archivo a solo lectura:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ chmod 400 key_file 
```
Nos conectamos por SSH con el comando que se nos da y al hacer un ls vemos el archivo flag.txt, que al leer con un cat obtendremos la bandera:
`picoCTF{k3y_5l3u7h_af277f77}`


## Notas adicionales

- Generalmente en el mundo de análisis forense primero se hace una imagen del disco para no dañar la evidencia y luego se analiza.

## Referencias