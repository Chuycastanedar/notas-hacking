
## Descripción

Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/eb5e6df8e14c52873cf88c582a1a4008/ciphertext)? Something seems a bit small.

## Solución

Inicio descargando el archivo que se nos da en un directorio haciendo uso del comando wget.

Después de analizar el reto. Me aseguro de tener instaladas las herramientas gmpy2 y pycryptodome.

Hago un cat al archivo para ver su contenido.
Haciendo uso de python3, importo gmpy2 y Cryptodome:
```bash
>>> from gmpy2 import *
>>> from Cryptodome.Util.number import long_to_bytes
```

Establecemos la presición, e y c:
```bash
>>> gmpy2.get_context().precision=2048
>>> 
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872650080519263755075355825243\
327515211479747536697517688468095325517209911688684309894900992899707504087647575997847717\
180766377832435022794675332132906451858990782325436498952049751141
```

Obtenemos el texto plano:
```bash
>>> root, exact = iroot(c, e)
>>> root
mpz(13016382529449106065894479374027604750406953699090365388203722801043052339225981)
```

Imprimimos el texto plano bytes, obtenemos la bandera:
```bash
>>> print(long_to_bytes(root))
b'picoCTF{n33d_a_lArg3r_e_d0cd6eae}'
```


## Notas adicionales


## Referencias
