
## Descripción

I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:55585/)!

## Solución

Ingreso al sitio web, y probé a subir algunos archivo.
Encontré que si agregabas uno con otra extensión no lo acepta, si contiene .png si la acepta.
Probé a buscar en el archivo robots.txt y encontré un archivo instructions.txt que decía una pista clave, se valida en el contenido del archivo al principio si es un archivo PNG.
También decía un directorio /uploads/ en el que no pude acceder pero que almacena las imágenes .png reales que subí ya que si agregaba el nombre de la imagen a la ruta podía verla.
Probé muchas cosas pero investigando, al final di con ingresar un código de una webshell en un archivo y burlando la seguridad agregamos .png al nombre del archivo php y también PNG al inicio de su contenido.
Nombre: `webshell.png.php`
Código: 
```
PNG
Código webshell

```
Ahora que tenemos el archivo subido simplemente accedemos a su ubicación desde el url y ahí mismo podemos aplicar comandos para ver el contenido del directorio, retroceder y ver el contenido de uno de los archivos que hay, lo que nos da la bandera.
`picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_d3ac625b}`

## Notas adicionales

- Webshell: Es un código php que al ejecutarse me va permitir ejecutar comandos.

## Referencias
[Ataques de Web Shell: Guía Completa para la Ciberseguridad Empresarial - Minery Report S.L.](https://mineryreport.com/blog/ataques-web-shell-ciberseguridad-empresarial/)