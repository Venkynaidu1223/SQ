create table bank(
    -> a_holdername char(17),
    -> a_no int,
    -> a_adress varchar(17),
    -> a_phno int,
    -> a_pricing int);
Query OK, 0 rows affected (0.04 sec)

mysql> insert into bank values('venky',1234,'guntur',450);
ERROR 1136 (21S01): Column count doesn't match value count at row 1
mysql> insert into bank values('venky',1234,'guntur',7013419027,450);
ERROR 1264 (22003): Out of range value for column 'a_phno' at row 1
mysql> insert into bank values('venky',1234,'guntur',7013,450);
Query OK, 1 row affected (0.00 sec)

mysql> insert into bank values('sai',1235,'ongole',9013,299);
Query OK, 1 row affected (0.01 sec)

mysql> insert into bank values('jaswanth',1237,'kurnool',9913,256);
Query OK, 1 row affected (0.01 sec)

mysql> insert into bank values('abhi',1239,'vizag',9989,178);
Query OK, 1 row affected (0.01 sec)

mysql> insert into bank values('vikram',1275,'hyd',7689,234);
Query OK, 1 row affected (0.01 sec)

mysql> insert into bank values('viswanth',1375,'chennai',7999,294);
Query OK, 1 row affected (0.01 sec)

mysql> insert into bank values('aravind',1387,'kakinda',9999,890);
Query OK, 1 row affected (0.01 sec)

mysql> select*from bank;
+--------------+------+----------+--------+-----------+
| a_holdername | a_no | a_adress | a_phno | a_pricing |
+--------------+------+----------+--------+-----------+
| venky        | 1234 | guntur   |   7013 |       450 |
| sai          | 1235 | ongole   |   9013 |       299 |
| jaswanth     | 1237 | kurnool  |   9913 |       256 |
| abhi         | 1239 | vizag    |   9989 |       178 |
| vikram       | 1275 | hyd      |   7689 |       234 |
| viswanth     | 1375 | chennai  |   7999 |       294 |
| aravind      | 1387 | kakinda  |   9999 |       890 |
+--------------+------+----------+--------+-----------+
7 rows in set (0.00 sec)

mysql> select*from bank where 220<a_pricing<300;
+--------------+------+----------+--------+-----------+
| a_holdername | a_no | a_adress | a_phno | a_pricing |
+--------------+------+----------+--------+-----------+
| venky        | 1234 | guntur   |   7013 |       450 |
| sai          | 1235 | ongole   |   9013 |       299 |
| jaswanth     | 1237 | kurnool  |   9913 |       256 |
| abhi         | 1239 | vizag    |   9989 |       178 |
| vikram       | 1275 | hyd      |   7689 |       234 |
| viswanth     | 1375 | chennai  |   7999 |       294 |
| aravind      | 1387 | kakinda  |   9999 |       890 |
+--------------+------+----------+--------+-----------+
7 rows in set (0.00 sec)

mysql> select*from bank where 220<a_pricing>300;
Empty set (0.00 sec)

mysql> select*from bank where a_pricing BETWEEN 220 and 300;
+--------------+------+----------+--------+-----------+
| a_holdername | a_no | a_adress | a_phno | a_pricing |
+--------------+------+----------+--------+-----------+
| sai          | 1235 | ongole   |   9013 |       299 |
| jaswanth     | 1237 | kurnool  |   9913 |       256 |
| vikram       | 1275 | hyd      |   7689 |       234 |
| viswanth     | 1375 | chennai  |   7999 |       294 |
+--------------+------+----------+--------+-----------+
4 rows in set (0.00 sec)

create table dhoni(
    -> pid int,
    -> product char(12),
    -> month char(11),
    -> nrecords int,
    -> purchase_price int,
    -> saleprice int);
Query OK, 0 rows affected (0.03 sec)

mysql> insert into dhoni values(1,'pen','jan',7,10);
ERROR 1136 (21S01): Column count doesn't match value count at row 1
mysql> insert into dhoni values(1,'pen','jan',156,7,10);
Query OK, 1 row affected (0.00 sec)

mysql> insert into dhoni values(2,'toys','jan',56,240,300);
Query OK, 1 row affected (0.00 sec)

mysql> insert into dhoni values(3,'bats','jan',20,560,900);
Query OK, 1 row affected (0.00 sec)

mysql> insert into dhoni values(4,'balls','feb',90,70,75);
Query OK, 1 row affected (0.01 sec)

mysql> insert into dhoni values(5,'jersy','feb',45,900,850);
Query OK, 1 row affected (0.01 sec)

mysql> insert into dhoni values(6,'caps','feb',65,100,85);
Query OK, 1 row affected (0.01 sec)

mysql> insert into dhoni values(7,'wickets','feb',20,200,175);
Query OK, 1 row affected (0.01 sec)

