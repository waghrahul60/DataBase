# AssignmentNo8


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Assume each salesperson has a 12% commission. Write a query on the orders table that will produce the order number, the salesperson number, and the amount of the salesperson’s commission for that order. 


```python
SELECT onum,snum,amt,(amt*12)/100 as commission
FROM orders;

        +------+------+---------+-------------+
        | onum | snum | amt     | commission  |
        +------+------+---------+-------------+
        | 3001 | 1007 |   18.69 |    2.242800 |
        | 3003 | 1001 |  767.19 |   92.062800 |
        | 3002 | 1004 | 1900.10 |  228.011997 |
        | 3005 | 1002 | 5160.45 |  619.254023 |
        | 3006 | 1007 | 1098.16 |  131.779204 |
        | 3009 | 1003 | 1713.23 |  205.587598 |
        | 3007 | 1002 |   75.75 |    9.090000 |
        | 3008 | 1001 | 4723.00 |  566.760000 |
        | 3010 | 1002 | 1309.95 |  157.193994 |
        | 3011 | 1001 | 9891.88 | 1187.025586 |
        +------+------+---------+-------------+
        10 rows in set (0.00 sec)
```

## 2) Write a query on the Customers table that will find the highest rating in each city. Put the output in this form: 
 
            For the city (city), the highest rating is : (rating). 


```python
SELECT city, max(rating) as rating 
FROM customers 
GROUP BY city;

            +----------+--------+
            | city     | rating |
            +----------+--------+
            | Berlin   |    300 |
            | London   |    100 |
            | Rome     |    200 |
            | San Jose |    300 |
            +----------+--------+
            4 rows in set (0.00 sec)
```

##  3) Write a query that lists customers in descending order of rating. Output the rating field first, followed by the customer’s name and number. 


```python
SELECT rating, cname, cnum 
FROM customers
ORDER BY rating desc;

        +--------+----------+------+
        | rating | cname    | cnum |
        +--------+----------+------+
        |    300 | Grass    | 2004 |
        |    300 | Cisneros | 2008 |
        |    200 | Giovanni | 2002 |
        |    200 | Liu      | 2003 |
        |    100 | Hoffman  | 2001 |
        |    100 | Clemens  | 2006 |
        |    100 | Clemens  | 2006 |
        |    100 | Pereira  | 2007 |
        +--------+----------+------+
        8 rows in set (0.00 sec)
```

## 4) Write a query that totals the orders for each day and places the results in descending order.


```python
SELECT count(odate) from orders
GROUP BY odate
ORDER BY count(odate);

        +--------------+
        | count(odate) |
        +--------------+
        |            1 |
        |            2 |
        |            2 |
        |            5 |
        +--------------+
        4 rows in set (0.00 sec)
```
