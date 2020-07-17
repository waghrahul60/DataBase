# Assignment No-3


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Write a select command that produces the order number, amount, and date for all rows in the Orders table. 


```python
Ans : -> mysql> select onum,amt,odate from orders;

        +------+---------+------------+
        | onum | amt     | odate      |
        +------+---------+------------+
        | 3001 |   18.69 | 1990-10-03 |
        | 3003 |  767.19 | 1990-10-03 |
        | 3002 | 1900.10 | 1990-10-03 |
        | 3005 | 5160.45 | 1990-10-03 |
        | 3006 | 1098.16 | 1990-10-03 |
        | 3009 | 1713.23 | 1990-10-04 |
        | 3007 |   75.75 | 1990-10-04 |
        | 3008 | 4723.00 | 1990-10-05 |
        | 3010 | 1309.95 | 1990-10-06 |
        | 3011 | 9891.88 | 1990-10-06 |
        +------+---------+------------+
        10 rows in set (0.00 sec)
```


```python

```

## 2) Write a query that produces all rows from the Customers table for which the salesperson’s number is 1001. 


```python
ANS : -> mysql> select * from  customers where snum=1001;

        +------+---------+--------+--------+------+
        | Cnum | Cname   | City   | Rating | Snum |
        +------+---------+--------+--------+------+
        | 2001 | Hoffman | London |    100 | 1001 |
        | 2006 | Clemens | London |    100 | 1001 |
        +------+---------+--------+--------+------+
```


```python

```

## 3) Write a query that displays the Salespeople table with the columns in the following order: city, sname, snum, comm. 


```python
ANS : mysql> select city,sname,snum,comm from salespeople;
        +-----------+---------+------+------+
        | city      | sname   | snum | comm |
        +-----------+---------+------+------+
        | London    | Peel    | 1001 | 0.12 |
        | San Jose  | Serres  | 1002 | 0.13 |
        | London    | Motika  | 1004 | 0.11 |
        | Barcelona | Rifkin  | 1007 | 0.15 |
        | New York  | Axelord | 1003 | 0.10 |
        +-----------+---------+------+------+
        5 rows in set (0.00 sec)
```


```python

```

## 4) Write a select command that produces the rating followed by the name of each customer in San Jose. 


```python
 ANS : ->mysql> select rating,cname from customers where city = "San Jose";
        +--------+----------+
        | rating | cname    |
        +--------+----------+
        |    200 | Liu      |
        |    300 | Cisneros |
        +--------+----------+
        2 rows in set (0.00 sec)
```


```python

```

## 5) Write a query that will produce the snum values of all salespeople (suppress the duplicates) with orders in the Orders table.


```python
mysql> select distinct snum from orders;
        +------+
        | snum |
        +------+
        | 1007 |
        | 1001 |
        | 1004 |
        | 1002 |
        | 1003 |
        +------+
```
