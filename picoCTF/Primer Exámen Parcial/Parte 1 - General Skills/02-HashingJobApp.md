
## Descripción

If you want to hash with the best, beat this test!`nc saturn.picoctf.net 60117`

## Solución

Me conecto al servidor con el comando que se me da.
Comienza y se me pide que convierta a md5 hash el texto que se me proporciona entre comillas.
De acuerdo a la pista me dice que puedo utilizar un conversor online, por lo que hago uso del que agregué en las referencias.
```bash
Please md5 hash the text between quotes, excluding the quotes: 'Hollywood'
Answer: 
1ac441036f927b9815ba1137464ee064

```
Simplemente realizo la conversión, ingreso la respuesta y repito unas cuantas veces hasta que finaliza y obtengo la bandera!.
`picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}`

## Notas adicionales

- El MD5 es un protocolo criptográfico que se usa para autenticar mensajes y verificar el contenido y las firmas digitales.

## Referencias

[Encriptaro hash MD5 online](https://hash.online-convert.com/es/generador-md5)
[¿Qué es el algoritmo hash MD5 y cómo funciona?](https://www.avast.com/es-es/c-md5-hashing-algorithm)