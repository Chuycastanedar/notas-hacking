
## Descripción

The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:54562/) out.

## Solución

Ingreso al sitio web y analizo un poco la página.
De acuerdo al nombre de nuestro reto, me centro en revisar el archivo robots.txt agregando la ruta al url de la página.
Veo que este mismo si está disponible y nos tiene una pista ahí sobre la bandera.
Abajo tenemos varias cadenas de texto, alguna que no tiene significado aparente y otras que parecen ser de base 64.
Utilizo la herramienta cyberchef y convierto estas mismas y doy con el nombre de un archivo: `flag1.txt`, la agrego a la ruta del url y no encuentro nada.
Encuentro en otra de las cadenas otra ruta `js/myfile.txt`, la agrego al url y veo que este archivo si existe y observo la bandera.
`picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}`

## Notas adicionales


## Referencias

[CyberChef](https://gchq.github.io/CyberChef/)