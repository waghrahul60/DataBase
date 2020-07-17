Name:- Rahul Wagh    Id:- 200240520078  JUHU


```python
Q: Create the following tables with the given structures and insert sample data as specified: 
```


```python
mysql> create table SALESPEOPLE
    -> (Snum int(4),
    -> Sname varchar(10),
    -> City varchar(10),
    -> Comm float(3,2)
    -> );
```


```python
mysql> create table CUSTOMERS
    -> (
    -> Cnum int(4),
    -> Cname varchar(10),
    -> City varchar(10),
    -> Rating int(4),
    -> Snum int(4)
    -> );
```


```python
mysql> create table ORDERS
    -> (
    -> Onum int(4),
    -> Amt float(7,2),
    -> Odate date,
    -> Cnum int(4),
    -> Snum int(4)
    -> );
```


```python
mysql> insert into salespeople
    -> values(1001,'Peel','London',.12);


mysql> insert into salespeople
    -> values(1002,'Serres','San Jose',.13);


mysql> insert into salespeople
    -> values(1004,'Motika','London',.11);


mysql> insert into salespeople
    -> values(1007,'Rifkin','Barcelona',.15);


mysql> insert into salespeople
    -> values(1003,'Axelord','New York',.10);
```


```python
select * from salespeople;
+------+---------+-----------+------+
| Snum | Sname   | City      | Comm |
+------+---------+-----------+------+
| 1001 | Peel    | London    | 0.12 |
| 1002 | Serres  | San Jose  | 0.13 |
| 1004 | Motika  | London    | 0.11 |
| 1007 | Rifkin  | Barcelona | 0.15 |
| 1003 | Axelord | New York  | 0.10 |
```


```python
mysql> insert into customers
    -> values(2001,'Hoffman','London',100,1001);


mysql> insert into customers
    -> values(2002,'Giovanni','Rome',200,1003);


mysql> insert into customers
    -> values(2003,'Liu','San Jose',200,1002);


mysql> insert into customers
    -> values(2004,'Grass','Berlin',300,1002);


mysql> insert into customers
    -> values(2006,'Clemens','London',100,1001);


mysql> insert into customers
    -> values(2008,'Cisneros','San Jose',300,1007);


mysql> insert into customers
    -> values(2007,'Pereira','Rome',100,1004);
```


```python
mysql> select * from customers;
+------+----------+----------+--------+------+
| Cnum | Cname    | City     | Rating | Snum |
+------+----------+----------+--------+------+
| 2001 | Hoffman  | London   |    100 | 1001 |
| 2002 | Giovanni | Rome     |    200 | 1003 |
| 2003 | Liu      | San Jose |    200 | 1002 |
| 2004 | Grass    | Berlin   |    300 | 1002 |
| 2006 | Clemens  | London   |    100 | 1001 |
| 2008 | Cisneros | San Jose |    300 | 1007 |
| 2007 | Pereira  | Rome     |    100 | 1004 |
+------+----------+----------+--------+------+
```


```python
mysql> insert into orders
    -> values(3001,18.69,'1990-10-03',2008,1007);


mysql> insert into orders
    -> values(3003,767.19,'1990-10-03',2001,1001);


mysql> insert into orders
    -> values(3002,1900.10,'1990-10-03',2007,1004);


mysql> insert into orders
    -> values(3005,5160.45,'1990-10-03',2003,1002);


mysql> insert into orders
    -> values(3006,1098.16,'1990-10-03',2008,1007);


mysql> insert into orders
    -> values(3009,1713.23,'1990-10-04',2002,1003);


mysql> insert into orders
    -> values(3007,75.75,'1990-10-04',2004,1002);


mysql> insert into orders
    -> values(3008,4723.00,'1990-10-05',2006,1001);


mysql> insert into orders
    -> values(3010,1309.95,'1990-10-06',2004,1002);

mysql> insert into orders
    -> values(3011,9891.88,'1990-10-06',2006,1001);
```


```python

mysql> select * from orders;
+------+---------+------------+------+------+
| Onum | Amt     | Odate      | Cnum | Snum |
+------+---------+------------+------+------+
| 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
| 3003 |  767.19 | 1990-10-03 | 2001 | 1001 |
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3007 |   75.75 | 1990-10-04 | 2004 | 1002 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
```
