
## Descripción

Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).

## Solución

Inicio descargando el archivo encriptado.
Lo leo con un cat y rápidamente observo que se trata de una cadea en base 64, por lo que desencripto este contenido con el comando base64 -d:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ cat enc_flag | base64 -d
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='
```

Obtengo la cadena, pero solamente debo de tomar la parte de dentro de las comillas simples. Guardo esta nueva cadena y la vuelvo a desencriptar de base 64; obtengo la bandera en el formato correcto pero encriptada aún.

La copeo y llevo a cyberchef y pruebo con ROT13, al probar con 19 rotaciones obtengo la bandera desencriptada:
`picoCTF{caesar_d3cr9pt3d_a47c6d69}`

## Notas adicionales

- Cuando tenemos == al final de una cadena de caracteres y números es posiblemente base 64.

## Referencias

https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,19)&input=d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