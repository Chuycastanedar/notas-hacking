
## Descripción

Can you open this safe? I forgot the key to my safe but this [program](https://artifacts.picoctf.net/c/83/SafeOpener.java) is supposed to help me with retrieving the lost key. Can you help me unlock my safe? Put the password you recover into the picoCTF flag format like: `picoCTF{password}`

## Solución

Inicio descargando el archivo del programa en java haciendo uso del comando wget.

Analizo a detalle el código y rápido observo el método openSafe() el cuál guarda en una variable llamada encodeKey una cadena de caracteres que fácilemte detecto como base 64.

Esté método compara el password con esta variable y valida si es o no.

Copeo esta cadena de caracteres y en mi terminal la devuelvo de base 64 con el comando: 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ echo "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz" | base64 -d 
pl3as3_l3t_m3_1nt0_th3_saf3
```

Añado el formato a la bandera:
`picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}`


## Notas adicionales


## Referencias