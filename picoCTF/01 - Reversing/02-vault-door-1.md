
## Descripción

This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java)


## Solución

Inicio descargando el archivo que me dan usando el comando wget.

Veo que se trata de un archivo .java, por lo que lo abro utilizando el editor nano. Analizo un poco el código y me doy cuenta de que el programa pide una contraseña que realmente es la misma bandera, y valida si tiene `picoCTF{}` para quitarlo de la cadena.

A partir de aquí, existe un método checkPassword en el que se valida que la contraseña sea igual a una cadena fija de caracteres los cuales corresponden al contenido entre llaves { } de la bandera. Esta vez utiliza a `charAt()` para comparar cada uno de los caracteres y en orden aleatorio, no lo compara como una cadena completa.

Para ello copié del código el fragmento que se encarga de ello:
``` bash
               password.charAt(0)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4'
```

 Abrí nano y lo pegué, detro de charAt() agregué un 0 a la izquierda a los números de 1 dígito y guardé mi archivo como bandera.

  Luego apliqué el siguienten comando `cat bandera | sort | awk '{print($3)}' | tr -d "'" | tr -d "\n"`.
  Este último se encarga de leer el contenido de mi archivo, lo ordena a partir de los números, imprime el caracter, elimina las comillas simples y los saltos de línea.
  Obtenemos la bandera, solamente agregamos picoCTF{} de acuerdo al formato:
`picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4}`

## Notas adicionales


## Referencias