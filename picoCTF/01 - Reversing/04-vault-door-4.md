
## Descripción

This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://challenge-files.picoctf.net/c_fickle_tempest/5c887bc56d0c788895c28b80d7b702aff7b889fc7d8edf83fe0dc25c8aa11756/VaultDoor4.java)

## Solución

Inicio descargando el archivo que me dan usando el comando wget.

Veo que se trata de un archivo .java, por lo que lo abro utilizando el editor nano. Analizo un poco el código y me doy cuenta de que el programa pide una contraseña que realmente es la misma bandera, y valida si tiene `picoCTF{}` para quitarlo de la cadena.

A partir de aquí, existe un método checkPassword que recibe el contenido y lo convierte a bytes y lo manda a un arreglo llamado passBytes. Luego se define un arreglo constante que se llama myBytes con una serie de bytes que se usará para comparar caracter a caracter con mi password mediante un ciclo siguiente.
Si alguno es diferente se sale y si todos son iguales la validación es correcta.

Para esto usaremos las herramientas de desarrollador de firefox . Usamos la función fromCharCode para convertir todos: 
```
String.fromCharCode(
106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
0142, 0131, 0164, 063 , 0163, 0137, 0145, 060)
```

A partir de aquí solo le sumamos un arreglo con los últimos caracteres que no tenemos que convertir y usamos un join para unirlos.

```
String.fromCharCode(
106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
0142, 0131, 0164, 063 , 0163, 0137, 0145, 060) + ['2' , '1' , '3' , '8' , '7' , '2' , '1' , '3' ].join('')
```

Obtenemos la bandera:
`picoCTF{jU5t_4_bUnCh_0f_bYt3s_e021387213}`

## Notas adicionales


## Referencias