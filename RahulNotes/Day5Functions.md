## Made By : Rahul Wagh

#                                            -: Functions :-

MySQL - Character Functions

fname varchar(20);
lname varchar(20);



```python
Create a emp table :
    
    CREATE TABLE emp
(
fname varchar(20),
lname varchar(20)
);


Insert Values :
    
INSERT INTO emp
values  ('Arun','Purun'),
        ('Tarun','Arun'),
        ('Sirun','Kirun'),
        ('Nautan','Purun');
    
```


```python
mysql> select * from emp;
mysql> mysql> select fname,lname from emp;

+--------+-------+
| fname  | lname |
+--------+-------+
| Arun   | Purun |
| Tarun  | Arun  |
| Sirun  | Kirun |
| Nautan | Purun |
+--------+-------+
4 rows in set (0.00 sec)
```


```python
mysql> select concat(fname,lname) from emp;
+---------------------+
| concat(fname,lname) |
+---------------------+
| ArunPurun           |
| TarunArun           |
| SirunKirun          |
| NautanPurun         |
+---------------------+
4 rows in set (0.00 sec)
```

## How To Add a Blank spaces between two names ?


```python
Method-1 : Works in all RDBMS

mysql> select concat(concat(fname,' '),lname) from emp;
        +---------------------------------+
        | concat(concat(fname,' '),lname) |
        +---------------------------------+
        | Arun Purun                      |
        | Tarun Arun                      |
        | Sirun Kirun                     |
        | Nautan Purun                    |
        +---------------------------------+
        4 rows in set (0.01 sec)
    
```


```python
Method-2 : Works in MySQL (Not supported By oracle)
    
mysql> select concat(fname,' ',lname) from emp;
        +-------------------------+
        | concat(fname,' ',lname) |
        +-------------------------+
        | Arun Purun              |
        | Tarun Arun              |
        | Sirun Kirun             |
        | Nautan Purun            |
        +-------------------------+
        4 rows in set (0.00 sec)
```

## Upper


```python
Converts all data into uppercase.

mysql> select upper(fname) from emp;
+--------------+
| upper(fname) |
+--------------+
| ARUN         |
| TARUN        |
| SIRUN        |
| NAUTAN       |
+--------------+
4 rows in set (0.00 sec)


mysql> update emp set fname = upper(fname);

//this is not a good way to update all table names or data in uppercase.

```


```python
## Case-sensitive query for MySQL

mysql> select * from emp where fname ='ARUN';
+-------+-------+
| fname | lname |
+-------+-------+
| Arun  | Purun |
+-------+-------+
1 row in set (0.00 sec)

## Case-insensitive query for oracle

select * from emp where upper(fname) ='ARUN';
```

## Lower


```python
Converts all data into lowercase.
mysql> select lower(fname) from emp;
+--------------+
| lower(fname) |
+--------------+
| arun         |
| tarun        |
| sirun        |
| nautan       |
+--------------+
4 rows in set (0.00 sec)

mysql> update emp set fname = lower(fname);

//this is not a good way to update all table names or data in lowercase.

```


```python
## Case-sensitive query for MySQL

mysql> select * from emp where fname ='arun';
+-------+-------+
| fname | lname |
+-------+-------+
| Arun  | Purun |
+-------+-------+
1 row in set (0.00 sec)

## Case-insensitive query for oracle

select * from emp where lower(fname) ='arun';
```


```python
Lets Create a New table:

CREATE TABLE emp1
(
ename varchar(20)
);

INSERT INTO emp1
values  ('Arun Purun'),
        ('Tarun Arun'),
        ('Sirun Kirun'),
        ('Nautan Purun');

        
mysql> select * from emp1;
+--------------+
| ename        |
+--------------+
| Arun Purun   |
| Tarun Arun   |
| Sirun Kirun  |
| Nautan Purun |
+--------------+
4 rows in set (0.00 sec)  
```


```python
INITCAP -> Not Suooprted In MySQL(Supported by oracle)

select initcap(ename) from emp1;

```


