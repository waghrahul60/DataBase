# AssignmentNo7


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Write a query that counts all orders for October 3. 


```python
mysql> select count(onum) from orders where odate = '1990-10-03';
        +-------------+
        | count(onum) |
        +-------------+
        |           5 |
        +-------------+
        1 row in set (0.00 sec)
```

## 2) Write a query that counts the number of different non-NULL city values in the Customers table. 


```python
mysql> select count(distinct(city)) from customers where city is not null;
        +-----------------------+
        | count(distinct(city)) |
        +-----------------------+
        |                     4 |
        +-----------------------+
        1 row in set (0.02 sec)
```

## 3) Write a query that selects each customer’s smallest order. 


```python
mysql> select min(amt),cnum from orders group by cnum;
        +----------+------+
        | min(amt) | cnum |
        +----------+------+
        |   767.19 | 2001 |
        |  1713.23 | 2002 |
        |  5160.45 | 2003 |
        |    75.75 | 2004 |
        |  4723.00 | 2006 |
        |  1900.10 | 2007 |
        |    18.69 | 2008 |
        +----------+------+
        7 rows in set (0.01 sec)
```

## 4) Write a query that selects the first customer, in alphabetical order, whose name begins with G


```python
mysql> select cname from customers where cname like 'G%' order by cname limit 1;
        +----------+
        | cname    |
        +----------+
        | Giovanni |
        +----------+
        1 row in set (0.01 sec)
```

## 5) Write a query that selects the highest rating in each city.


```python
mysql> select city, max(rating) from customers group by city;
        +----------+-------------+
        | city     | max(rating) |
        +----------+-------------+
        | Berlin   |         300 |
        | London   |         100 |
        | Rome     |         200 |
        | San Jose |         300 |
        +----------+-------------+
        4 rows in set (0.00 sec)
```

## 6) Write a query that counts the number of salespeople registering orders for each day. (If a salesperson has more than one order on a given day, he or she should be counted only once.). 


```python
mysql> SELECT count(distinct(odate)), odate FROM orders GROUP BY odate;
        +------------------------+------------+
        | count(distinct(odate)) | odate      |
        +------------------------+------------+
        |                      1 | 1990-10-03 |
        |                      1 | 1990-10-04 |
        |                      1 | 1990-10-05 |
        |                      1 | 1990-10-06 |
        +------------------------+------------+
        4 rows in set (0.01 sec)
```
