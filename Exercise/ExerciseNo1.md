```python
Name:- Rahul Wagh  id:- 200240520045  JUHU
```


```python
1. Create the table SEMP with the following structure:-   
```


```python
create table SEMP
(
EMPNO char(4),
EMPNAME char(20),
BASIC float(9,2),
DEPTNO char(2),
DEPTHEAD char(2)
);
```


```python
2. Create the table SDEPT with the following structure:-   
```


```python
create table SDEPT
(
DEPTNO char(2),
DEPTNAME char(15)
);
```


```python
3. Insert into the SDEPT table the following values:-   
```


```python
a.   insert into SDEPT 
         values('10','Devlopment');
        
b.   insert into SDEPT 
    values('20','Training');

```


```python
4. Insert into the SEMP table the following values:-   
```


```python

    a.  insert into SEMP
        values('0001','SUNIL',6000,'10','NULL');

    b.  insert into SEMP
        values('0002','HIREN',8000,'20','NULL');

    c.  insert into SEMP
        values('0003','ALI',4000,'10','0001');

    d.  insert into SEMP
        values('0004','GEORGE',6000,'NULL','0001');

    e.  create table s
        (
         `s#`int(4),
         Sname varchar(10),
         status char(10),
         city varchar(10)
        );

    f.  create table p
        (
         `p#` int(4),
          Pname varchar(10),
          color varchar(10),
          weight float(7,2),
          city varchar(10)
        );

    g. create table j
       (
        `j#` int(4),
         jname varchar(10),
         city varchar(10)
       );

    h. create table spj
       ( 
        `s#` int(4),
        `p#` int(4),
        `j#` int(4),
        qty float(7,2)
       ); 

```


```python
5. Display all the data from the S table.   
```


```python
select * from s;
```


```python
6. Display only the S# and SNAME fields from the S table.   
```


```python
select `s#`,sname from s;
```


```python
7. select pname,color from p where CITY='London';

```


```python

8. select * from s where CITY='London';


```


```python
9. select * from s where CITY='Paris' or CITY='Athens';


```


```python
10. select * from j where CITY='Athens';


```


```python
11. select Pname,weight from p where weight between 12 and 14;


```


```python
12. select * from s where status>=20;


```


```python
13. select * from s where city!='London';


```


```python
14. select city from s;


```


```python
15. a. select weight*1000 from p;    ->for milligrams
    b. select weight/1000 from p;    ->for kilograms
    
    
```
