
## Descripción

Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:17781/](http://mercury.picoctf.net:17781/)

## Solución

Ingresamos a la página y vemos un apartado para "buscar" las galletas. Al ingresar vemos que nos aparece que no es válida pero si usamos la que nos sugiere si, usando el cookie editor vemos que la cookie tiene el valor de 0 por lo que si probamos el 1 vemos que hay respuesta y si seguimos con 2 igual; el problema es que no es optimo buscar de una en una por que no es rápido.

Ingresamos a la terminal y lo hacemos con el comando:
```bash
for i in {0..20}; do curl -s http://mercury.picoctf.net:17781/check -H "Cookie: name=$i"; done | grep picoCTF 
```

Donde haciendo uso de un ciclo for buscamos con curl las cookies y filtramos con un grep, esto hace que se busque del 0 al 20 y devuelve la bandera solamente.  `picoCTF{3v3ry1_l0v3s_c00k135_bb3b3535}`

## Notas adicionales

- Es mucho más rápido automatizar esto desde la terminal con un ciclo y algunos comandos.

## Referencias

[picoCTF 2021 writeup [12] - Web - Cookies](https://www.youtube.com/watch?v=LseQ-XWCXVo&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=12)