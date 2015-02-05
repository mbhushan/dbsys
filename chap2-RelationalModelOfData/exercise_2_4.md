a) What PC models have a speed of at least 3.00?
mysql> select * from PC where speed >= 3.0;
+-------+-------+------+------+-------+
| model | speed | ram  | hd   | price |
+-------+-------+------+------+-------+
| 1005  |   3.2 |  512 |  250 |   630 |
| 1006  |   3.2 | 1024 |  320 |  1049 |
| 1013  |  3.06 |  512 |   80 |   529 |
+-------+-------+------+------+-------+

b) Which manufacturers make laptops with a hard disk of at least 100GB?
c) Find the model number and price of all products (of any type) made by
manufacturer B.
d) Find the model numbers of all color laser printers.
e) Find those manufacturers that sell Laptops, but not P C ’s.
! f) Find those hard-disk sizes that occur in two or more PC ’s.
