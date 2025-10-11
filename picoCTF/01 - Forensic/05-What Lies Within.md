
## Descripción

There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?


## Solución

Descargo la imagen con el comando wget.
Podemos simplemente subir la imagen a un sitio web de esteganografía para decodificar el mensaje y encontrar la bandera.
Tambíen haciendo uso en terminal de la herramienta zsteg. Probará todas sus técnicas y podemos encontrar la bandera haciendo uso de un grep para filtrarla rápidamente.

picoCTF{h1d1ng_1n_th3_b1t5


## Notas adicionales

- Esteganografía: Tecnica que implica ocultar información sensitiva dentro de un archivo o mensaje ordinario no secreto para que no sea detectado.
- La información confidencial se extraerá del archivo o mensaje ordinario en su destino evitando así la detección.
- Es un paso adicional que se puede usar junto con el cifrado para ocultar datos.

- Hay varios tipos de esteganografía: En texto, imágenes, audio, video, metadatos, incluso en paquetes de red, etc.

- La esteganografía es un método para esconder que la comunicación está tomando lugar, evitando que los datos confidenciales sean expuestos.
- La criptografía es un método en el cual se utiliza una manipulación de los datos para transformarlos de otra forma, lo cual también pudiera levantar sospechas de que algo se oculta.
## Referencias

https://stylesuxx.github.io/steganography/