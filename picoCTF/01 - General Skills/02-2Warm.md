## Descripción

Can you convert the number 42 (base 10) to binary (base 2)?

## Solución
Convertir el número decimal a su representación en binario.

### Forma 1
Se divide repetidamente entre 2, anotando los restos, y luego se leen de abajo hacia arriba. 

- 42 ÷ 2 = 21, resto 0
- 21 ÷ 2 = 10, resto 1
- 10 ÷ 2 = 5, resto 0
- 5 ÷ 2 = 2, resto 1
- 2 ÷ 2 = 1, resto 0
- 1 ÷ 2 = 0, resto 1

### Forma 2
Podemos utilizar función bin() en python que se encargará de convertirlo y nos devolverá el resultado.

``` bash
JCR_07-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)
'0b101010'
```

```
picoCTF{101010}
```
 
## Notas adicionales

También podemos utilizar la calculadora o cualquier conversor, a mano, solo necesitamos resolverlo.
La idea es usar la IA para ayudarnos en cosas generales y no para que nos realice el trabajo, para aprender.


## Referencias
[Cómo pasar de decimal a binario paso a paso y fácilmente](https://okdiario.com/howto/como-pasar-decimal-binario-paso-paso-2125014)
[bin | Interactive Chaos](https://interactivechaos.com/es/python/function/bin)
