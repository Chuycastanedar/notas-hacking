
## Descripción

Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:62638/) to find the flag

## Solución

Ingresamos al sitio y nos encontramos con 3 apartados: Home, About y Contact.
Si exploramos la página veremos que hay varias pistas aparte de las que se nos dan en el reto.
Si nos vamos al apartado de About que es donde nos vamos a centrar, veremos la pista de que inspeccionemos por lo que inspeccionamos el código justo de ahí y si lo analizamos a detalle encontramos una cadena de caracteres que junto a la pista sobre que la bandera puede estar encriptada damos que es posiblemente esa.
`notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMDJjZGNiNTl9`

Entramos a cyberchef y la pegamos, convertimos y obtenemos que es base 64 y veremos la bandera.

## Notas adicionales

- Si ves una cadena larga que solo tiene letras, números y termina en `=` o `==`, ¡es Base64!
## Referencias

[CyberChef](https://gchq.github.io/CyberChef/)