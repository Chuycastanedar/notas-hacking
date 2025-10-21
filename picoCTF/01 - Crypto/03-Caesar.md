
## Descripción

Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).

## Solución

Inicio descargando el mensage con el comando wget y el link.
Me descarga el siguiente archivo:
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ file ciphertext                       
ciphertext: ASCII text, with no line terminators
```

Al leerlo obtengo una bandera con formato correcto, pero con el interior encriptado:
``` bash
┌──(kali㉿kali)-[~/Downloads]
└─$ file ciphertext                       
ciphertext: ASCII text, with no line terminators
```

Desde el nombre del reto se que se trata de un algoritmo caesar o como el del reto anterior ROT13, por lo que simplemente accedo a cyberchef e ingreso la parte encriptada de la bandera, cambio las veces que se rota cada letra hasta que la cadena de caracteres tome sentido, es en 30.

Obtengo la bandera:
`picoCTF{crossingtherubiconvfhsjkou}`

## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,30)&input=e3lua29vZWpjcGRhbnF4ZXlranJiZG9mZ2txfQ