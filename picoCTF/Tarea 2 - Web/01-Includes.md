
## Descripción

Can you get the flag?Go to this [website](http://saturn.picoctf.net:57070/) and see what you can discover.

## Solución

Ingresamos al sitio web y vemos que se trata de una página simple, que nos da contexto sobre los copybooks y tiene solamente un botón que al presionarlo nos da una pista.
Lo que hice fue inspeccionar el código de la página y accedí a la hoja de css y de js, donde encontré la mitad de la bandera en cada uno de los archivos.

`picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}`

## Notas adicionales

Many programming languages and other computer files have a directive, often called include (sometimes copy or import), that causes the contents of a second file to be inserted into the original file. These included files are called copybooks or header files. They are often used to define the physical layout of program data, pieces of procedural code and/or forward declarations while promoting encapsulation and the reuse of code.

## Referencias

