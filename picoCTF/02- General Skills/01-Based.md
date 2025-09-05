## Descripción

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 15130`.

## Solución

Necesitamos conectarnos con nc a donde se nos indica. Luego nos dará la cadena en binario y utilizando cyberchef la convertimos y la salida se la devolvemos a la terminal. Repetimos este paso 2 veces más con las cadenas que nos da y al final nos dará la flag.

``` bash
JCR_07-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 15130
Let us see how data is stored
colorado
Please give the 01100011 01101111 01101100 01101111 01110010 01100001 01100100 01101111 as a word.
...
you have 45 seconds.....

Input:
colorado
Please give me the  143 150 141 151 162 as a word.
Input:
chair
Please give me the 6d6170 as a word.
Input:
map
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_02167de8}
```
## Notas adicionales

En cyberchef el símbolo de varita convierte automáticamente.
## Referencias

[CyberChef](https://gchq.github.io/CyberChef/)