```python
LPAD : Used for Left justification
    
mysql> select lpad(ename,25,' ') from emp1;

        +---------------------------+
        | lpad(ename,25,' ')        |
        +---------------------------+
        |                Arun Purun |
        |                Tarun Arun |
        |               Sirun Kirun |
        |              Nautan Purun |
        +---------------------------+
        4 rows in set (0.00 sec)

## Used For Cheque Printing
        
mysql> select lpad(ename,25,'*') from emp1;

        +---------------------------+
        | lpad(ename,25,'*')        |
        +---------------------------+
        | ***************Arun Purun |
        | ***************Tarun Arun |
        | **************Sirun Kirun |
        | *************Nautan Purun |
        +---------------------------+
        4 rows in set (0.00 sec)
        
```


```python
RPAD :  Used for Right justification
    
mysql> select rpad(ename,25,' ') from emp1;
        +---------------------------+
        | rpad(ename,25,' ')        |
        +---------------------------+
        | Arun Purun                |
        | Tarun Arun                |
        | Sirun Kirun               |
        | Nautan Purun              |
        +---------------------------+
        4 rows in set (0.00 sec)
        
## Used For Cheque Printing

mysql> select rpad(ename,25,'*') from emp1;
        +---------------------------+
        | rpad(ename,25,'*')        |
        +---------------------------+
        | Arun Purun*************** |
        | Tarun Arun*************** |
        | Sirun Kirun************** |
        | Nautan Purun************* |
        +---------------------------+
        4 rows in set (0.00 sec)
```


```python
Ltrime : Remove the blank spaces from left side.
    ## Output is left jistified

        mysql> select ltrim(ename) from emp1;
        +--------------+
        | ltrim(ename) |
        +--------------+
        | Arun Purun   |
        | Tarun Arun   |
        | Sirun Kirun  |
        | Nautan Purun |
        +--------------+
        4 rows in set (0.00 sec)
        
        
Ltrime : Remove the blank spaces from Right side.
    ## Output is Right jistified  
    ## Use to convert char to verchar
        
        mysql> select rtrim(ename) from emp1;
        +--------------+
        | rtrim(ename) |
        +--------------+
        | Arun Purun   |
        | Tarun Arun   |
        | Sirun Kirun  |
        | Nautan Purun |
        +--------------+
        4 rows in set (0.00 sec)
        
Trime : Remove blank spaces from Both the sides in MySQL.
    
    
mysql> select trim(ename) from emp1;
        +--------------+
        | trim(ename)  |
        +--------------+
        | Arun Purun   |
        | Tarun Arun   |
        | Sirun Kirun  |
        | Nautan Purun |
        +--------------+
        4 rows in set (0.00 sec)
```

## SUBSTR


```python
substr : 

mysql> select substr(ename,3) from emp1; ##Starting Position is 3
        +-----------------+
        | substr(ename,3) |
        +-----------------+
        | un Purun        |
        | run Arun        |
        | run Kirun       |
        | utan Purun      |
        +-----------------+
        4 rows in set (0.00 sec)

mysql> select substr(ename,2) from emp1;  ##Starting Position is 2
        +-----------------+
        | substr(ename,2) |
        +-----------------+
        | run Purun       |
        | arun Arun       |
        | irun Kirun      |
        | autan Purun     |
        +-----------------+
        4 rows in set (0.00 sec)


mysql> select substr(ename,3,2) from emp1;  ## Starting Position is 3 
                                            ## String length is 2
        +-------------------+
        | substr(ename,3,2) |
        +-------------------+
        | un                |
        | ru                |
        | ru                |
        | ut                |
        +-------------------+
        4 rows in set (0.00 sec)



mysql> select substr(ename,3,6) from emp1; ## Starting Position is 3 
                                            ## String length is 6
        +-------------------+
        | substr(ename,3,6) |
        +-------------------+
        | un Pur            |
        | run Ar            |
        | run Ki            |
        | utan P            |
        +-------------------+
        4 rows in set (0.00 sec)


### Use to extract a Part Of a string
```


