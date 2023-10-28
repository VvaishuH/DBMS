Design and Develop SQL DDL statements which demonstrate the use of SQL objects
such as Table, View, Index, Sequence, Synonym
SQL> create table client_master(client_no int, client_name 
varchar(20),address varchar(50),city varchar(10), pincode int, state
varchar(20),bal_due float,primary key(client_no));
Table created.
SQL> insert into client_master
values('001','abhi','nasik','nasik','422004','MH','5000');
1 row created.
SQL> insert into client_master
values('002','piyu','nasik','nasik','422004','MH','10000');
1 row created.
SQL> insert into client_master 
values('003','abd','nasik','nasik','422003','MH','5000');
1 row created.
SQL> insert into client_master 
values('004','abd','nasik','nasik','422003','MH','5000');
1 row created.
SQL> insert into client_master
values('005','abc','nasik','nasik','422003','MH','5000');
1 row created.
SQL> select * from client_master;
CLIENT_NO CLIENT_NAME ADDRESS CITY PINCODE STATE BAL_DUE
-------------------------------------------------- ---------- ----------
1 abhi nasik nasik 422004 MH 5000
2 piyu nasik nasik 422004 MH 10000
3 abd nasik nasik 422003 MH 5000
4 abd nasik nasik 422003 MH 5000
5 abc nasik nasik 422003 MH 5000
SQL> select client_name, client_no from client_master;
CLIENT_NAME CLIENT_NO
-------------------- ----------
abhi 1
piyu 2
abd 3
abd 4
abc 5
SQL> insert into client_master 
values('006','xyz','nasik','nasik','422004','MH','6000');
1 row created.
SQL> select client_name, client_no from client_master;
CLIENT_NAME CLIENT_NO
-------------------- ----------
abhi 1
piyu 2
abd 3
abd 4
abc 5
xyz 6
6 rows selected.
SQL> create table product_master (product_no int, description varchar (20),
profit_per float, unit_measure varchar (10), quantity int, reorder int,
sell_price float, cost_price float, primary key(product_no));
Table created.
SQL> insert into product_master 
values('001','shampoo','1','one','4','2','10','15');
1 row created.
SQL> insert into product_master 
values('002','oil','13','one','4','2','11','16');
1 row created.
SQL> alter table client_master add telephone_no int;
Table altered.
SQL> select * from client_master;
CLIENT_NO CLIENT_NAME ADDRESS CITY PINCODE STATE BAL_DUE
TELEPHONE_NO
1 abhi nasik nasik 422004 MH 5000
2 piyu nasik nasik 422004 MH 10000
3 abd nasik nasik 422003 MH 5000
4 abd nasik nasik 422003 MH 5000
5 abc nasik nasik 422003 MH 5000
6 xyz nasik nasik 422004 MH 6000
6 rows selected.
SQL> select * from product_master;
PRODUCT_NO DESCRIPTION PROFIT_PER UNIT_MEASU QUANTITY REORDER SELL_PRICE 
COST_PRICE
001 shampoo 1 one 4 2 10 
15
002 oil 13 one 4 2 11 
16
SQL> CREATE TABLE auto (
 2 roll_no NUMBER GENERATED ALWAYS AS IDENTITY NOT NULL,
 3 name VARCHAR2(20),
 4 PRIMARY KEY (roll_no)
 5 );
Table created.
SQL> select * from auto;
no rows selected
SQL> INSERT INTO auto (name) VALUES ('abc');
1 row created.
SQL> INSERT INTO auto (name) VALUES ('adc');
1 row created.
SQL> CREATE SEQUENCE auto_sequence START WITH 100;
Sequence created.
SQL> select * from auto;
 ROLL_NO NAME
---------- --------------------
 1 abc
 2 adc
SQL> update client_master set client_name='nut' where client_no='4';
1 row updated.
SQL> select * from client_master;
CLIENT_NO CLIENT_NAME ADDRESS CITY PINCODE STATE BAL_DUE
TELEPHONE_NO
1 abhi nasik nasik 422004 MH 5000
2 piyu nasik nasik 422004 MH 10000
3 abd nasik nasik 422003 MH 5000
4 nut nasik nasik 422003 MH 5000
5 abc nasik nasik 422003 MH 5000
6 xyz nasik nasik 422004 MH 6000
6 rows selected.
SQL> create index client_find on client_master(client_name, city);
Index created.
SQL> select * from product_master;
PRODUCT_NO DESCRIPTION PROFIT_PER UNIT_MEASU QUANTITY REORDER SELL_PRICE 
COST_PRICE
001 shampoo 1 one 4 2 10 
15
002 oil 13 one 4 2 11 
16
SQL> desc product_master;
Name Null? Type
----------------------------------------- -------- -----------------------
-----
PRODUCT_NO NOT NULL NUMBER(38)
DESCRIPTION VARCHAR2(20)
PROFIT_PER FLOAT(126)
UNIT_MEASURE VARCHAR2(10)
QUANTITY NUMBER(38)
REORDER NUMBER(38)
SELL_PRICE FLOAT(126)
COST_PRICE FLOAT(126)
SQL> alter table client_master rename to c_master;
Table altered.
SQL> insert into product_master 
values('003','nutela','15','three','40','5','110','123');
1 row created.
SQL> create view client as select client_no,client_name from c_master;
View created.
SQL> select * from client;
CLIENT_NO CLIENT_NAME
---------- --------------------
 1 abhi
 2 piyu
 3 abd
 4 nut
 5 abc
 6 xyz
6 rows selected# DBMS
All dbms quries are hear
