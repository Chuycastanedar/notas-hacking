
## Descripción

This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://challenge-files.picoctf.net/c_fickle_tempest/856cff883937e1cfe99e7e5b9c2fbbf08232a8135f919b1111615f007a4de03a/VaultDoor3.java)

## Solución

Inicio descargando el archivo que me dan usando el comando wget.

Veo que se trata de un archivo .java, por lo que lo abro utilizando el editor nano. Analizo un poco el código y me doy cuenta de que el programa pide una contraseña que realmente es la misma bandera, y valida si tiene `picoCTF{}` para quitarlo de la cadena.

A partir de aquí, existe un método checkPassword en el que se valida la longitud del password. Se crea un buffer alterno de 32 caracteres igual y mediante ciclos se van tomando fragmentos del password y los pasa al buffer.

Abrimos una ventana de herramientas de desarrollador en firefox y nos vamos a la parte de consola. Usaremos JavaScript para este reto. Ejecutamos `allow pasting` para permitir pegar código, declaramos una variable `var password = "jU5t_a_sna_3lpm11g54e_u_4_m4r042";` con ek contenido que copeamos del código.

Creo el buffer `var buffer = Array(32);` 

Copeo del código el código de los ciclos que extra de password y guarda en buffer.
``` javascript
for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
```

Simplemente uso el método join para unir los fragmentos en buffer y obtengo la bandera:
`buffer.join("")`

`picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_e45012}`


## Notas adicionales


## Referencias