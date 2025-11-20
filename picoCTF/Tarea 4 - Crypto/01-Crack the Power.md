
## Descripción

We received an encrypted message. The modulus is built from primes large enough that factoring them isn’t an option, at least not today. See if you can make sense of the numbers and reveal the flag. Download the [message](https://challenge-files.picoctf.net/c_amiable_citadel/d75bf3f0753b354c1fabcaec0bdeb5902d67448835d57a0b0b268560a19f16a3/message.txt).

## Solución

Ingreso al reto y descargo el mensaje cifrado. La descripción me da pistas cruciales: menciona que el módulo N es demasiado grande para ser factorizado (por lo que descarto ataques tradicionales de factorización de primos), pero insinúa que ciertos valores son "más pequeños de lo habitual" y sugiere invertir el cifrado sin usar N.

Analizo los datos del problema. Tengo un exponente e=20 y un texto cifrado c extremadamente grande.

En RSA estándar, el cifrado es c≡me(modN). Normalmente, me es muchísimo más grande que N, por lo que la operación de módulo "envuelve" el número, haciéndolo difícil de revertir sin la clave privada.

Sin embargo, si el mensaje m es corto y el exponente e es pequeño (o el módulo N es exageradamente grande), puede ocurrir que me<N. Cuando esto pasa, la operación de módulo no tiene efecto, y la ecuación se simplifica a una igualdad aritmética simple:

c=me

Para recuperar el mensaje original m, simplemente necesito calcular la **raíz e-ésima** de c:

Utilizo Python con la librería `gmpy2`.

Creo el siguiente script para calcular la raíz 20 (ya que e=20) del texto cifrado:

1. Importo `gmpy2`.
    
2. Defino c y e.
    
3. Uso `gmpy2.iroot(c, e)` para calcular la raíz entera exacta.
    
4. Convierto el número resultante (que es el mensaje en formato entero) a bytes y luego a texto ASCII.
    

El script decodifica los bytes y me entrega la bandera.

`picoCTF{t1ny_e_9b88056f}`


## Notas adicionales


## Referencias