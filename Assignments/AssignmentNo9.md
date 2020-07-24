# AssignmentNo9


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Write a query that lists each order number followed by the name of the customer who made the order. 


```python
SELECT orders.onum, customers.cname 
FROM customers, orders
WHERE orders.cnum = customers.cnum
ORDER BY 1;

        +------+----------+
        | onum | cname    |
        +------+----------+
        | 3001 | Cisneros |
        | 3002 | Pereira  |
        | 3003 | Hoffman  |
        | 3005 | Liu      |
        | 3006 | Cisneros |
        | 3007 | Grass    |
        | 3008 | Clemens  |
        | 3008 | Clemens  |
        | 3009 | Giovanni |
        | 3010 | Grass    |
        | 3011 | Clemens  |
        | 3011 | Clemens  |
        +------+----------+
        12 rows in set (0.00 sec)
```

## 2) Write a query that gives the names of both the salesperson and the customer for each order along with the order number. 


```python
SELECT salespeople.sname, customers.cname, orders.onum
FROM orders, customers, salespeople
WHERE orders.snum = salespeople.snum AND orders.cnum = customers.cnum;

        +---------+----------+------+
        | sname   | cname    | onum |
        +---------+----------+------+
        | Peel    | Hoffman  | 3003 |
        | Axelord | Giovanni | 3009 |
        | Serres  | Liu      | 3005 |
        | Serres  | Grass    | 3007 |
        | Serres  | Grass    | 3010 |
        | Peel    | Clemens  | 3008 |
        | Peel    | Clemens  | 3011 |
        | Peel    | Clemens  | 3008 |
        | Peel    | Clemens  | 3011 |
        | Rifkin  | Cisneros | 3001 |
        | Rifkin  | Cisneros | 3006 |
        | Motika  | Pereira  | 3002 |
        +---------+----------+------+
        12 rows in set (0.00 sec)
```

## 3) Write a query that produces all customers serviced by salespeople with a commission above 12%. Output the customer’s name, the salesperson’s name, and the salesperson’s rate of commission. 


```python
SELECT cname,sname,comm*100 as "comm rate"  
FROM customers,salespeople
WHERE customers.snum = salespeople.snum AND comm > .12;

        +----------+--------+-----------+
        | cname    | sname  | comm rate |
        +----------+--------+-----------+
        | Liu      | Serres |     13.00 |
        | Grass    | Serres |     13.00 |
        | Cisneros | Rifkin |     15.00 |
        +----------+--------+-----------+
        3 rows in set (0.00 sec)

```

## 4) Write a query that calculates the amount of the salesperson’s commission on each order by a customer with a rating above 100. 


```python
SELECT amt, comm
FROM salespeople JOIN customers using (snum) JOIN orders using(snum)
WHERE rating > 100;
    
        +---------+------+
        | amt     | comm |
        +---------+------+
        |   18.69 | 0.15 |
        | 5160.45 | 0.13 |
        | 5160.45 | 0.13 |
        | 1098.16 | 0.15 |
        | 1713.23 | 0.10 |
        |   75.75 | 0.13 |
        |   75.75 | 0.13 |
        | 1309.95 | 0.13 |
        | 1309.95 | 0.13 |
        +---------+------+
        9 rows in set (0.00 sec)
```