mysql> select*from dhoni;
+------+---------+-------+----------+----------------+-----------+
| pid  | product | month | nrecords | purchase_price | saleprice |
+------+---------+-------+----------+----------------+-----------+
|    1 | pen     | jan   |      156 |              7 |        10 |
|    2 | toys    | jan   |       56 |            240 |       300 |
|    3 | bats    | jan   |       20 |            560 |       900 |
|    4 | balls   | feb   |       90 |             70 |        75 |
|    5 | jersy   | feb   |       45 |            900 |       850 |
|    6 | caps    | feb   |       65 |            100 |        85 |
|    7 | wickets | feb   |       20 |            200 |       175 |
+------+---------+-------+----------+----------------+-----------+
7 rows in set (0.00 sec)

mysql> select product,month,nrecords from dhoni where purchase_price>saleprice;
+---------+-------+----------+
| product | month | nrecords |
+---------+-------+----------+
| jersy   | feb   |       45 |
| caps    | feb   |       65 |
| wickets | feb   |       20 |
+---------+-------+----------+
3 rows in set (0.00 sec)
mysql> create database pawan;
Query OK, 1 row affected (0.01 sec)

mysql> use pawan;
Database changed
mysql> create table venky(
    -> pid int,
    -> product char(17),
    -> price int,
    -> 3mtotal int);
Query OK, 0 rows affected (0.04 sec)

mysql> insert into venky values(1,'lunchbox',230,2);
Query OK, 1 row affected (0.01 sec)

mysql> insert into venky values(2,'matchbox',2,67);
Query OK, 1 row affected (0.01 sec)

mysql> insert into venky values(3,'notebook',35,5);
Query OK, 1 row affected (0.01 sec)

mysql> insert into venky values(4,'pens',10,56);
Query OK, 1 row affected (0.01 sec)

mysql> select*from venky;
+------+----------+-------+---------+
| pid  | product  | price | 3mtotal |
+------+----------+-------+---------+
|    1 | lunchbox |   230 |       2 |
|    2 | matchbox |     2 |      67 |
|    3 | notebook |    35 |       5 |
|    4 | pens     |    10 |      56 |
+------+----------+-------+---------+
4 rows in set (0.00 sec)

mysql> insert into venky values(5,'cakes',690,3);
Query OK, 1 row affected (0.01 sec)

mysql> insert into venky values(6,'bags',560,4);
Query OK, 1 row affected (0.01 sec)

mysql> insert into venky values(7,'pads',56,2);
Query OK, 1 row affected (0.01 sec)

mysql> select*from venky;
+------+----------+-------+---------+
| pid  | product  | price | 3mtotal |
+------+----------+-------+---------+
|    1 | lunchbox |   230 |       2 |
|    2 | matchbox |     2 |      67 |
|    3 | notebook |    35 |       5 |
|    4 | pens     |    10 |      56 |
|    5 | cakes    |   690 |       3 |
|    6 | bags     |   560 |       4 |
|    7 | pads     |    56 |       2 |
+------+----------+-------+---------+
7 rows in set (0.00 sec)

create table money(
    -> a_holdername char(17),
    -> a_no int,
    -> pm_trans int,
    -> cm_trans int,
    -> a_phno int);
Query OK, 0 rows affected (0.03 sec)

mysql> insert into money values('venky',1234,2300,13000,7013);
Query OK, 1 row affected (0.01 sec)

mysql> insert into money values('charan',2345,23000,13000,7189);
Query OK, 1 row affected (0.01 sec)

mysql> insert into money values('pawan',3456,77000,121000,7873);
Query OK, 1 row affected (0.01 sec)

mysql> insert into money values('chiru',4565,77890,56000,6037);
Query OK, 1 row affected (0.01 sec)

mysql> insert into money values('varun',2365,73420,99000,6877);
Query OK, 1 row affected (0.01 sec)

mysql> insert into money values('vaishnav',8736,56790,567900,2341);
Query OK, 1 row affected (0.01 sec)

mysql> select*from money ;
+--------------+------+----------+----------+--------+
| a_holdername | a_no | pm_trans | cm_trans | a_phno |
+--------------+------+----------+----------+--------+
| venky        | 1234 |     2300 |    13000 |   7013 |
| charan       | 2345 |    23000 |    13000 |   7189 |
| pawan        | 3456 |    77000 |   121000 |   7873 |
| chiru        | 4565 |    77890 |    56000 |   6037 |
| varun        | 2365 |    73420 |    99000 |   6877 |
| vaishnav     | 8736 |    56790 |   567900 |   2341 |
+--------------+------+----------+----------+--------+
6 rows in set (0.00 sec)

mysql> select*from money where cm_trans>pm_trans;
+--------------+------+----------+----------+--------+
| a_holdername | a_no | pm_trans | cm_trans | a_phno |
+--------------+------+----------+----------+--------+
| venky        | 1234 |     2300 |    13000 |   7013 |
| pawan        | 3456 |    77000 |   121000 |   7873 |
| varun        | 2365 |    73420 |    99000 |   6877 |
| vaishnav     | 8736 |    56790 |   567900 |   2341 |
+--------------+------+----------+----------+--------+
4 rows in set (0.00 sec)

mysql>
