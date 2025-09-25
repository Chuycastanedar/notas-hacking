
## Descripción

Using a Secure Shell (SSH) is going to be pretty important.
Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `61008` to get the flag?You'll also need the password `6dd28e9b`. If asked, accept the fingerprint with `yes`.If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/)If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)

## Solución

Necesitamos conectarnos conectarnos por ssh al servidor, puerto con el usuario y contraseña que se nos proporcinan en la instancia.
Usamos el comando ssh seguido del nombre, agregamos un '@' y luego el servidor. Necesitamos escribir el -p para especificar el puerto, que de hecho lo menciona en las pistas lo de especificarlo.
Solamente necesitamos poner yes para entrar e ingresar la contraseña, se nos devolverá la flag.

``` bash
JCR_07-picoctf@webshell:~$ ssh ctf-player@titan.picoctf.net -p 49869
The authenticity of host '[titan.picoctf.net]:49869 ([3.139.174.234]:49869)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:49869' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_5d09a462}
Connection to titan.picoctf.net closed.
```

## Notas adicionales

- ssh [usuario]@[servidor] -p [puerto]
- -p especificar el puerto
- Las contraseñas no se ven al teclear en la terminal

- ## Referencias
