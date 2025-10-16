
## Descripción

We found this [file](https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n). Recover the flag.

## Solución

Descargamos el archivo con el comando wget.
Verifico que tipo de archivo es con el comando file, y solamente obtengo data.

Vemos el encabezado en formato hexadecimal:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd tunn3l_v1s10n | head
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/
00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v
00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT
00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.
```

Alcanzamos a ver un BM, por lo que tentativamente puede ser un archivo BMP. Cambiamos la extensión del archivo: `mv tunn3l_v1s10n tunn3l_v1s10n.bmp`.

Abrimos el archivo con un editor hexadecimal.
El tamaño del encabezado debe ser de 40 bytes, 28 en hex especificado en la posición 0E, lo cambiamos.

En el Offset 0A tenemos otro BAD, debe estar el Offset en el cual inician los datos. Cambiamos a 28 0 y al intentar abrir el archivo esta vez si abre, pero en la imagen apreciamos que dice not a flag.

Con exiftool apreciamos que la altura de la imagen es algo baja respecto al tamaño por lo que intentamos cambiar con el heditor hexadecimal, cambiamos a 40 04 y al abrirla apreciaremos la imagen completa y en ella la bandera!.
`picoCTF{qu1t3_a_v13w_2020}`


## Notas adicionales


## Referencias

https://en.wikipedia.org/wiki/List_of_file_signatures