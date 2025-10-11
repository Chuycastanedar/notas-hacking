
## Descripción

I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt) is all blank!


## Solución

Descargamos el archivo con el comando wget en algún directorio.
Vemos que tiene tamaño, mas no contenido.
Descargaremos pwntools para python.
En este caso nos ayudará a abrir el archivo en formato binario, buscar los caracteres y reemplazarlos por 0 o 1.
Descargamos pwntools en caso de no tenerla, luego creamos un archivo exp.py. 

Dentro de el agregamos lo siguiente:
```python
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace('b\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascci') 
data = unbits(data)

print(data)
```
Ejecutamos el archivo exp.py.
Obtendremos la bandera, estaba codificada en el archivo:
`picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}`

## Notas adicionales

- pwntools son una serie de librerías muy usadas en hacking

## Referencias

https://es.wikipedia.org/wiki/Unicode