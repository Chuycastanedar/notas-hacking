
## Descripción

Can you figure out how this program works to get the flag? Connect to the program with netcat: `$ nc saturn.picoctf.net 55640` The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/522/picker-II.py).

## Solución

Ingreso con nc al reto, observo que me pide ingresar algo.
Descargo el código fuente y al analizarlo veo que hay muchas partes distractores y así.

Solamente me centro en la función win(), la cuál lee un archivo flag.txt que me dará la bandera.

La vulnerabilidad del reto anterior fue arreglada ya que ahora al ingresar win cuando el programa me pide la entrada la nueva función filter no permite que win se ejecute.

Aún podemos evadir esto ingresando lo siguiente: `globals()['w' + 'i' + 'n']`. Este evade la función y obtenemos la cadena de caracteres en hex de la bandera.

Voy a cyberchef, pego la cadena con la operación From Hex y obtengo la bandera:
`picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_0b5f1131}`


## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg3MCAweDY5IDB4NjMgMHg2ZiAweDQzIDB4NTQgMHg0NiAweDdiIDB4NjYgMHgzMSAweDZjIDB4MzcgMHgzMyAweDcyIDB4MzUgMHg1ZiAweDY2IDB4MzQgMHgzMSAweDZjIDB4NWYgMHg2MyAweDMwIDB4NjQgMHgzMyAweDVmIDB4NzIgMHgzMyAweDY2IDB4MzQgMHg2MyAweDM3IDB4MzAgMHg3MiAweDVmIDB4NmQgMHgzMSAweDY3IDB4NjggMHgzNyAweDVmIDB4MzUgMHg3NSAweDYzIDB4NjMgMHgzMyAweDMzIDB4NjQgMHg1ZiAweDMwIDB4NjIgMHgzNSAweDY2IDB4MzEgMHgzMSAweDMzIDB4MzEgMHg3ZCA