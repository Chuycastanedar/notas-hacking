
## Descripción

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Solución

Inicio descargando la captura de paquetes y la llave usando el comando wget y sus respectivos links.

Abrimos la captura de paquetes con la herramienta wireshark. Tenemos una comunicación efectivamente TLS como se menciona en las pistas y si intentamos seguir el stream veremos que esta encriptado.

Para ello vamos a la opción edit,  preferencias, protocolos, TLS y cargamos la llave que descargamos previamente.
Una vez que cargamos la llave el tráfico se desencripta. Vamos a edit find y en el detalle de los paquetes buscaremos una cadena con coindicencias picoCTF; encontraremos la bandera.
`picoCTF{nongshim.shrimp.crackers}`

## Notas adicionales

- Transport Layer Security: Es un protocolo criptográfico diseñado para proveer comunicaciones seguras sobre una red de computadoras. Es altamente usado en aplicaciones como correo, mensajería instantánea pero su uso asegurando HTTPS sigue siendo el que es publicamente más visible.
- La llave se usa para cifrar los mensajes.

## Referencias 

https://en.wikipedia.org/wiki/Transport_Layer_Security