
## Descripción

Try [here](http://titan.picoctf.net:64117/) to find the flag

## Solución

Ingreso al sitio web y veo que se trata de un formulario, en el cuál debemos ingresar nuestros datos para iniciar sesión.
A partir de ahí aparece una segunda verificación y dice que ingresemos autenticación OTP, la cuál será la que debemos evadir para completar el reto. Entonces ingreso datos en el primer formulario y al pasar al segundo abro mi inspector en el apartado de network o hago uso de la herramienta burpsuite.
Ya que tengo abierto el inspector ingreso datos a la autenticacíon OTP en el sitio y lo envío, nos apareceran en network los métodos POST y GET. 
Seleccionamos, resend y vemos que en el envío nos aparece el opt= y el dato que ingresamos, por lo que probamos a eliminar la variable con todo y el dato y volvemos a enviarlo en el botón send.
Veremos que esto ha causado un impacto ya que nos aparece otro método POST, lo seleccionamos y si vamos a la pestaña response que es la respuesta del servidor encontraremos que nos dice que hemos sobrepasado la autenticación OTP y nos entrega la bandera:
`Welcome, earstdyugihogf you sucessfully bypassed the OTP request. Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_3e3ddc76}`

## Notas adicionales

- Una contraseña de un solo uso (OTP) es una cadena de números o caracteres que se genera y se envía a un usuario para que la utilice en un único intento de inicio de sesión o transacción.

## Referencias

[Message from EVA](https://www.entrust.com/es/resources/learn/what-is-a-one-time-password)