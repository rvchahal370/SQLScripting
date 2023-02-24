What is a database- As collection of data and holds this data in the form of tables

what is a table- Holds the data in form of rows and columns
It is similar to excel spreadsheet.

database provides us a capability to access and manipulate this data.

Two types of databses
=======================

1. Relational Database- data is stored in the form of rows and colums and also tables having the relationship with them
Examples are MySQL,SQL Server, PostreSQL, SQLite, MariaDB

2. NOSQL/NoRelational Database- Having Key value, Graph, Document
Examples are Hbase, MongoDB, Cassandra

SQL- Structured Query Language- is used to query a relational database

C- Create
R- Read -> Select
U- Update
D- Delete

DDL- Data Definition Language- Commands used to change/alter the structure/schema of the table
Examples are Create, Alter, Drop, Truncate, Rename

DML- Data manipulation Language- Commands Used to change the data of the table
Example are Insert, Update, Delete, Select

Difference between Truncate and Delete
- Truncate is DDL command whereas Delete is DML command
- Truncate delete the only records like Delete command, But truncate first Drop the table and than recreate the table
whereas Delete command delete the records one by one
- Truncate is more faster than Delete command, so for the large data set it is always recommended to choose the Truncate command over Delete

TIMESTAMP data type used to get the present date time 
Example:- Changed_date TIMESTAMP DEFAULT NOW() ON UPDATE NOW()

CONSTRAINT means we are defining a rules and according to that rules data should be entered
CONSTRAINT are used to limit the type of data that can go into a table.
This ensures the accuracy and reliability of the data is maintained.
if there is any voilation then the action is aborted.
Types of constraint are->
NOT NULL
UNIQUE KEY
PRIMARY KEY
FOREIGN KEY
CHECK CONSTRAINT (Not included in MYSQL)
Foreign Key Constraint query- FOREIGN KEY(Existing_table_column_name) REFERENCE Linking_table_name(Linking_table_column_name)

The foreign key constraint is used to prevent actions that would destroy links between two tables

A foreign key is a field in one table that refers to the primary key in another table.

The table with the foreign key is called the child table, the table with the primary key is called the parent or referenced table.

Select Source_of_joining, enrollment_date from students

Order of Execution
====================

FROM (Loading the table)

Select(Projecting Source_of_joining, Enrollment_date)

Select Source_of_joining, enrollment_date from students order by enrollment_date

Order of Execution
====================

FROM (Loading the table)
Select * from Students

Select(Projecting Source_of_joining, Enrollment_date)
Select Source_of_joining, Enrollment_date from Students

Order By (Order By Enrollment_date)
Select Source_of_joining, Enrollment_date from Students Order By Enrollment_date


Select Source_of_joining from students order by enrollment_date

Order of Execution
====================

FROM (Loading the table)
Select * from Students

Select(Projecting Source_of_joining, Enrollment_date)
Select Source_of_joining, Enrollment_date from Students

Order By (Order By Enrollment_date)
Select Source_of_joining from Students Order By Enrollment_date


Select DISTINCT Source_of_joining from Students Order By Enrollment_date

Order of Execution
====================

FROM (Loading the table)
Select * from Students

Select(Projecting Source_of_joining, Enrollment_date)
Select Source_of_joining, Enrollment_date from Students

DISTINCT
Select DISTINCT Source_of_joining, Enrollment_date from Students // DISTINCT will applicable for both the columns which is logically incorrect thats why system will throw an error

Order By (Order By Enrollment_date)
Select Source_of_joining from Students Order By Enrollment_date

/* Find how many students get to know throught the different source_of_joining */
Select Source_of_joining, Count(*) from Students Group By source_of_joining

/* Find out how many students get to know through the common source of Source_of_joining and location */
Select location, Source_of_joining from Students Group By Source_of_joining, location

Where and Having Clause
===============================

Where clause is used before the Group By and do filtering on the individual records
Where clause is used after the Group By and do filtering on the aggregative records
Where and Having clause is used together in the same query

Rank and DenseRank
===========================

Note: RowNumber() must be used with the Order By
RowNumber() will not be of any use where records are duplicate, Example for the same salary as 20000 ROWNUMBER() will be giving the number as 2 and 3 without any creteria
For this kind of scenario Rank() and DenseRank() will work

Difference between Rank() and DenseRank()

Rank()- For the duplicate values same Rank will be assigned but for the next entry it skips the Rank
Example- 3 3 5 6

DENSERANK()- It Doesn't skip the Rank in between
Example- 3 3 4 5





