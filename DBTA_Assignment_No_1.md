Name:- Rahul Wagh    Id:- 200240520078  JUHU


```python
Q: Create the following tables with the given structures and insert sample data as specified: 
```

mysql> create table SALESPEOPLE
    -> (Snum int(4),
    -> Sname varchar(10),
    -> City varchar(10),
    -> Comm float(3,2)
    -> );

mysql> create table CUSTOMERS
    -> (
    -> Cnum int(4),
    -> Cname varchar(10),
    -> City varchar(10),
    -> Rating int(4),
    -> Snum int(4)
    -> );

mysql> create table ORDERS
    -> (
    -> Onum int(4),
    -> Amt float(7,2),
    -> Odate date,
    -> Cnum int(4),
    -> Snum int(4)
    -> );

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

select * from salespeople;
+------+---------+-----------+------+
| Snum | Sname   | City      | Comm |
+------+---------+-----------+------+
| 1001 | Peel    | London    | 0.12 |
| 1002 | Serres  | San Jose  | 0.13 |
| 1004 | Motika  | London    | 0.11 |
| 1007 | Rifkin  | Barcelona | 0.15 |
| 1003 | Axelord | New York  | 0.10 |
