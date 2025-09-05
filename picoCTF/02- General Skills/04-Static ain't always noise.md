## Descripción

Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static)? This [BASH script](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh) might help!

## Solución

Necesitamos descargar el archivo bin y el script que se nos dan utilizando el comando wget con el vínculo.
Podemos simplemente utilizar un strings al bin static usando un pipe con un grep para buscar las coincidencias de "pico" y nos da la bandera.

```bash
JCR_07-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_f5aeda17}
```


## Notas adicionales

Comando file * nos devuelve que tipo de archivos son cada uno de los que hay en el directorio.

## Referencias
