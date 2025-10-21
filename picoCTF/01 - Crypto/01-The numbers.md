
## Descripción

The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Solución

Iniciamos descargando el archivo PNG con el comando wget y el link.

Abro el PNG con el comando open, observo la siguiente cadena de caracteres en la imagen: `16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }`

Obviamente notamos que corresponde a la bandera encriptada, ya que cumple con el formato y la misma pista lo dice. Sabemos que hasta antes de la primer llave debe decir picoCTF de acuerdo al formato, por lo que ya contamos con este fragmento.

Si somos observadores veremos que desde este primer fragmento el número que aparece por caracter corresponde a su posición numérica dentro del alfabeto, por lo que buscamos en google una imagen de alfabeto sin ñ con números; simplemente cambiaremos cada número por su respectiva letra y obtendremos la bandera!!.

`picoCTF{thenumbersmason}`

## Notas adicionales


## Referencias

https://www.google.com/url?sa=i&url=https%3A%2F%2Fes.dreamstime.com%2Fimagenes-de-archivo-alfabeto-con-n%25C3%25BAmeros-image37379804&psig=AOvVaw3Yc_hAdzWZzm95R_AJ0UBe&ust=1761166484125000&source=images&cd=vfe&opi=89978449&ved=0CBUQjRxqFwoTCPiJp8qWtpADFQAAAAAdAAAAABAK