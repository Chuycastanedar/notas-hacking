## Descripción

Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer. `ssh -p 63292 ctf-player@saturn.picoctf.net`. The password is `d8819d45`

  

Hint : What programs do you have access to?

## Solución

  

Pensando en la pista,  hacemos un `help`, para ver los comandas a que podemos usar en el sell, y vemos que se puede usar `echo` para revisar directorios a falta de `ls` o `cat`.

luego buscamos la forma de como imprimir el contenido de archivos con `echo`.

```bash

Specialer$ help

...

 echo [-neE] [arg ...]                                    time [-p] pipeline

 ...

Specialer$ echo *

abra ala sim

Specialer$ echo */*

abra/cadabra.txt abra/cadaniel.txt ala/kazam.txt ala/mode.txt sim/city.txt sim/salabim.txt

Specialer$ echo "$(<abra/cadabra.txt)"

Nothing up my sleeve!

Specialer$ echo "$(<abra/cadaniel.txt)"

Yes, I did it! I really did it! I'm a true wizard!

Specialer$ echo "$(<ala/kazam.txt)"

return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_c42168d9}

```

## Notas

`echo "$(<file.txt)"` el sustituto de `cat file.txt`

## Referencias

[echo][https://runcloud.io/blog/echo-command-in-linux&]

[cat-without-cat][https://jarv.org/posts/cat-without-cat/]