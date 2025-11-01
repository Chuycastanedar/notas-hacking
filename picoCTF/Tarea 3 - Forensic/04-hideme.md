
## Descripción

Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/261/flag.png).

## Solución

Inicio descargando el archivo con el comando wget.

Verifiqué con zsteg para encontrar datos ocultos.
Si veo, por lo que investigando encuentro y descargo la herramienta foremost. Obtengo los datos ocultos y se me guardan en una carpeta output dentro del mismo directorio.

Me cambio a output con el comando cd. 

Veo que hay dentro con ls e ingreso al directorio zip con cd.
Dentro de encuentro un archivo 00000077.zip, por lo que lo descomprimo usando `7z x 00000077.zip`.

Me da una carpeta secret, ingreso con cd y dentro tengo el archivo flag.png. Abro el archivo y es una imagen png con la bandera dentro!!
`picoCTF{Hiddinng_An_imag3_within_@n_ima9e_96539bea}`


## Notas adicionales


## Referencias

https://www.kali.org/tools/foremost/