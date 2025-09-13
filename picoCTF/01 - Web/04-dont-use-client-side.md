
## Descripción

Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/17682/` ([link](https://jupiter.challenges.picoctf.org/problem/17682/)) or http://jupiter.challenges.picoctf.org:17682

## Solución

Inicio ingresando al portal super seguro e intento ingresar algo y verificar pero todo son mensajes de error.
Al no ver otra manera doy clic derecho, inspeccionar y Sources donde me encuentro con el código de la página con algo de HTML, CSS y Java Script. 
Analicé el código de JS y me doy cuenta que ahí mismo hay una función con una serie de estructuras if que se encargan de comparar fragmentos de la cadena de texto que ingresemos con otras cadenas, para finalmente validarla con un alert.
``` bash
function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '706c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_b') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == '5}') {
                  alert("Password Verified")
                  }
                }
              }
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
```
Al ver esto me doy cuenta que la bandera y la respuesta esperada por el portal es la misma y se encuentran en la misma función.
Solamente es cuestión de ordenar los fragmentos de acuerdo al orden de las multiplicaciones que se realizan a la variable split dentro de substring para fragmentar la cadena y compararlo.
El resultado es: `picoCTF{no_clients_plz_b706c5}`

## Notas adicionales

- substring(inicio, fin) función para obtener un fragmento de una cadena.

## Referencias
