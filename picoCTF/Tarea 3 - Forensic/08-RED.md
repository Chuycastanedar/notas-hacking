
## Descripción

RED, RED, RED, REDDownload the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)


## Solución

Inicio descargando el archivo haciendo uso del comando wget.

Observo que se trata directamente de una imagen png, que al abrir solo muestra un color rojo.

Hago uso de la herramienta exiftool para buscar info y solamente observo un poema que habla sobre el color rojo aquí.

Entonces hago uso de la herramienta zsteg y logro encontrar el texto del poema, y una larga cadena de caracteres que identifico como base 64, y de acuerdo a la pista texto que se plasma en color rojo.

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ zsteg red.png      
meta Poem           .. text: "Crimson heart, vibrant and bold,\nHearts flutter at your sight.\nEvenings glow softly red,\nCherries burst with sweet life.\nKisses linger with your warmth.\nLove deep as merlot.\nScarlet leaves falling softly,\nBold in every stroke."                
b1,rgba,lsb,xy      .. text: "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="
```

Utilizo la herramienta cyberchef y obtengo la bandera decodificada:
`picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}`.

## Notas adicionales


## Referencias

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnR5TTJSZk1YTmZkR2d6WDNWc2RERnROSFF6WDJOMWNqTmZaakJ5WHpVMFpHNHpOVFZmZlE9PWNHbGpiME5VUm50eU0yUmZNWE5mZEdnelgzVnNkREZ0TkhRelgyTjFjak5mWmpCeVh6VTBaRzR6TlRWZmZRPT1jR2xqYjBOVVJudHlNMlJmTVhOZmRHZ3pYM1ZzZERGdE5IUXpYMk4xY2pOZlpqQnlYelUwWkc0ek5UVmZmUT09Y0dsamIwTlVSbnR5TTJSZk1YTmZkR2d6WDNWc2RERnROSFF6WDJOMWNqTmZaakJ5WHpVMFpHNHpOVFZmZlE9PQ