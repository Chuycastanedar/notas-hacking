
## Descripción

Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/56816/` ([link](https://jupiter.challenges.picoctf.org/problem/56816/)) or http://jupiter.challenges.picoctf.org:56816

## Solución

Inicio ingresando a la página web, en la cual no podemos encontrar nada sobre la bandera.
Comienzo a inspeccionar el código utilizando las herramientas de desarrollador del navegador y encuentro el fragmento de Java Script con la lógica y dentro del cual logro ver que se ha aplicado ofuscación (previamente lo investigué) para volver el código más confuso.
Después de analizarlo encuentro que la bandera se está directamente en esta parte del código fragmentada en partes sin orden y guardada en un array de strings.

`var _0x5a46 ['37115}','_again_3','this','Password\x20Verified','Incorrect\x20password','getElementById','value','substring','picoCTF{','not_this'];`

Simplemente yo ignoré todo para no confundirme con la ofuscación, como se la estructura de la bandera tome los fragmentos e intenté darle orden y sentido y la encontré.
`picoCTF{not_this_again_337115}`

## Notas adicionales

- Obfuscation: Ofuscación en español, es el proceso de hacer que algo sea más difícil de entender, confuso o poco claro de forma intencionada.
- En el desarrollo de software, la **ofuscación de código** es la técnica de modificar el código fuente o el código máquina de un programa para que sea muy difícil de leer y comprender para un ser humano, pero que siga siendo perfectamente funcional para una computadora.

## Referencias

[Google Gemini](https://gemini.google.com/app?hl=es)
Me explicó obfuscation.