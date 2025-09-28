
## Descripción

How about trying to match a regular expressionThe website is running [here](http://saturn.picoctf.net:61329/).

## Solución

Ingreso al sitio web y me encuentro con un apartado para ingresar texto y un botón que lo valida.
Al probarlo veo que aparece una alerta que me dice que no coincide, por lo que voy a inspeccionar el código de la página.
Tal como lo dice la pista me enfoco en buscar la parte que valida la cadena y encuentro la función send_request().
``` js 
function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}
```
La analicé pero me di cuenta rápido del comentario `p.....F` el cuál es la pista clave que me hizo probar picoCTF.
Es la cadena de texto que espera la función por lo que tal como está en el código, aparecerá una alerta y nos dará la bandera.

## Notas adicionales

- Expresiones regulares: Las expresiones regulares (regex o RegExp) son patrones que se utilizan para hacer coincidir combinaciones de caracteres en cadenas.
- Permiten definir reglas flexibles para buscar patrones específicos
## Referencias

[Expresiones Regulares - JavaScript | MDN](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Regular_expressions)