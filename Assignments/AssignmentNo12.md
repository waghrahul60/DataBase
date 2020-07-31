# AssignmentNo12


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Write a query that selects all customers whose ratings are equal to or greater than ANY of Serres’.


```python
mysql> select * from customers where rating >=any(select rating from customers where snum in(select snum from salespeople where sname='serres'));
+------+----------+----------+--------+------+
| Cnum | Cname    | City     | Rating | Snum |
+------+----------+----------+--------+------+
| 2002 | Giovanni | Rome     |    200 | 1003 |
| 2003 | Liu      | San Jose |    200 | 1002 |
| 2004 | Grass    | Berlin   |    300 | 1002 |
| 2008 | Cisneros | San Jose |    300 | 1007 |
+------+----------+----------+--------+------+
```

## 3) Write a query that selects all orders for amounts greater than any for the customers in London.


```python
    -> mysql> SELECT *
    -> FROM orders
    -> WHERE amt> ANY
    ->     ( SELECT amt
    ->      FROM orders
    ->      WHERE cnum IN
    ->          ( SELECT cnum
    ->           FROM customers
    ->           WHERE city='london' ) );
+------+---------+------------+------+------+
| Onum | Amt     | Odate      | Cnum | Snum |
+------+---------+------------+------+------+
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
```

## 4) Write the above query using MIN or MAX.


```python
    -> mysql> SELECT *
    -> FROM orders
    -> WHERE amt>
    ->     (SELECT min(amt)
    ->      FROM customers
    ->      NATURAL JOIN orders
    ->      WHERE city='london');
+------+---------+------------+------+------+
| Onum | Amt     | Odate      | Cnum | Snum |
+------+---------+------------+------+------+
| 3002 | 1900.10 | 1990-10-03 | 2007 | 1004 |
| 3005 | 5160.45 | 1990-10-03 | 2003 | 1002 |
| 3006 | 1098.16 | 1990-10-03 | 2008 | 1007 |
| 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
| 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
| 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
| 3011 | 9891.88 | 1990-10-06 | 2006 | 1001 |
+------+---------+------------+------+------+
```
