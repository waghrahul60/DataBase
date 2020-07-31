# AssignmentNo16


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Write a command that will enable a user to pull orders grouped by date out of the Orders table quickly. 


```python
mysql> SELECT * FROM orders GROUP BY odate;
        +------+---------+------------+------+------+
        | Onum | Amt     | Odate      | Cnum | Snum |
        +------+---------+------------+------+------+
        | 3001 |   18.69 | 1990-10-03 | 2008 | 1007 |
        | 3009 | 1713.23 | 1990-10-04 | 2002 | 1003 |
        | 3008 | 4723.00 | 1990-10-05 | 2006 | 1001 |
        | 3010 | 1309.95 | 1990-10-06 | 2004 | 1002 |
        +------+---------+------------+------+------+
        4 rows in set (0.06 sec)
```

## 2) If the Orders table has already been created, how can you force the onum field to be unique (assume all current values are unique)? 


```python
 ##We can do using the UNIQUE KEY constraint or the PRIMARY KEY constraint. 
```

## 3) Create an index that would permit each salesperson to retrieve his or her orders grouped by date quickly. 


```python
mysql> show index from orders;
+--------+------------+----------------+--------------+-------------+-----------+-------------+----------+--------+------+------------+---------+---------------+
| Table  | Non_unique | Key_name       | Seq_in_index | Column_name | Collation | Cardinality | Sub_part | Packed | Null | Index_type | Comment | Index_comment |
+--------+------------+----------------+--------------+-------------+-----------+-------------+----------+--------+------+------------+---------+---------------+
| orders |          1 | i_odate_orders |            1 | Odate       | A         |           4 |     NULL | NULL   | YES  | BTREE      |         |               |
+--------+------------+----------------+--------------+-------------+-----------+-------------+----------+--------+------+------------+---------+---------------+
1 row in set (0.00 sec)
```

## 4) Let us assume that each salesperson is to have only one customer of a given rating, and that this is currently the case. Enter a command that enforces it


```python

```
