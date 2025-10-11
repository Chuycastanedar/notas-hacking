
## Descripción

Python scripts are invoked kind of like programs in the Terminal... 
Can you run [this Python script](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py) using [this password](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/pw.txt) to get [the flag](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/flag.txt.en)?

## Solución

Comienzo descargando los tres archivos: El script py, la contraseña y la bandera encriptada.
Para esto hago uso del comando wget y el link a cada uno de ellos.
Ya que los tengo en mi directorio leí cada uno de ellos con un  cat, pero al no encontrar ejecuté el script con el comando python.
`python ende.py`
Veo que me regresa: `Usage: ende.py (-e/-d) [file]` por lo que pruebo las opciones y me manda errores.
Analicé el código del script y al final veo que esta esta parte: `print("Please use '-e', '-d', or '-h'.")
Probé la opción de -h y veo que me da la instrucción de como ejecutarlo, usando -d y nombre del archivo encriptado.
Lo ejecuto, ingreso la contraseña almacenada en el otro archivo txt y obtengo la bandera.
```bash
(kali㉿kali)-[~]
└─$ python ende.py -d flag.txt.en      
Please enter the password:aa821c16aa821c16aa821c16aa821c16
picoCTF{4p0110_1n_7h3_h0us3_aa821c16}
```

## Notas adicionales

- man Comando para el manual

## Referencias