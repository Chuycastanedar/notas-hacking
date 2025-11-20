
## Descripción

This service provides you an encrypted flag. Can you decrypt it with just N & e? Connect to the program with netcat: `$ nc verbal-sleep.picoctf.net 50438` The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_verbal_sleep/c798cbe85b3e431345406f393827b9b905481b5fcd6d4b4a845527ee0602da9b/encrypt.py).

## Solución

Me conecto al reto usando nc verbal-sleep.picoctf.net 50438. El servicio me entrega un módulo N, un exponente e y un mensaje cifrado. 

Esto indica una vulnerabilidad de Factor Primo Compartido. Si el servidor reutiliza uno de los números primos (p) para generar diferentes módulos, podemos hallar ese factor común calculando el Máximo Común Divisor (MCD) de dos módulos distintos.

Realizo dos conexiones al servidor y anoto los valores:

    Conexión A: Obtengo N1​ y el texto cifrado C1​.

    Conexión B: Obtengo N2​.

Creo un script en Python que utiliza math.gcd(N1, N2). El resultado es mayor que 1, lo que confirma que comparten un primo p. Con p conocido, calculo el segundo factor q simplemente dividiendo N1​/p.

Teniendo p y q, calculo ϕ(n), genero la clave privada d y descifro el mensaje C1​.
`picoCTF{tw0_1$_pr!m341c6ed35}`


## Notas adicionales


## Referencias