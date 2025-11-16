
## Descripción

Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java)


## Solución

Inicio descargando el archivo que me dan usando el comando wget.

Veo que se trata de un archivo .java, por lo que lo abro utilizando el editor nano. Analizo un poco el código y me doy cuenta de que el programa pide una contraseña que realmente es la misma bandera, y valida si tiene `picoCTF{}` para quitarlo de la cadena.
A partir de aquí, existe un método checkPassword en el que se valida que la contraseña sea igual a una cadena fija de caracteres los cuales corresponden al contenido entre llaves { } de la bandera, agregamos `picoCTF{}` y la obtenemos!.
`picoCTF{w4rm1ng_Up_w1tH_jAv4_eec0716b713}`

## Notas adicionales

- No se debe hacer esto de guardar dentro del código la contraseña así en texto plano.

## Referencias