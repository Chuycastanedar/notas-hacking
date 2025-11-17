
## Descripción

You will find the flag after analysing this apk Download [here](https://artifacts.picoctf.net/c/449/timer.apk).

## Solución

Inicio descargando el archivo .apk usando el comando wget.

Desde las pistas se me menciona a jadx para decompilar el archivo y obtener la bandera, en mi caso ya contaba con jadx instalado pero si no hay que instalarlo.
Usé el siguiente comando: `jadx-gui /home/kali/Downloads/timer.apk`.

Este, me abre la apk decompilada con la interfaz que te permite navegar por las clases.

Uso la barra de búsqueda ingresando picoCTF para encontrar la coincidencia de la bandera y logro dar con ella:
`picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}`


## Notas adicionales

- jadx: Herramienta para decompilar.
- jadx-gui: Entorno de escritorio.

## Referencias