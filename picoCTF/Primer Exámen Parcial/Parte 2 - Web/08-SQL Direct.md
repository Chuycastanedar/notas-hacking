## Descripción

Connect to this PostgreSQL server and find the flag! `psql -h saturn.picoctf.net -p 64492 -U postgres pico` Password is `postgres`

## Solución

Mostramos las tablas que tiene la base de datos con `\dt` y podríamos haber buscado mas detalles con el `\dt+`,  pero al hacer un `SELECT` del contenido de la tabla aparece la bandera.

```sql

┌──(kali㉿kali)-[~/pico]

└─$ psql -h saturn.picoctf.net -p 64492 -U postgres pico

Password for user postgres:

psql (17.6 (Debian 17.6-1), server 15.2 (Debian 15.2-1.pgdg110+1))

Type "help" for help.

  

pico=# \dt

         List of relations

 Schema | Name  | Type  |  Owner  

--------+-------+-------+----------

 public | flags | table | postgres

(1 row)

  

pico=# \dt+

                                   List of relations

 Schema | Name  | Type  |  Owner   | Persistence | Access method | Size  | Description

--------+-------+-------+----------+-------------+---------------+-------+-------------

 public | flags | table | postgres | permanent   | heap          | 16 kB |

(1 row)

  

pico=# SELECT * FROM flags;

 id | firstname | lastname  |                address                

----+-----------+-----------+----------------------------------------

  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}

  2 | Leia      | Organa    | Alderaan

  3 | Han       | Solo      | Corellia

(3 rows)

  

pico=#

```

## Notas

`\dt` muestra las tablas

`\d` muestra los detalles de una tabla especifica

## Referencias

[postgresql-show-tables?_][https://neon-com.translate.goog/postgresql/postgresql-administration/postgresql-show-tables?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es&_x_tr_pto=tc&_x_tr_hist=true]