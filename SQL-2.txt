-- Finding the rows whose session is java

select * from RGM where session="Java";

select * from RGM;

-- usage of where clause with a condition

select ID,SName,Session from RGM where session="Java";

-- where with multiple conditions using AND keyword

select * from RGM where session="Python" and Address="Kurnool";

-- Finding the names starting with particular letter using LIKE 

select * from RGM where SName like "s%";     -- % symbol after the letter used to print all the letters(complete name)

select * from RGM where SName like "sh%";

-- Finding the names ending with particular letter 

select * from RGM where SName like "%u";  

-- Finding the names having particular letter at particular position

select * from RGM where SName like "_i%"; 

-- Finding the names starting with particular letter using NOT LIKE 

select * from RGM where SName not like "s%";

select * from RGM where SName not like "sh%";

-- Finding the names not ending with particular letter 

select * from RGM where SName not like "%u";

-- Finding the names not having particular letter at particular position

select * from RGM where SName not like "_i%"; 

-- IN clause usage

select * from RGM where college in ("GPREC","KSRM")

select * from RGM where address in ("Kurnool")

-- using or keyword to find multiple data

select * from RGM where address = "Kurnool" or address = "Nandyal"



create table student (
ID int primary key not null,
SName varchar(20) not null,
Marks int not null);

select * from student;

-- inserting values

insert into student values (101,"chandu",89);
insert into student values (102,"deepthi",94);
insert into student values (103,"manju",87);
insert into student values (104,"pallavi",95);
insert into student values (105,"sowgandhi",92);
insert into student values (106,"divya",88);
insert into student values (107,"manjula",84);
insert into student values (108,"bhavana",85),(109,"dinesh",93),(110,"anjali",96);

-- using comaprision operators

select * from student where marks = 88; 

select * from student where marks < 88; 

select * from student where marks <= 88; 

select * from student where id <= 104; 

select * from student where marks != 85; 

select * from student where marks <> 85;    -- <> symbol represents not equal to 

select * from student where marks between 90 and 99; -- marks between the criteria will be printed

select * from student where marks between 90 and 99 order by marks; -- displays the results in an order by default ascending 

select * from student where marks between 90 and 99 order by marks asc;  -- uing the keyword asc to display in ascending order

select * from student where marks between 90 and 99 order by marks desc;  -- using the keyword desc to display result in descending order

select * from student where not marks = 96;  -- using the not keyword instead of ! or <>

select * from RGM;

-- using DISTINCT keyword to display unique values of a column

select distinct address from RGM;

select distinct college from RGM;

-- using COUNT() function to count the no.of values 

select count(distinct college) from RGM;

select count(distinct marks) from student;

select * from student where marks != 88 and marks != 95;  // select * from student where not marks = 88 and not marks = 95;

-- using the LIMIT keyword to display particular no.of rows

select * from student limit 3;

select * from RGM where session="java" limit 3;

-- using LIMIT with ORDER BY

select * from RGM where session="java" limit 3 order by ID desc;

select count(address),address from RGM group by address;

select * from RGM;

select * from RGM order by address;  -- displays the values in ascending order

select * from RGM order by address limit 4;


-- USAGE OF DATE:

create table DOB (
id int not null,
dob date not null);

INSERT into DOB values(101,"2003-04-10"),(102,"2002-03-17"),(103,"2001-01-23");

select * from dob;




create table salesman (
salesman_id int primary key not null,
name varchar(20) not null,
city varchar(20) not null,
commission float not null);

insert into salesman values(5001,"rishi","hyderabad",0.34);
insert into salesman values(5002,"priya","paris",0.13);
insert into salesman values(5003,"mc lyon","london",0.11);
insert into salesman values(5004,"james","rome",0.16);

select * from salesman;

select name,commission from salesman;


create table orders (
ord_no int primary key not null,
purch_amnt float not null,
ord_date date not null,
custo_id int not null,
salesman_id int not null);

insert into orders values(701,150.43,"2002-10-03",3005,5002),(702,140.43,"2012-02-07",3003,5005),(703,146.43,"2004-03-06",3006,5006);

select * from orders

select * from orders order by ord_no;

select * from orders order by purch_amnt;

select * from orders order by ord_date;

select * from orders order by custo_id;

select * from orders order by salesman_id;
   
