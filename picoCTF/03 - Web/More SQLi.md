
## Descripción

Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:59445/).

## Solución

Ingresamos al sitio web y si probamos a ingresar sesión con cualquier cosa de ejemplo veremos que nos aparece directamente la sentencia SQL que se utiliza para acceder a la DB, y que nuestros datos se concatenan y no se procesan.
Esto nos dice que es posible hacer un ataque de SQL Injection, por lo que al ingresar en el password lo siguiente:
` ' OR 1=1; -- //`  haremos que efectivamente sobrepasemos el fallo.

`picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8b7cc2a}`

## Notas adicionales


## Referencias

[SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)