
## Descripción

The login system has been upgraded with a basic rate-limiting mechanism that locks out repeated failed attempts from the same source. We’ve received a tip that the system might still trust user-controlled headers. Your objective is to bypass the rate-limiting restriction and log in using the known email address: **ctf-player@picoctf.org** and uncover the hidden secret. The website is running [here](http://amiable-citadel.picoctf.net:62018/). Can you try to log in?. Download the passwords list [here](https://challenge-files.picoctf.net/c_amiable_citadel/58ec5807836ef921478972a19480bc3f3299766c984356c015298b4c8134acd2/passwords.txt).


## Solución

Inicio ingresando al sitio web.
Veo que solamente tenemos un recuadro en el que podemos ingresar nuestro correo y contraseña. Ingreso el correo que se me da: ctf-player@picoctf.org.

Descargo el archivo de contraseñas con el comando wget, y las muestro con un cat.
Tomé la primera contraseña y la ingresé, e intenté hacer login al mismo tiempo que abrí las herramientas de desarrollador en el apartado de network y exploré que la petición era la siguiente: `{"email":"ctf-player@picoctf.org","password":"oNbpNg5z"}`.

Al ver estó simplemente probé a cambiar en el apartado de contraseña la contraseña que se enviaba por la siguiente de la lista, y reenvié la petición.
En el apartado de Response estuve obteniendo false en varias ocasiones:
```
success	false
error	"Too many failed attempts. Please try again in 20 minutes."
```
Probé reenviando de esta manera un par de contraseñas distintas obteniendo el mismo resultado, hasta que en una de ellas obtuve true seguido de la bandera: 
```
|   |   |
|---|---|
|success|true|
email	"ctf-player@picoctf.org"
|   |   |
|---|---|
|firstName|"pico"|
|   |   |
|---|---|
|lastName|"player"|
|   |   |
|---|---|
|flag|"picoCTF{xff_byp4ss_brut3_1663a1a8}"|
```

`picoCTF{xff_byp4ss_brut3_1663a1a8}`
## Notas adicionales


## Referencias
