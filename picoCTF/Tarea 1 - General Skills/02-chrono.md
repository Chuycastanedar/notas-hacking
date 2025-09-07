
## Descripción

How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:
```
Server: saturn.picoctf.net
Port: 62645
Username: picoplayer 
Password: emrdK96SGH
```

## Solución

Empezamos por conectarnos por ssh al servidor con los datos que nos proporciona la instancia.
Por el nombre del reto y la descripción sobre automatizar tareas para correr en intervalos en los servidores linux di con chron, que se encarga de ello.
Como un modo de usar chron según investigué en el vínculo de abajo es manipular directamente el archivo donde se guardan variables de entorno o tareas `/etc/crontab` probé a aplicarle un cat a este mismo `picoplayer@challenge:~$ cat /etc/crontab` lo que me devolvió la flag directamente. `picoCTF{Sch3DUL7NG_T45K3_L1NUX_0bb95b71}`

## Notas adicionales

- Cron es el nombre del programa que permite a usuarios Linux/Unix ejecutar automáticamente comandos o scripts a una hora o fecha específica.
- Cron es un servicio
- cat /etc/crontab Mostrar el contenido del archivo donde se guardan tareas o variables de entorno etc.

## Referencias

[Manual básico de como usar Cron](https://www.linuxtotal.com.mx/?cont=info_admon_006)