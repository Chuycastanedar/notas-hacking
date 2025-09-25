
## Descripción

There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/`
Do you think you can log us in? Try to see if you can login!

## Solución

Ingresamos al sitio web y vemos que no hay mucho que hacer, aunque tenemos varias pistas sobre SQL y la base de datos.
Tenemos un apartado de inicio de sesión para el admin e intentamos acceder pero solo da error.
Si revisamos el código apreciamos un campo oculto llamado debug y que está establecido en 0 por lo que abrimos el inspector y lo establecemos en 1, al intentar otro acceso nos vuelve a dar error pero encontramos una pista, la sentencia SQL que se completa con los datos ingresados para validar el usuario en la DB.

Esto nos dice que al momento de ingresar datos solamente se concatenan y no hay un manejo de ellos por lo que es posible aplicar una técnica de SQL Injection para lograr que al ingresar los datos de la contraseña logremos que se genere una sentencia SQL que nos permita acceder a datos de la base de datos.
Para ello solamente completamos el usuario como admin y en contraseña lo siguiente: `' OR 1==1;`.
Esto hace que la sentencia se complete: 'SELECT * FROM users WHERE name= 'admin' AND password='' OR 1=1;' 
En teoría la sentencia es válida y nos haría obtener todo de la tabla users; en este reto nos dará la bandera.

## Notas adicionales

- SQL Injection es una tecnica utilizada en hacking que se encarga de introducir de cierta manera caracteres para lograr completar la sentencia que accede a la DB y obtener acceso a datos.

## Referencias

[picoCTF 2019 writeup [7] - Web - Irish-Name-Repo 1](https://www.youtube.com/watch?v=0EDbUSDqrng&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=7)