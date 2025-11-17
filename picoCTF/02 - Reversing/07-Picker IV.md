
## Descripción

Can you figure out how this program works to get the flag? Connect to the program with netcat: `$ nc saturn.picoctf.net 61049` The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV).

## Solución

Ingreso con nc al reto y veo que el programa solicita una dirección de memoria para saltar a ella. Descargo el binario y uso el comando `nm` para listar los símbolos y encontrar la dirección de la función `win`:

`nm picker-IV | grep win`

Esto me devuelve `000000000040129e T win`.

Copio la dirección `40129e`, vuelvo a conectar al servidor y la pego cuando me la pide (sin el 0x). El programa salta a esa dirección y me entrega la bandera.
`picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_01672a61}`

## Notas adicionales


## Referencias