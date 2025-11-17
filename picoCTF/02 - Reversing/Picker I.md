
## Descripción

This service can provide you with a random number, but can it do anything else? Connect to the program with netcat: `$ nc saturn.picoctf.net 60421` The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/513/picker-I.py).

## Solución

Ingreso con nc al reto, observo que me pide ingresar algo.
Descargo el código fuente y al analizarlo veo que hay muchas partes distractores y así.

Solamente me centro en la función win(), la cuál lee un archivo flag.txt que me dará la bandera.

La vulnerabilidad se centra en el bucle principal en la línea `eval(user_input + '()')` donde se toma a la cadena de caracteres y se ejecuta como código python por lo que solamente hace falta ingresar el nombre de la funcion win cuando me lo pida el reto y nos dará la cadena de caracteres en formato hexadecimal.

Voy a cyberchef, pego la cadena con la operación From Hex y obtengo la bandera:
`picoCTF{4_d14m0nd_1n_7h3_r0ugh_b523b2a1}`

## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg3MCAweDY5IDB4NjMgMHg2ZiAweDQzIDB4NTQgMHg0NiAweDdiIDB4MzQgMHg1ZiAweDY0IDB4MzEgMHgzNCAweDZkIDB4MzAgMHg2ZSAweDY0IDB4NWYgMHgzMSAweDZlIDB4NWYgMHgzNyAweDY4IDB4MzMgMHg1ZiAweDcyIDB4MzAgMHg3NSAweDY3IDB4NjggMHg1ZiAweDYyIDB4MzUgMHgzMiAweDMzIDB4NjIgMHgzMiAweDYxIDB4MzEgMHg3ZA