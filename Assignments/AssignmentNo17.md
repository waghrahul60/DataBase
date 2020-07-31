# AssignmentNo17


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1) Create the Orders table so that all onum values as well as all combinations of cnum and snum are different from one another, and so that NULL values are excluded from the date field. 


```python
mysql> CREATE TABLE order_new ( onum INT, cnum INT, snum INT, odate DATE NOT NULL, CONSTRAINT pk_orders PRIMARY KEY (onum,cnum,snum) ); 
 
```


```python
mysql> desc order_new;
        +-------+---------+------+-----+---------+-------+
        | Field | Type    | Null | Key | Default | Extra |
        +-------+---------+------+-----+---------+-------+
        | onum  | int(11) | NO   | PRI | NULL    |       |
        | cnum  | int(11) | NO   | PRI | NULL    |       |
        | snum  | int(11) | NO   | PRI | NULL    |       |
        | odate | date    | NO   |     | NULL    |       |
        +-------+---------+------+-----+---------+-------+
        4 rows in set (0.00 sec)
```

## 2) Create the Salespeople table so that the default commission is 10% with no NULLS permitted, snum is the primary key, and all names fall alphabetically between A and M, inclusive (assume all names will be uppercase). 


```python
mysql>  CREATE TABLE salespeople_new ( snum INT PRIMARY KEY, sname VARCHAR(20) CHECK (SUBSTR(UPPER(sname),1,1) BETWEEN 'A' AND 'M'), city VARCHAR(10) , comm FLOAT(7,2) NOT NULL DEFAULT 0.10 );
Query OK, 0 rows affected (0.03 sec)
```


```python
mysql> desc salespeople_new;
        +-------+-------------+------+-----+---------+-------+
        | Field | Type        | Null | Key | Default | Extra |
        +-------+-------------+------+-----+---------+-------+
        | snum  | int(11)     | NO   | PRI | NULL    |       |
        | sname | varchar(20) | YES  |     | NULL    |       |
        | city  | varchar(10) | YES  |     | NULL    |       |
        | comm  | float(7,2)  | NO   |     | 0.10    |       |
        +-------+-------------+------+-----+---------+-------+
        4 rows in set (0.01 sec)
```

## 3) Create the Orders table, making sure that the onum is greater than the cnum, and the cnum is greater that the snum. Allow no NULLS in any of these three fields. 


```python
mysql> CREATE TABLE order_new2( onum INT NOT NULL CHECK(onum > cnum), cnum INT NOT NULL CHECK(cnum > snum), snum INT NOT NULL CHECK(snum < onum and snum < cnum), odate DATE, amt FLOAT(7,2) );
Query OK, 0 rows affected (0.02 sec)
```


```python
mysql> desc order_new2;
        +-------+------------+------+-----+---------+-------+
        | Field | Type       | Null | Key | Default | Extra |
        +-------+------------+------+-----+---------+-------+
        | onum  | int(11)    | NO   |     | NULL    |       |
        | cnum  | int(11)    | NO   |     | NULL    |       |
        | snum  | int(11)    | NO   |     | NULL    |       |
        | odate | date       | YES  |     | NULL    |       |
        | amt   | float(7,2) | YES  |     | NULL    |       |
        +-------+------------+------+-----+---------+-------+
        5 rows in set (0.01 sec)
```
