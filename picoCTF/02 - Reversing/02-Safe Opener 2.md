
## Descripción

What can you do with this file? I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/286/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

## Solución

Inicio descargando el archivo .class del programa usando el comando wget.

Como ya se menciona en la pista podemos decompilar el archivo para observar su código, pero yo apliqué el comando siguiente: 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ strings SafeOpener.class | grep picoCTF
picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_3dae8463}
```

Este comando busca todo el texto legible del archivo .class, unido con un pipe a grep que busca las coincidencias con la bandera. Como la bandera estaba guardada en texto plano obtenemos la bandera:
`picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_3dae8463}`


## Notas adicionales

- strings: Este comando extrae todo el texto legible del archivo binario.

## Referencias