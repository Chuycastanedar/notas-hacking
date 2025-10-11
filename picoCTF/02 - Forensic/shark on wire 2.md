
## Descripción

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Solución

Descargamos el archivo con el comando wget en algun directorio.
Se trata de un archivo de captura de paquetes, por lo que lo abrimos con wireshark.
Lo que más se aprecia es tráfico UDP, por lo que tomaremos uno de los primeros paquetes que se aprecian e iremos a follow UDP Stream.
Al analizar estos cambiando de Stream veremos que hay algunos que parecen ser fragmentos de bandera pero no completos.
Vamos a filtrarlos con el puerto 22: `udp.dstport==22`.

Todas las coincidencias en el puerto origen va variando, lo que haremos será abrir en la terminal pyton y usar chr() para ver a que corresponde cada uno de ellos las 3 cifras después del 5.

Al convertir todas, obtendremos la bandera...


## Notas adicionales


## Referencias

