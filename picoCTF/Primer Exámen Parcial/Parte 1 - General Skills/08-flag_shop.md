## Descripción

There's a flag shop selling stuff, can you buy a flag? [Source](https://jupiter.challenges.picoctf.org/static/64e724ad327f83ad833d9c6baa072b1f/store.c). Connect with `nc jupiter.challenges.picoctf.org 4906`.

## Solución

Parece ser que hay un error en el código que maneja las banderas imitación, este actualiza el `account_balance` pues directamente  le resta el `total_cost`.

```c

int auction_choice;

fflush(stdin);

scanf("%d", &auction_choice);

if(auction_choice == 1){

    printf("These knockoff Flags cost 900 each, enter desired quantity\n");

    int number_flags = 0;

    fflush(stdin);

    scanf("%d", &number_flags);

    if(number_flags > 0){

        int total_cost = 0;

        total_cost = 900*number_flags;

        printf("\nThe final cost is: %d\n", total_cost);

        if(total_cost <= account_balance){

            account_balance = account_balance - total_cost;

            printf("\nYour current balance after transaction: %d\n\n", account_balance);

        }

        else{

            printf("Not enough funds to complete purchase\n");

        }

    }

}

```

un entero en `C` solo maneja hasta un valor de `2,147,483,647`, entonces lo desbordamos al multiplicar con 900 un valor lo suficiente grande, que hace que el bit que identifica el signo se active y se vuelva negativo.

Cuando llega a la resta, resta con un valor negativo por lo que termina sumando ese valor `account_balance = account_balance - total_cost;`

```bash

Welcome to the flag exchange

We sell flags

  

1. Check Account Balance

2. Buy Flags

3. Exit

  

 Enter a menu selection

2

Currently for sale

1. Defintely not the flag Flag

2. 1337 Flag

1

These knockoff Flags cost 900 each, enter desired quantity

2386099

  

The final cost is: -2147478196

  

Your current balance after trans2386099action: 2147479296

  

Welcome to the flag exchange

We sell flags

  

1. Check Account Balance

2. Buy Flags

3. Exit

  

 Enter a menu selection

2

Currently for sale

1. Defintely not the flag Flag

2. 1337 Flag

2

1337 flags cost 100000 dollars, and we only have 1 in stock

Enter 1 to buy one1

YOUR FLAG IS: picoCTF{m0n3y_bag5_9c5fac9b}

```

## Notas

  

## Referencias