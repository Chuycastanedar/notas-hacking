
## Descripción

Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/160/cipher.txt) using this key "CYLAB".

## Solución

Inicio descargando el mensaje cifrado con el comando wget.

Copeo la bandera cifrada y me dirijo a cyberchef, usando la operación vigenere y la llave obtengo la bandera:

`picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}`

## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfMjk1MWM4OWZ9Cg