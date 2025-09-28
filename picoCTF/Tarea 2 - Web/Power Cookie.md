
## Descripción

Can you get the flag?Go to this [website](http://saturn.picoctf.net:59033/) and see what you can discover.

## Solución

Ingreso al sitio web y veo simplemente un título y un botón.
Dice que continuar como invitado y al dar clic no obtenemos nada. Dentro de las pistas se nos dice sobre modificar cookies, por lo que hacemos uso de nuestra herramienta cookie editor y veremos que la cookie que tenemos es isAdmin y contiene el valor de 0.
Simplemente necesitamos modificar la cookie a 1, recargar la página y obtenemos la bandera.
`picoCTF{gr4d3_A_c00k13_65fd1e1a}`

## Notas adicionales


## Referencias