```python

mysql> select substr(ename, -3) from emp1; ## here -3 mens last three char.
        +-------------------+
        | substr(ename, -3) |
        +-------------------+
        | run               |
        | run               |
        | run               |
        | run               |
        +-------------------+
        4 rows in set (0.00 sec)

mysql> select substr(ename, -3,2) from emp1; ## last 3 char but length = 2
                                             ## lenght started counting from left to right.
        +---------------------+
        | substr(ename, -3,2) |
        +---------------------+
        | ru                  |
        | ru                  |
        | ru                  |
        | ru                  |
        +---------------------+
        4 rows in set (0.00 sec)

mysql> select substr(ename, -6) from emp1;   ## last 6 char
                        
        +-------------------+
        | substr(ename, -6) |
        +-------------------+
        |  Purun            |
        | n Arun            |
        |  Kirun            |
        |  Purun            |
        +-------------------+
        4 rows in set (0.00 sec)

mysql> select substr(ename, -6,4) from emp1; ## last 6 char but length = 4
                                             ## lenght started counting from left to right.
        +---------------------+
        | substr(ename, -6,4) |
        +---------------------+
        |  Pur                |
        | n Ar                |
        |  Kir                |
        |  Pur                |
        +---------------------+
        4 rows in set (0.00 sec)
```

## REPLACE


```python
It is used for replace a specific string.

mysql> select replace(ename,'un','xy') from emp1;
        +--------------------------+
        | replace(ename,'un','xy') |
        +--------------------------+
        | Arxy Purxy               |
        | Tarxy Arxy               |
        | Sirxy Kirxy              |
        | Nautan Purxy             |
        +--------------------------+
        4 rows in set (0.00 sec)
        
        
mysql> select replace(ename,'un','xyz') from emp1;
        +---------------------------+
        | replace(ename,'un','xyz') |
        +---------------------------+
        | Arxyz Purxyz              |
        | Tarxyz Arxyz              |
        | Sirxyz Kirxyz             |
        | Nautan Purxyz             |
        +---------------------------+
        4 rows in set (0.00 sec)
        
mysql> select replace(ename,'un','x') from emp1;
        +-------------------------+
        | replace(ename,'un','x') |
        +-------------------------+
        | Arx Purx                |
        | Tarx Arx                |
        | Sirx Kirx               |
        | Nautan Purx             |
        +-------------------------+
        4 rows in set (0.00 sec)
```

## TRANSLATE


```python
Translate is not avaliable in MySQL. ##It is avaliable in Oracle

select translate(ename,'un','xy') from emp1;

o/p

u -> x
n -> y

select translate(ename,'un','y') from emp1;

o/p

u -> x
n ->           ## N will be removed

```

## INSTR


```python
instr : Return starting position of string
    
mysql> select instr(ename,'un') from emp1;
        +-------------------+
        | instr(ename,'un') |
        +-------------------+
        |                 3 |
        |                 4 |
        |                 4 |
        |                11 |
        +-------------------+
        4 rows in set (0.00 sec)
```

## ASCII


```python
mysql> select ascii(ename) from emp1;
        +--------------+
        | ascii(ename) |
        +--------------+
        |           65 |
        |           84 |
        |           83 |
        |           78 |
        +--------------+
        4 rows in set (0.00 sec)


mysql> select ascii('z') from emp1;
        +------------+
        | ascii('z') |
        +------------+
        |        122 |
        |        122 |
        |        122 |
        |        122 |
        +------------+
        4 rows in set (0.00 sec)
        
mysql> select distinct ascii('z') from emp1;
        +------------+
        | ascii('z') |
        +------------+
        |        122 |
        +------------+
        1 row in set (0.00 sec)
```

## DUAL


```python
DUAL : 
    1.dual is a s/m table.
    2.contains only one row and one columns
    3.is a dummy table
    
```
