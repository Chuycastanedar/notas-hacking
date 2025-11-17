
## Descripción

Can you figure out how this program works to get the flag? Connect to the program with netcat: `$ nc saturn.picoctf.net 49310` The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/525/picker-III.py).

## Solución

Ingreso con nc al reto, observo las opciones del menú. Descargo el código fuente y al analizarlo veo que ahora restringen la ejecución a una lista predefinida en `func_table` y validan su longitud (128 caracteres).

Me centro en la función `write_variable`, que usa `exec` para modificar variables globales. Aunque hay un filtro que bloquea paréntesis `()` y punto y coma `;`, noté que permite el uso de comillas y operadores matemáticos.

La vulnerabilidad reside en que podemos sobrescribir la variable `func_table`. Como no puedo llamar a `win()` directamente por el filtro de paréntesis, construyo la cadena usando concatenación de strings para cumplir con el requisito de longitud.

En el menú elijo la opción 3, selecciono la variable `func_table` e ingreso el payload: `'win' + ' ' * 125`. Esto pone "win" al principio y rellena el resto con espacios hasta llegar a 128.

Luego elijo la opción 1 para ejecutar la primera función de mi nueva tabla (que ahora es `win`). Obtengo la cadena hexadecimal.

Voy a CyberChef, pego la cadena con la operación From Hex y obtengo la bandera: `picoCTF{7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_a186f9ac}`

## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg3MCAweDY5IDB4NjMgMHg2ZiAweDQzIDB4NTQgMHg0NiAweDdiIDB4MzcgMHg2OCAweDMxIDB4MzUgMHg1ZiAweDMxIDB4MzUgMHg1ZiAweDc3IDB4NjggMHgzNCAweDM3IDB4NWYgMHg3NyAweDMzIDB4NWYgMHg2NyAweDMzIDB4MzcgMHg1ZiAweDc3IDB4MzEgMHgzNyAweDY4IDB4NWYgMHg3NSAweDM1IDB4MzMgMHg3MiAweDM1IDB4NWYgMHgzMSAweDZlIDB4NWYgMHg2MyAweDY4IDB4MzQgMHg3MiAweDY3IDB4MzMgMHg1ZiAweDYxIDB4MzEgMHgzOCAweDM2IDB4NjYgMHgzOSAweDYxIDB4NjMgMHg3ZA