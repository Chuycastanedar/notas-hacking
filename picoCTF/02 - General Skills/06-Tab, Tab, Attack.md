
## Descripción
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/9689f2b453ad5daeb73ca7534e4d1521/Addadshashanammu.zip)

## Solución
Iniciamos descargando el archivo .zip que se nos da con el comando wget y el vínculo.
Descomprimimos el zip con unzip [Nombre del archivo.zip]
Ponemos la primera letra de la carpeta y damos tab hasta el final y nos da la bandera.

```bash
JCR_07-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/9689f2b453ad5daeb73ca7534e4d1521/Addadshashanammu.zip
--2025-09-03 17:32:09--  https://mercury.picoctf.net/static/9689f2b453ad5daeb73ca7534e4d1521/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4519 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip                           100%[===================================================================================================>]   4.41K  --.-KB/s    in 0s      

2025-09-03 17:32:09 (937 MB/s) - 'Addadshashanammu.zip' saved [4519/4519]

JCR_07-picoctf@webshell:~$ ls
Addadshashanammu.zip  README.txt
JCR_07-picoctf@webshell:~$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
JCR_07-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  README.txt
JCR_07-picoctf@webshell:~$ cd Addadshashanammu
JCR_07-picoctf@webshell:~/Addadshashanammu$ ls
Almurbalarammi
JCR_07-picoctf@webshell:~/Addadshashanammu$ cd
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
.bash_history         .bashrc               .python_history       .wget-hsts            Addadshashanammu.zip  
.bash_logout          .profile              .ssh/                 Addadshashanammu/     README.txt            
JCR_07-picoctf@webshell:~$ Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_2bcfb2ab}
```


## Notas adicionales

Para borrar todos los archivos del directorio usamos rm *
rm -rf * borra todo aun con directorios
unzip descomprime .zip en la terminal linux.
cd enter se va a la carpeta del usuario
cd - me regresa al directorio anterior del que me moví
Si ponemos la letra inicial de la carpeta primera y damos Tab cada vez nos ingresará a la carpeta siguiente

## Referencias

