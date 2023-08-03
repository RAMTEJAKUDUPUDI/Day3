Microsoft Windows [Version 10.0.22621.1992]
(c) Microsoft Corporation. All rights reserved.

C:\Users\KUDUPUDI RAMTEJA>cd..

C:\Users>cd..

C:\>cd xampp

C:\xampp>cd mysql

C:\xampp\mysql>cd bin

C:\xampp\mysql\bin>mysql.exe -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 8
Server version: 10.4.24-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| collage            |
| collage1           |
| customer           |
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| student            |
| students           |
| test               |
| univ               |
+--------------------+
11 rows in set (0.016 sec)

MariaDB [(none)]> use collage;
Database changed
MariaDB [collage]> create table collage(name varchar(20),id int(10));
Query OK, 0 rows affected (0.023 sec)

MariaDB [collage]> insert into data(name,id) values(ram,1);
ERROR 1146 (42S02): Table 'collage.data' doesn't exist
MariaDB [collage]> insert into collage(name,id) values(ram,1);
ERROR 1054 (42S22): Unknown column 'ram' in 'field list'
MariaDB [collage]> insert into collage(name,id) values('ram',1);
Query OK, 1 row affected (0.003 sec)

MariaDB [collage]> insert into collage(name,id) values('teja',2);
Query OK, 1 row affected (0.007 sec)

MariaDB [collage]> insert into collage(name,id) values('sanjay',3);
Query OK, 1 row affected (0.007 sec)

MariaDB [collage]> insert into collage(name,id) values('vamsi',4);
Query OK, 1 row affected (0.007 sec)

MariaDB [collage]> insert into collage(name,id) values('sri ram',5);
Query OK, 1 row affected (0.007 sec)

MariaDB [collage]> desc collage;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| name  | varchar(20) | YES  |     | NULL    |       |
| id    | int(10)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.006 sec)

MariaDB [collage]> select name,id from collage order by id;
+---------+------+
| name    | id   |
+---------+------+
| ram     |    1 |
| teja    |    2 |
| sanjay  |    3 |
| vamsi   |    4 |
| sri ram |    5 |
+---------+------+
5 rows in set (0.007 sec)

MariaDB [collage]> select count(*) from collage;
+----------+
| count(*) |
+----------+
|        5 |
+----------+
1 row in set (0.008 sec)

MariaDB [collage]> select max(id) from collage;
+---------+
| max(id) |
+---------+
|       5 |
+---------+
1 row in set (0.002 sec)

MariaDB [collage]> select min(id) from collage;
+---------+
| min(id) |
+---------+
|       1 |
+---------+
1 row in set (0.000 sec)

MariaDB [collage]> select avg(id) from collage;
+---------+
| avg(id) |
+---------+
|  3.0000 |
+---------+
1 row in set (0.000 sec)

MariaDB [collage]> select name,id from collage order by id desc;
+---------+------+
| name    | id   |
+---------+------+
| sri ram |    5 |
| vamsi   |    4 |
| sanjay  |    3 |
| teja    |    2 |
| ram     |    1 |
+---------+------+
5 rows in set (0.000 sec)

MariaDB [collage]> select name from collage group by name;
+---------+
| name    |
+---------+
| ram     |
| sanjay  |
| sri ram |
| teja    |
| vamsi   |
+---------+
5 rows in set (0.001 sec)

MariaDB [collage]> select name,id from collage group by name;
+---------+------+
| name    | id   |
+---------+------+
| ram     |    1 |
| sanjay  |    3 |
| sri ram |    5 |
| teja    |    2 |
| vamsi   |    4 |
+---------+------+
5 rows in set (0.001 sec)

MariaDB [collage]> select time_format("%H %I %S");
ERROR 1582 (42000): Incorrect parameter count in the call to native function 'time_format'
MariaDB [collage]> select time format("%H %I %S");
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '("%H %I %S")' at line 1
MariaDB [collage]> select timeformat("%H %I %S");
ERROR 1305 (42000): FUNCTION collage.timeformat does not exist
MariaDB [collage]> select time_format("09:16:10","%H %I %S");
+------------------------------------+
| time_format("09:16:10","%H %I %S") |
+------------------------------------+
| 09 09 10                           |
+------------------------------------+
1 row in set (0.007 sec)

MariaDB [collage]> time_to_sec("09:16:10");
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'time_to_sec("09:16:10")' at line 1
MariaDB [collage]> time_to_sec("09:16:10");
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'time_to_sec("09:16:10")' at line 1
MariaDB [collage]> select time_to_sec("09:16:10");
+-------------------------+
| time_to_sec("09:16:10") |
+-------------------------+
|                   33370 |
+-------------------------+
1 row in set (0.006 sec)

MariaDB [collage]> select timediff("09:16:10","09:16:04");
+---------------------------------+
| timediff("09:16:10","09:16:04") |
+---------------------------------+
| 00:00:06                        |
+---------------------------------+
1 row in set (0.007 sec)

MariaDB [collage]> select timestamp("2023-08-03","09:16:10"));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near ')' at line 1
MariaDB [collage]> select timestamp("2023-08-03","09:16:10");
+------------------------------------+
| timestamp("2023-08-03","09:16:10") |
+------------------------------------+
| 2023-08-03 09:16:10                |
+------------------------------------+
1 row in set (0.000 sec)

MariaDB [collage]> select to_days("2023-08-03");
+-----------------------+
| to_days("2023-08-03") |
+-----------------------+
|                739100 |
+-----------------------+
1 row in set (0.007 sec)


MariaDB [collage]>
