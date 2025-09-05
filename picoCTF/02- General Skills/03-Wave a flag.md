## Descripción

Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm) has extraordinarily helpful information...
## Solución

Se nos da un link, iniciamos copiando el vínculo y descargándo el bin con nombre warm en nuestra terminal de linux utilizando el comando wget.
Ya descargado el bin continuamos modificando sus permisos para poder ejecutarlo con el comando chmod += warm.
Ejecutamos el bin con ./warm, warm es el nombre del bin.
Nos devuelve que dice que le demos -h para ayudarnos o algo así. Volvemos a ejecutar con el comando ./warm -h y no devuelve la ayuda que será la bandera.

## Notas adicionales

Comando history despliega toda la lista de comando que eh utilizado.
Comando history - c borra mi lista.
En la terminal:
- Ctrl + letra mas grande
- Ctrl - letra menor
- Ctrl L borra pantalla
- Ctrl a navega a inicio
- Ctrl e navega al final
No todos los comandos tienen -h o --help.
## Referencias
