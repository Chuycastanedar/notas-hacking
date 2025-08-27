## Descripción
If l told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Solución

Convertir el número en hexadecimal a su representación en código ASCII
### Forma 1 
- Usar una página web hex to ascii
- Usar una herramienta web como ciberhef

### Forma 2
Puede usarse incluso el interprete de python para convertir de hex a ascii

```bash
JCR_07-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x70)
112
>>> chr(112)
'p'
```

```
picoCTF{p}
```

## Notas adicionales 
- Siempre hay que poner la solución en el formato de la bandera
## Referencias
https://www.rapidtables.com/convert/number/hex-to-ascii.html
https://gchg.github.io/CiberChef/