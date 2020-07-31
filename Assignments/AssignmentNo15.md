# AssignmentNo15


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Assume there is a table called Multicust, with all of the same column definitions as Salespeople. Write a command that inserts all salespeople with more than one customer into this table.


```python
CREATE TABLE Multicast AS
SELECT *
FROM salespeople
WHERE snum IN
    (SELECT snum
     FROM customers
     GROUP BY snum
     HAVING count(snum)>1);
    
SELECT *
FROM multicust;

        SNUM   SNAME    CITY      COMM

        1001   Peel     London     .12
        1002   Serres   San Jose   .13   
```

## 2) Write a command that deletes all customers with no current orders.


```python
INSERT INTO customers
VALUES(2012,
       'rakesh',
       'bikaner',
       500,
       1005);


DELETE customers
WHERE cnum=ANY
    (SELECT cnum
     FROM orders
     WHERE cnum NOT IN
         (SELECT cnum
          FROM customers));

```

## 3) Write a command that increases by twenty percent the commissions of all salespeople with total current orders above Rs. 3,000.



```python
SELECT *
FROM salespeople;


        SNUM  SNAME      CITY        COMM

        1001   Peel      London     .12
        1002   Serres    San Jose   .13
        1004   Motika    London     .11
        1007   Rifkin    Barcelona  .15
        1003   Axelrod   Newyork    .12

UPDATE salespeople
SET comm=comm*1.20
WHERE snum IN
    (SELECT snum
     FROM orders
     WHERE amt>300);


SELECT *
FROM salespeople;


            SNUM   SNAME    CITY       COMM

            1001   Peel    London       .14
            1002   Serres    San Jose   .16
            1004   Motika    London     .13
            1007   Rifkin    Barcelona  .18
            1003   Axelrod   Newyork    .12
```
