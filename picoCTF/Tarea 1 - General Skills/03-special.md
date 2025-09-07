
## Descripción

Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.`ssh -p 56030 ctf-player@saturn.picoctf.net`The password is `3f39b042`

## Solución


## Notas adicionales

Inicio conectándome por SSH al servidor con los datos que se nos dan.
Intento teclear comandos y luego veo que no se puede, después de intentos, la pista y de todo investigo y doy con expansión de parámetros y variables donde al principio no veo respuestas diferentes.
``` bash
Special$ {parameter?ls}
{parameter?ls} 
sh: 1: {parameter?ls}: not found
Special$ {parameter=ls}
{parameter=ls} 
sh: 1: {parameter=ls}: not found
Special$ ${parameter?ls}
${parameter?ls} 
sh: 1: parameter: ls
Special$ ${:ls}
${:ls} 
sh: 1: Bad substitution
```
Logro dar con la forma de teclear los comandos.

``` bash
Special$ ${parameter=ls}
${parameter=ls} 
blargh
Special$ ${parameter=cat blargh}
${parameter=cat blargh} 
cat: blargh: Is a directory
Special$ ${parameter=cd blargh}
${parameter=cd blargh} 
Special$ ${parameter=ls blargh}
${parameter=ls blargh} 
flag.txt
Special$ ${parameter=cat < blargh/flag.txt}
${parameter=cat < blargh/flag.txt} 
cat: '<': No such file or directory
picoCTF{5p311ch3ck_15_7h3_w0r57_f906e25a}
```
Se que blargh es un directorio, y dentro de blargh hay un .txt que al aplicar un cat y asignarlo a parameter nos da el contenido, que se trata de la bandera!.

## Referencias

[Expansión de la carcasa](https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_03_04.html)