
## Descripción

Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe? You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:61253/) and good luck

## Solución

Ingresamos al sitio web.
Solamente observamos un título, y cajas de texto para ingresar usuario y contraseña. Probamos y de acuerdo al nombre del reto y pistas solamente nos menciona a las cookies.
Ya que intenté identificarme con cualquier usuario y contraseña, abro mi extensión de cookie editor y observo ya una cookie con el nombre que es clave ya que menciona secret recipe. La copeo e ingreso a cyberchef para usar from base 64, y al convertir la cadena de caracteres obtengo la bandera.
`picoCTF{c00k1e_m0nster_l0ves_c00kies_4736F6CB}`\

## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnRqTURCck1XVmZiVEJ1YzNSbGNsOXNNSFpsYzE5ak1EQnJhV1Z6WHpRM016WkdOa05DZlElM0QlM0Q&oeol=CR
