# AssignmentNo19


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Create a view that shows all of the customers who have the highest ratings


```python
->  mysql> create view max_rat_cust as select * from customers where rating=(select max(rating) from customers);
    Query OK, 0 rows affected (0.54 sec)

    mysql> select * from max_rat_cust;
    +------+----------+----------+--------+------+
    | Cnum | Cname    | City     | Rating | Snum |
    +------+----------+----------+--------+------+
    | 2004 | Grass    | Berlin   |    300 | 1002 |
    | 2008 | Cisneros | San Jose |    300 | 1007 |
    +------+----------+----------+--------+------+
    2 rows in set (0.04 sec)

```

## 2) Create a view that shows the number of salespeople in each city.


```python
-> mysql> create view count_city as select city,count(city) from salespeople group by city;
    Query OK, 0 rows affected (0.36 sec)

    mysql> select * from count_city;
    +-----------+-------------+
    | city      | count(city) |
    +-----------+-------------+
    | London    |           2 |
    | San Jose  |           2 |
    | Barcelona |           1 |
    | New York  |           1 |
    +-----------+-------------+
```

## 3) Create  a  view  that  shows  the  average  and  total  orders  for  each  salesperson  after his or her name. Assume all names are unique


```python
-> mysql> create view  avg_count as select sname,avg(onum),count(onum) from orders,salespeople where orders.snum=salespeople.snum group by sname;
    Query OK, 0 rows affected (0.31 sec)

    mysql> select * from avg_count;
    +---------+-----------+-------------+
    | sname   | avg(onum) | count(onum) |
    +---------+-----------+-------------+
    | Rifkin  | 3003.5000 |           2 |
    | Peel    | 3003.0000 |           1 |
    | Motika  | 3002.0000 |           1 |
    | Serres  | 3007.3333 |           3 |
    | Axelord | 3009.0000 |           1 |
    +---------+-----------+-------------+
```

## 4) Create a view that shows each salesperson with multiple customers.



```python
-> mysql> CREATE VIEW m_c AS
        -> SELECT sname,
        ->        cname
        -> FROM salespeople
        -> JOIN customers USING (snum);
        Query OK, 0 rows affected (0.27 sec)

        mysql> select * from m_c;
        +---------+-----------+
        | sname   | cname     |
        +---------+-----------+
        | Peel    | Hoffman   |
        | Axelord | Giovanni  |
        | Serres  | Liu       |
        | Serres  | Grass     |
        | Peel    | Clemens   |
        | Rifkin  | Cisneros  |
        | Serres  | Pereira   |
        | Rifkin  |    kmb    |
        +---------+-----------+
```
