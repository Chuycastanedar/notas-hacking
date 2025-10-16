
## Descripción

Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)

## Solución

Inicio descargando el archivo con el comando wget en un directorio.
Veo la extensión .gz por lo que lo desenpaqueto: `gzip -d disk.flag.img.gz `

Haremos uso de la herramienta Autopsy,  en específico las herramientas de línea de comando Sleuth kit que ya vienen con Kali y que Autopsy también utiliza.

Hacemos uso de una herramienta llamada mmls que nos permite ver información de las particiones de disco, como esta imagen de diso que tenemos.

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ mmls disk.flag.img                                    
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
```

Observo que tengo estas particiones, hice uso de una herramienta llamada fls que nos permite listar los directorios dentro de la imagen. Al final me dirigí a la última partición Linux en la que busqué en el directorio root ydentro de este encontré el archivo flag.
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ fls -o 411648 disk.flag.img                 
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ fls -o 411648 disk.flag.img 472
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
```

Usando la herramienta icat que lee archivos que están desde una partición, me percaté de que la bandera se encuentra en el archivo flag.txt.enc pero se encuentra encriptada:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ icat -o 411648 disk.flag.img 1782                  
Salted__�ށ��e��B�J▒�c�$QE&$��4jM�KGeE�1�^Ȥ7� ���؎$�'%                                                                                
┌──(kali㉿kali)-[~/Downloads]
└─$ icat -o 411648 disk.flag.img 1876
           -0.881573            34.31173
```

Con la herramienta icat leí el archivo .ash_history que se encuentra en el mismo directorio, dentro del cual encontré el historial de comandos que se usó para crear el archivo de bandera y encriptarlo:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ icat -o 411648 disk.flag.img 1875
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt 
```

Simplemente saco el contenido de la bandera encriptada y lo guardo en un nuevo archivo usando icat, lo desencripto con el mismo comando que se encriptó usando la opción -d y leo la bandera desencriptada:
``` bash
┌──(kali㉿kali)-[~/Downloads]
└─$ icat -o 411648 disk.flag.img 1782 > flag.txt.enc

┌──(kali㉿kali)-[~/Downloads]
└─$ openssl aes256 -d -salt -in flag.txt.enc -out flag_desencriptado.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40072EC5CC7F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:

┌──(kali㉿kali)-[~/Downloads]
└─$ cat flag_desencriptado.txt 
picoCTF{h4un71ng_p457_5113beab} 
```


## Notas adicionales


## Referencias