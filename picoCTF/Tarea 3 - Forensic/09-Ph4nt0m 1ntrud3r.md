
## Descripción

A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/b6fbb3a5560749f838cdc6db4950985767c4691db3a7b34a220e5654ee39e700/myNetworkTraffic.pcap) and try to get the flag.

## Solución

Inicio descargando el archivo en un directorio usando el comando wget.
Abro la captura de paquetes utilizando la herramienta wireshark, observo varios paquetes TCP. En las pistas veo que se menciona algo del tiempo.

Logro ver que los paquetes tienen una carga al parecer en base 64, lo que hago es filtrar por tamaño de longitud de 12 y 4: `tcp.len==12 || tcp.len==4`.

De esta manera obtengo los paquetes con esta longitudy de acuerdo a las pistas hago clic en el apartado de time para ordenar por tiempo.

Simplemente en ese orden y en esos paquetes voy seleccionando en ese orden y abajo en Retransmited TCP Segment data hago clic derecho y voy a Show Packet Bytes... donde encuentro una cadena de caracteres en base 64. Puedo ahí mismo seleccionar la opción Base 64 que ya decodifica la cadena y uniendo estos fragmentos obtengo la bandera completa: `picoCTF{1t_w4snt_th4t_34sy_tbh_4r_36f4a666}`.


## Notas adicionales


## Referencias