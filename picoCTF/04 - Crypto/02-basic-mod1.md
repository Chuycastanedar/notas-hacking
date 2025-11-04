
## Descripción

We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/128/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Solución

Inicio descargando el archivo txt usando el comando wget.

En la descripción del reto prácticamente se nos proporcionan los datos necesarios para mapear los caracteres y desencriptar el mensaje, por lo que lo haremos creando un pequeño script de python.

Dentro de dicho script nos encargamos de lo siguiente:
- Abrir y leer el archivo message.txt, separar los caracteres con split y guardar en una variable.
- Declarar una variable para la bandera.
- Mediante un ciclo for recorrer los caracteres obteniendo el mod 37 de cada uno, previamente convertido a entero.
	- Mediante un if evaluar si el mod de el número actual corresponde a una letra mayúscula, número o guión bajo de acuerdo a la descripción del reto y a la tabla ascii.
	- Concatenar en la variable de la bandera.
- Al finalizar, imprimir la bandera.

``` python
numeros = open('message.txt').read().split()
flag = ' '

for numero in numeros:
        mod = int(numero) % 37
        if mod >= 0 and mod <= 25:
                c = chr(mod+65)
        elif mod >= 26 and mod <=35:
                c = chr(mod+22)
        elif mod == 36:
                c = '_'
        flag += c

print(flag)
```

Ejecutamos el script y obtenemos la bandera.
Es necesario complementar el formato con: `picoCTF{}`
`picoCTF{R0UND_N_R0UND_B6B25531


## Notas adicionales


## Referencias