
## Descripción

Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/26760321c25c9659050a37a707247690/server.py) [http://mercury.picoctf.net:52134/](http://mercury.picoctf.net:52134/)

## Solución

Descargo el archivo e ingreso al sitio.
Pruebo a ingresar el nombre de la galleta predeterminada, verifico las cookies y hay una cookie de flask.
Al echarle un vistazo al código py veo que ahí se almacenan los nombres de las galletas en un arreglo, y que toma uno de esos nombres del arreglo para crear una llave secreta para la cookie. Si corresponde a admin muestra la bandera.

Haremos uso de la herramienta flask unsign.

Con los datos de todos los nombres de las cookies, creamos otro archivo .txt para usarlo de diccionario en el ataque.
Instalaremos la herramienta flask unsign.
Hacemos uso de ella indicandole la cookie y el archivo de palabras, nos devolverá la palabra del diccionario con la que fue firmada.
Forjamos una nueva cookie de admin ahora con la opción sign, y utilizamos esta para reemplacarla en el sitio.
Podemos hacerlo desde la terminal con un curl.
Obtendremos la bandera.

`picoCTF{pwn_4ll_th3_cook1E5_478da04c}`

## Notas adicionales

- Herramienta Flask Unsign nos permite crear un ataque de fuerza bruta a la cookie para saber con que llave se cifró.

## Referencias

[Paradoxis/Flask-Unsign: Command line tool to fetch, decode, brute-force and craft session cookies of a Flask application by guessing secret keys.](https://github.com/Paradoxis/Flask-Unsign)