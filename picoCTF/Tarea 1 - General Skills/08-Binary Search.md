
## Descripción

Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here: challenge.zip

`ssh -p 58838 ctf-player@atlas.picoctf.net`Using the password `1db87a14`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

## Solución

Iniciamos accediendo por ssh al servidor con los datos que se nos proporcionan.
En cuanto ingresamos nuestra contraseña se inicia el juego de búsqueda binaria, donde deberemos ingresar un número del 1 al 1000 y tendremos 10 intentos consecutivos para adivinar el número.
Si logramos adivinarlo antes de los 10 ganamos y nos otorga la llave!.
```bash
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Higher! Try again.
Enter your guess: 750
Lower! Try again.
Enter your guess: 625
Lower! Try again.
Enter your guess: 570
Lower! Try again.
Enter your guess: 535
Higher! Try again.
Enter your guess: 553
Lower! Try again.
Enter your guess: 545
Higher! Try again.
Enter your guess: 549
Higher! Try again.
Enter your guess: 551
Congratulations! You guessed the correct number: 551
Here's your flag: picoCTF{g00d_gu355_1597707f}
```

## Notas adicionales

- Have you ever played hot or cold? Binary search is a bit like that.

## Referencias
