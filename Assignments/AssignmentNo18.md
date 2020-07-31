# AssignmentNo18


```python
Name:- Rahul Wagh     ID:- 200240520078     JUHU
```

## 1. Create a table called Cityorders. This will contain the same onum, amt and snum fields  as  the  Orders  table,  and  the  same  cnum  and  city  fields  as  the  Customers table, so that each customer’s order will be  entered into this table  along  with his or  her  city.  Onum  will  be  the  primary  key  of  Cityorders.  All  of  the  fields  in Cityorders will be constrained to match the Customers and Orders tables. Assume the parent keys in these tables already have the proper constraints.


```python
-> mysql> create table cityorders
        -> (
        -> onum int(4) primary key,
        -> amt float(7,2),
        -> snum int(4),
        -> cnum int(4),
        -> city varchar(20)
        -> )
        -> ;

        mysql> desc cityorders;
        +-------+-------------+------+-----+---------+-------+
        | Field | Type        | Null | Key | Default | Extra |
        +-------+-------------+------+-----+---------+-------+
        | onum  | int         | NO   | PRI | NULL    |       |
        | amt   | float(7,2)  | YES  |     | NULL    |       |
        | snum  | int         | YES  |     | NULL    |       |
        | cnum  | int         | YES  |     | NULL    |       |
        | city  | varchar(20) | YES  |     | NULL    |       |
        +-------+-------------+------+-----+---------+-------+
```

## 2. Redefine the Orders table as follows:-add a new column called prev, which will identify, for each order, the onum of the previous order for that current customer. Implement this with a foreign key referring to the Orders table itself. The foreign key  should  refer  as  well  to  the  cnum  of  the  customer,  providing  a  definite enforced link between the current order and the one referenced.


```python
-> Alter table orders add foreign key(prev) references order(onum);

-> Alter table cityorders add foreign key(cnum) references customers(cnum);

```
