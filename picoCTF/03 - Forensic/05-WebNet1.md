
## Descripción

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Solución

Inicio descargando la captura de paquetes y la llave usando el comando wget y sus respectivos links.

Abrimos la captura de paquetes con la herramienta wireshark. Tenemos una comunicación efectivamente TLS como se menciona en las pistas y si intentamos seguir el stream veremos que esta encriptado.

Para ello vamos a la opción edit,  preferencias, protocolos, TLS y cargamos la llave que descargamos previamente.
Una vez que cargamos la llave el tráfico se desencripta. 
Intenté buscar la bandera de acuerdo al reto anterior pero solamente encontré una coincidencia que no era la bandera.

Seleccioné un paquete TLS, seguir Stream y en el número 0 bajando un poco encontré la bandera tal cuál.
`picoCTF{honey.roasted.peanuts}`

## Notas adicionales

- Transport Layer Security: Es un protocolo criptográfico diseñado para proveer comunicaciones seguras sobre una red de computadoras. Es altamente usado en aplicaciones como correo, mensajería instantánea pero su uso asegurando HTTPS sigue siendo el que es publicamente más visible.
- La llave se usa para cifrar los mensajes.

## Referencias

https://en.wikipedia.org/wiki/Transport_Layer_Security