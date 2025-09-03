## Descripción

Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `25103` to get the flag?

## Solución

Tenemos que utilizar el comando nc para conectarnos al servidor que se especifica.
Usando el puerto especificado.

``` bash
JCR_07-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 25103
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_d0c64587}
```

Así obtenemos la flag :
```
picoCTF{nEtCat_Mast3ry_d0c64587}
```
## Notas adicionales
**nc** - arbitrary TCP and UDP connections and listens
Utilizando esta herramienta permite conectarnos a un servidor en un puerto determinado.

## Referencias
[nc(1): arbitrary TCP/UDP connections/listens - Linux man page](https://linux.die.net/man/1/nc)
