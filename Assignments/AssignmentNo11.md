# AssignmentNo11


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Write a query that uses a subquery to obtain all orders for the customer named Cisneros. Assume you do not know his customer number (cnum). 


```python
SELECT cnum, onum 
FROM orders
WHERE  cnum =
(SELECT cnum FROM customers WHERE cname = 'cisneros');

        +------+------+
        | cnum | onum |
        +------+------+
        | 2008 | 3001 |
        | 2008 | 3006 |
        +------+------+
        2 rows in set (0.00 sec)
```

## 2) Write a query that produces the names and ratings of all customers who have above-average orders. 


```python
SELECT cname, rating 
FROM customers
WHERE cnum in 
(SELECT cnum from orders where amt > (SELECT avg(amt) from orders));

        +---------+--------+
        | cname   | rating |
        +---------+--------+
        | Liu     |    200 |
        | Clemens |    100 |
        | Clemens |    100 |
        +---------+--------+
        3 rows in set (0.00 sec)

```

## 3) Write a query that selects the total amount in orders for each salesperson for whom this total is greater than the amount of the largest order in the table


```python
SELECT sum(amt) as TOTALAMT
FROM orders
Group by snum
HAVING sum(amt) > (Select max(amt) from orders);

        +----------+
        | TOTALAMT |
        +----------+
        | 15382.07 |
        +----------+
        1 row in set (0.00 sec)
```
