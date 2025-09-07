
## Descripción

Can you read files in the root file?
The system admin has provisioned an account for you on the main server:`ssh -p 58669 picoplayer@saturn.picoctf.net`Password: `yX-YQgX-vS`Can you login and read the root file?

## Solución

Iniciamos conectándonos al servidor con los datos que se nos proporcionan.
Si intentamos acceder a /root nos daremos cuenta que no es posible de ninguna manera ya que no contamos con los permisos necesarios ni acceder como super usuario ni con la contraseña que se nos proporciona.
Investigué y usé el comando sudo -l para ver que comandos puede ejecutar mi usuario con sudo,  y me percaté que decía lo siguiente:
```bash
User picoplayer may run the following commands on challenge: (ALL) /usr/bin/vi
```

Investigué y vi es un editor de texto que en este caso tenemos con permisos, por lo que intente el comando
``` bash
sudo vi /root
```

Me abrió la carpeta /root desde el y con las flechas me dirigí a un archivo flag.txt, solo presione enter y encontre la flag.


## Notas adicionales

- sudo -l Comando para ver que comandos podemos ejecutar desde el usuario actual con sudo
- vi Editor de texto, puede contar con permisos su

## Referencias

[Linux sudo: ejecutar comandos con privilegios root - IONOS México](https://www.ionos.mx/digitalguide/servidores/configuracion/linux-sudo/)

[Cómo usar el editor VI en Linux | Diario de Linux](https://www.linuxjournal.com/content/how-use-vi-editor-linux)