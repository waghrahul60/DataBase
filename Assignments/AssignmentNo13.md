# AssignmentNo13


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1. Create  a  union  of  two  queries  that  shows  the  names,  cities,  and  ratings  of  all customers.  Those  with  rating  of  200  or  greater  will  also  have  the  words  “High Rating”, while the others will have the words “Low Rating”.


```python
-> mysql> select cname,city,'HIGH RATING' rating from customers where rating >200
        -> union
        -> select cname,city,'LOW RATING' rating from customers where rating <=200;
        +-----------+----------+-------------+
        | cname     | city     | rating      |
        +-----------+----------+-------------+
        | Grass     | Berlin   | HIGH RATING |
        | Cisneros  | San Jose | HIGH RATING |
        | Hoffman   | London   | LOW RATING  |
        | Giovanni  | Rome     | LOW RATING  |
        | Liu       | San Jose | LOW RATING  |
        | Clemens   | London   | LOW RATING  |
        | Pereira   | Rome     | LOW RATING  |
        |    kmb    | Rome     | LOW RATING  |
        +-----------+----------+-------------+
```

## 2. Write  a  command  that  produces  the  name  and  number  of  each  salesperson  and each  customer  with  more  than  one  current  order.  Put  the  results  in  alphabetical order.


```python
-> mysql> SELECT sname,
        ->        snum,
        ->        cname
        -> FROM salespeople
        -> JOIN customers using(snum)
        -> WHERE snum IN
        ->     (SELECT snum
        ->      FROM customers
        ->      GROUP BY snum
        ->      HAVING count(snum)>1)
        -> ORDER BY sname,
        ->          cname;
        +--------+------+-----------+
        | sname  | snum | cname     |
        +--------+------+-----------+
        | Peel   | 1001 | Clemens   |
        | Peel   | 1001 | Hoffman   |
        | Rifkin | 1007 |    kmb    |
        | Rifkin | 1007 | Cisneros  |
        | Serres | 1002 | Grass     |
        | Serres | 1002 | Liu       |
        +--------+------+-----------+
```

## 3. Form a union of three queries. Have the first select the snums of all salespeople in San  Jose;  the  second,  the  cnums  of  all  customers  in  San  Jose;  and  the  third  the onums of all orders on October 3. Retain duplicates between the last two queries but eliminate any redundancies between either of them and the first. (Note: in the sample tables asgiven, there would be no such redundancy. This is besides the point.)


```python
-> mysql> SELECT snum
        -> FROM salespeople
        -> WHERE city='san jose'
        -> UNION
        -> SELECT DISTINCT snum
        -> FROM orders
        -> WHERE snum IN
        ->     (SELECT snum
        ->      FROM orders
        ->      WHERE odate LIKE '1990-10-03');
        +------+
        | snum |
        +------+
        | 1002 |
        | 1007 |
        | 1001 |
        | 1004 |
        +------+
```
