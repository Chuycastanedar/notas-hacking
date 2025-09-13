
## Descripción

The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/15796/` ([link](https://jupiter.challenges.picoctf.org/problem/15796/)) or http://jupiter.challenges.picoctf.org:15796

## Solución

Ingresamos al link que se nos da, entramos a la página de login y vemos que al intentar ingresar con el usuario que se nos proporciona no nos deja por la contraseña y aparte nos dice que de esa manera no.
Al intentar ingresar con otro usuario inventado o sin ingresar datos observamos que si nos permite hacer login.
Probé a inspeccionar y no encontré nada, por lo que la solución fue buscar en las cookies.
Vemos que al ingresar con un usuario se guarda como False, por lo que intentamos cambiar y para eso necesitaremos una extensión de Cookie editor en la que al descargarla y abrirla en la página web podremos editarla por True y recargar la página, lo que nos dará la bandera ahí mismo en la página.

## Notas adicionales

- Una cookie es un pequeño bloque de datos creado por el servidor web mientras el usuario navega un sitio web y es guardada en el dispositivo del usuario que usa para acceder.

## Referencias

[Cookie-Editor - Microsoft Edge Addons](https://microsoftedge.microsoft.com/addons/detail/cookieeditor/neaplmfkghagebokkhpjpoebhdledlfi?hl=es-419)