
## Descripción

We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar). The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.

## Solución

Inicio descargando el archivo .tar que contiene los archivos usernames.txt y passwords.txt usando el comando wget.

Desenpaqueto el archivo: `tar -xvf leak.tar `.

Ingreso al directorio con el comando cd y al explorar ambos archivos veo solamente usuarios y contraseñas en vertical que corresponden cada uno a la del otro archivo en la misma posición.

Debido a esto uso el comando paste que se encarga de unir ambos archivos linea por linea, que unido a un grep busca coincidencias con el nombre de usuario que se nos indica:
```bash
┌──(kali㉿kali)-[~/Downloads/leak]
└─$ paste usernames.txt passwords.txt | grep "cultiris" 
cultiriscvpbPGS{P7e1S_54I35_71Z3}
```

Como resultado encontramos el usuario que debido al paste está unido a la contraseña que fácilmente identificamos con la estructura de la bandera. `cvpbPGS{P7e1S_54I35_71Z3}`

Es posible observar que las letras no corresponden por lo que entro a cyberchef y pruebo con un cifrado sencillo como ROT 13 y encuentro la bandera: `picoCTF{C7r1F_54V35_71M3}`

## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=Y3ZwYlBHU3tQN2UxU181NEkzNV83MVozfQ