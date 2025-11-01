
## Descripción

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/16/challenge.zip)

The same files are accessible via SSH here: `ssh -p 55965 ctf-player@atlas.picoctf.net` Using the password `6abf4a82`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

## Solución

Inicio descargando el archivo usando el comando wget.
Observo que es un archivo comprimido .zip, por lo que lo descomprimo: `7z x challenge.zip`

Usando el comando cd ingreso a la carpeta home, luego ctf-player y drop-in. Dentro de drop-in encuentro el archivo flag.png y lo abro con el comando open, observo que se trata de una imagen con un código qr por lo que lo leo con mi teléfono celular y encuentro la bandera decodificada: `picoCTF{p33k_@_b00_7843f77c}`.

## Notas adicionales


## Referencias