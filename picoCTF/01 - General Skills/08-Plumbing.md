## Descripción
Sometimes you need to handle process data outside of a file. 
Can you find a way to keep the output from this program and search for the flag? 
Connect to `jupiter.challenges.picoctf.org 14291`.

## Solución

Utilizando el comando nc vamos a acceder al servidor que se nos presenta, en el puerto especificado. Este 
nos devolverá todo el contenido de un archivo donde tendremos que buscar la bandera para acreditar
el reto. Al ser tantas líneas juntas, nuestra solución mas sencilla es utilizar el comando grep para buscar la 
bandera fácilmente.

Simplemente tenemos que agregar el comando nc con el servidor y puerto, y unimos el comando grep
para buscar la bandera con la coincidencia picoCTF. Esta unión se realiza utilizando un pipe o |.

``` bash
JCR_07-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 | grep 'picoCTF'
picoCTF{digital_plumb3r_ea8bfec7}
```


## Notas adicionales
| es un pipe en linux que me permite redirigir la salida de un comando para ingresarla al siguiente comando.
Podemos unir comandos con pipe como sea necesario.
## Referencias
[All about pipes, by The Linux Information Project (LINFO)](https://www.linfo.org/pipes.html)