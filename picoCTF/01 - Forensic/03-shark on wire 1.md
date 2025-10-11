
## Descripción

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Solución

Descargo el archivo con un wget.
Haremos uso de la herramienta Wireshark, abrimos dentro de ella el archivo que descargamos. Podemos analizar las capturas de un tráfico de red, y hay muchos paquetes con protocolo UDP.
En uno de los paquetes UDP de acuerdo a una de las pistas vamos a la opción de follow y stream que es un conjunto de paquetes que pertencen a una misma comunicación; analizamos y no vemos mucho por lo que vamos cambiando de stream y en uno de ellos creo en el 6 encontramos la bandera.
`picoCTF{StaT31355_636f6e6e}`

## Notas adicionales

- Una captura de paquetes pcap es un API que nos permite capturar tráfico vivo de la red, paquetes de datos que van viajando de las capas 2 y 7 del modelo OSI.
- Posteriormente usamos un wireshark para crear un archivo con extensión pcap donde se guarde esa información de los paquetes de la red.
- Puede tener formatos: Libpcap, WinPcap y PCAPng.
- Es usado para ver tráfico en el protocolo TCP UDP.

## Referencias

https://www-comparitech-com.translate.goog/net-admin/pcap-guide/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=tc