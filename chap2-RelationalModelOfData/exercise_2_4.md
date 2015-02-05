a) What PC models have a speed of at least 3.00?
``` sql
mysql> select * from PC where speed >= 3.0;
+-------+-------+------+------+-------+
| model | speed | ram  | hd   | price |
+-------+-------+------+------+-------+
| 1005  |   3.2 |  512 |  250 |   630 |
| 1006  |   3.2 | 1024 |  320 |  1049 |
| 1013  |  3.06 |  512 |   80 |   529 |
+-------+-------+------+------+-------+
```

b) Which manufacturers make laptops with a hard disk of at least 100GB?
``` sql
mysql> select maker, model from product where model in (select model from laptop where hd >= 100);
+-------+-------+
| maker | model |
+-------+-------+
| A     | 2005  |
| B     | 2007  |
| E     | 2001  |
| F     | 2008  |
| G     | 2010  |
+-------+-------+
5 rows in set (0.04 sec)
```

c) Find the model number and price of all products (of any type) made by manufacturer B.
```sql
mysql> (select  model, price from PC where model in (select model from product where maker='B')) union (select  model, price from laptop where model in (select model from product where maker='B')) union (select  model, price from printer where model in (select model from product where maker='B'))
    -> ;
    +-------+-------+
    | model | price |
    +-------+-------+
    | 1004  |   649 |
    | 1005  |   630 |
    | 1006  |  1049 |
    | 2007  |  1429 |
    +-------+-------+
    4 rows in set (0.04 sec)
```

d) Find the model numbers of all color laser printers.

e) Find those manufacturers that sell Laptops, but not P C ’s.

! f) Find those hard-disk sizes that occur in two or more PC ’s.
