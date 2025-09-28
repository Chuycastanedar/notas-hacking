
## Descripción

I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster!Browse [here](http://titan.picoctf.net:59021/), and find the flag!

## Solución

Ingreso al sitio web y solamente se me dan varias pistas y contexto sobre la minificacíon.
Pruebo a ver el código de la página y me encuentro con todo un código en una misma línea, sin entenderse.
Cierro y me voy a inspeccionar y sources, y al seleccionar el archivo abro todo el código pero esta vez acá lo veo con un formato legible por su estructura, por lo que simplemente bajo y encuentro dentro de este mismo, la bandera.

## Notas adicionales

- La minificación reduce el tamaño del código, pero no cambia su funcionalidad.
- Unminify es el proceso inverso a la minificación de código, que restaura archivos de lenguaje como JavaScript, CSS y HTML de su formato comprimido a un formato legible y estructurado, haciéndolos más fáciles de leer, entender y depurar para los desarrolladores humanos.

## Referencias