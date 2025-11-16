
## Descripción

In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://challenge-files.picoctf.net/c_fickle_tempest/f2e90d844f6e64092bc1a611c16d52a832e0f2cb856991bc9fa205bcd0cd31bd/VaultDoor5.java)

## Solución

Inicio descargando el archivo que me dan usando el comando wget.

Veo que se trata de un archivo .java, por lo que lo abro utilizando el editor nano. Analizo un poco el código y me doy cuenta de que el programa pide una contraseña que realmente es la misma bandera, y valida si tiene `picoCTF{}` para quitarlo de la cadena.

A partir de aquí, existe un método checkPassword que recibe el contenido y lo convierte a bytes y manda a otra función urlEncode.

Se  hace una codificación, regresa y se convierte a bytes nuevamente y luego se codifica en base 64 con otra función. Al final se compara con otra cadena de texto.

Para esto, vamos a decodificar de base 64 y url encode la cadena de caracteres codificada con la que se compara para obtener la bandera.

Copeamos y vamos a cyberchef, pegamos la cadena de caracteres sin las comillas y signo + y vemos que cyberchef ya la reconoce por lo que doy clic en la varita mágica. Cyberchef automáticamente aplica From Base 64 y seguido URL Decode por lo que ya obtenemos la bandera lista, solamente agregamos `picoCTF{}` para el formato.

`picoCTF{c0nv3rt1ng_fr0m_ba5e_64_4bb22721}`


## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)URL_Decode(true)&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm1KVFkySlRjeUpUTXdKVFprSlRWbUpUWXlKVFl4SlRNMUpUWTFKVFZtSlRNMkpUTTBKVFZtSlRNMEpUWXlKVFl5SlRNeUpUTXlKVE0zSlRNeUpUTXg