# SQL Direct

## Descripción
Connect to this PostgreSQL server and find the flag!

Additional details will be available after launching your challenge instance.

## Pistas
What does a SQL database contain?

## Solución
pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

## Bandera

picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}

## Notas adicionales



## Referencias