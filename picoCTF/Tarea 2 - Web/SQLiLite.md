
## Descripción

Can you login to this website?Try to login [here](http://saturn.picoctf.net:54357/).

## Solución

Ingreso al sitio web y me encuentro con un apartado para iniciar sesión.
Agrego admin al usuario como se me indica en la pista y pruebo con una contraseña.
Veo que me aparece login failed pero tengo de pista la consulta sql que se usa para validar el ingreso de los datos y veo que se concatenan tal cual los escribimos, por lo que es una clara oportunidad para un ataque de SQL Injection.
Dentro del apartado de contraseña ingreso: `'OR 1==1;`
Este se encargará de completar la consulta a: `SELECT * FROM users WHERE name='admin' AND password=''OR 1==1;'`
Nos aparecerá la nueva página donde dice que hemos ingresado, simplemente inspeccionamos el código y obtendremos la bandera.
`picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}`

## Notas adicionales

- SQL Injection: SQL injection is a code injection technique that might destroy your database.

## Referencias
[SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)