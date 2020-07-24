# AssignmentNo10


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Write a query that produces all pairs of salespeople who are living in the same city.  Exclude combinations of salespeople with themselves as well as duplicate rows with the order reversed. 


```python
SELECT a.sname,b.sname,a.city 
FROM salespeople a, salespeople b
WHERE a.city = b.city AND a.sname < b.sname;

        +--------+-------+--------+
        | sname  | sname | city   |
        +--------+-------+--------+
        | Motika | Peel  | London |
        +--------+-------+--------+
        1 row in set (0.00 sec)
```

## 2) Write a query that produces the names and cities of all customers with the same rating as Hoffman. 


```python
SELECT cname,city 
FROM customers
where rating =
(SELECT rating from customers where cname = 'hoffman');

        +---------+--------+
        | cname   | city   |
        +---------+--------+
        | Hoffman | London |
        | Clemens | London |
        | Clemens | London |
        | Pereira | Rome   |
        +---------+--------+
        4 rows in set (0.00 sec)
```
