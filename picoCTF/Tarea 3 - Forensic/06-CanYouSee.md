
## Descripción

How about some hide and seek? Download this file [here](https://artifacts.picoctf.net/c_titan/4/unknown.zip).

## Solución

Inicio descargando el archivo usando el comando wget.
Observo que es un archivo comprimido .zip, por lo que lo descomprimo: `7z x unknown.zip`.

Obtengo un archivo de imagen .jpg, por lo que lo abro usando el comando open y solamente observo una imagen sin mas.

Hago uso de la herramienta exiftool para ver la información de la imagen, en el apartado Attribution URL encuentro una cadena de caracteres números, letras y al final dos == que identifico como base 64.

Usando la herramienta cyberchef con la fórmula from base 64, obtengo la bandera: `picoCTF{ME74D47A_HIDD3N_deca06fb}`.


## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnROUlRjMFJEUTNRVjlJU1VSRU0wNWZaR1ZqWVRBMlptSjlDZz09