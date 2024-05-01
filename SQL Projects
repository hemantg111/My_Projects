show databases;
create database learndb;
use test;

create table students (sid int, Sname char(30), age int, course char(20));

insert into students values (1, "Ram", 27, "MySql");
insert into students values (2, "Siri", 32, "Mysql");
select * from students;
desc students;
create table patients (Pid int, Pname varchar(30), DOB Date, TOA datetime);
insert into patients values (1, "XYZ", "1996-09-12", "2023-08-30 10:11:00");
insert into patients values (2, "ABC", "1995-08-05", now());
select * from patients;

select year(dob) from patients;
select monthname(dob) from patients;
select now();
select 2+3;
select 2>3;
select 3>2 as Result ;
select 2+3 as Total;
select 2 = null as Result;
select 2 is null as Result; 
select 2 is not null as Result;
-- DDL
-- Alter 
desc students;
alter table students add column mark int;
alter table students drop column mark;
alter table students modify COURSE varchar(50);
alter table students change sid std_id int;
alter table students rename Mystudents;
desc mystudents;
select * from mystudents;
-- Rename
Rename table mystudents to students;
-- Drop
create table sample (test varchar(16383));

drop table sample;
-- DML
-- Insert
select * from students;
insert into students (sid, sname, marks) values (3, "John", 80);
insert into students values (5, "Arpitha", 21, "DA", 50), (6, "Siri",22, "DA", 60);
-- Update
set sql_safe_updates = 0;
Update students set sname = "Ramesh" where sid = 1;
update students set age = 25 where age= 27;
select * from students;
update students set MARKS = 80 where sname = "siri" and course = "DA";
update students set MARKS = 90, course = "Statistics" where sid = 4;
update students set course = "MySql";
-- Delete
delete from students where sId = 6;
select * from student;
delete from students where marks = 90;
delete from students;
truncate table students;
-- DQL
select * from myemp;
select * from myemp limit 5;
select * from myemp limit 101,5;
select emp_id, first_name, last_name, salary from myemp;
select emp_id, first_name, last_name, salary, salary * 0.2 as Bonus from myemp;
select emp_id, first_name, last_name, salary + salary * 0.2 as Total_Salary from myemp;
select emp_id, first_name, last_name, round(salary + salary * 0.2, 1) as Total_Salary from myemp;
-- Distinct
select distinct(dep_id) from myemp;
select distinct(mgr_id) from myemp;
select distinct dep_id, mgr_id from myemp;
-- Order by
select distinct(dep_id) from myemp order by dep_id desc;
select distinct dep_id, mgr_id from myemp order by dep_id;
select distinct dep_id, mgr_id from myemp order by dep_id, mgr_id;
select dep_id,mgr_id from myemp order by dep_id,mgr_id;
-- Order the data based on salary column in desending and choose only emp_id, firstname, lastname & salary columns
select emp_id, first_name, last_name, salary from myemp order by salary desc;
-- Operetors
select * from myemp where dep_id = 80;
select * from myemp where salary > 10000;
select * from myemp where salary > 10000 order by salary desc;
select * from myemp where dep_id != 80;
-- employees data who are having their hire year greater than 1995
select * from myemp where Year(hire_date) > 1995 order by year(hire_date);
select * from students;
insert into students values (4,Null, "Mysql",60);

select *,ifnull(sname, "Empty") as Sname from students;
select * from students where sname is null;
select * from myemp order by salary desc;
select * from myemp order by salary desc limit 1,2;
-- Like
select * from myemp where first_name like "a%";
select * from myemp where first_name like "%a";
select * from myemp where first_name like "%a%";
select * from myemp where first_name like "J____";
select * from myemp where first_name Not like "J____";
-- And
select * from myemp where dep_id = 80 and salary > 10000;
-- OR
select * from myemp where dep_id = 50 or dep_id = 60;
select * from myemp where dep_id = 50 or dep_id = 60 or dep_id = 70;
-- IN
select * from myemp where dep_id in (10,20,30,40,50);
select * from myemp where dep_id not in (10,20,30,40,50);
select * from myemp where dep_id not in (10,20,30,40,50) order by dep_id;
select * from myemp where dep_id = 50 and first_name like "a%";
-- Between
select * from myemp where salary between 5000 and 10000;
-- Fetch the employees data who is hired after 1996 and salary in between 5000 and 10000
select * from myemp where year(hire_date) > 1996 and salary between 5000 and 10000 order by year(hire_date);
-- Case
select emp_id, first_name, last_name,
case
when job_id = "ad_pres" then "President"
when job_id = "ad_vp" then "Vice President"
when job_id = "it_prog" then "Programmers"
else "Employee"
end as JobTitle from myemp;
drop table student_name;
create table student_name (first_name varchar(20));
insert into student_name values ("Ram"), ("TOM"), ("JOHN"), ("HARRY");
alter table student_name add column last_name varchar(20);
insert into student_name (last_name) values ("Santosh"), ("Siri"), ("Arpitha"), ("Jyothi");
select * from student_name;
select ifnull(first_name, "Empty") as Names from student_name;
select ifnull(first_name, "Empty") as Names from student_name;
select coalesce(first_name,null,last_name, null) as names from student_name;
select coalesce(null, null, "Hi", null);
select coalesce(null, null, "Hi", "Hello");
-- Aggregate 
select sum(salary) from myemp;
select avg(salary), min(salary), max(salary) from myemp;
select first_name, avg(salary) from myemp; -- Error Code
select * from myemp;
select count(*) from myemp;
-- Count of employees whose salary greater than 10000
select count(*) from myemp where salary > 10000;
-- Count of employees who belongs to dep_id = 50
select count(*) as count from myemp where dep_id = 50;
-- Group by
select dep_id, avg(salary) from myemp group by dep_id;
select dep_id, avg(salary) from myemp group by dep_id order by dep_id;
select dep_id, min(salary) from myemp group by dep_id;
select dep_id, avg(salary) from myemp where dep_id in (10,20) group by dep_id;
select dep_id, avg(salary) from myemp group by dep_id having dep_id in (10,20);
select dep_id, mgr_id, round(avg(salary),2)as Avg_Salary from myemp group by dep_id,mgr_id order by dep_id;
-- Count how many emploees are there dep_id wise
select dep_id, count(*) as Total_count from myemp group by dep_id order by dep_id;
-- Count how many employees are there whose salary greater than 12000, dep_id wise
select dep_id, count(*) as Total_count from myemp where salary > 10000 group by dep_id order by count(*) desc;
-- Constraints
drop table students;
create table students (sid int unique ,
                       sname varchar(30) not null ,
                       age int check(age >21),
                       course varchar(20) default "MySql");
desc students;
show create table students;
insert into students (sid, sname, age) values (1, "Tom", 25);
select * from students;
insert into students (sid,sname, age) values (2,null, 22); -- Error for violating not null constraint
insert into students (sid,sname, age) values (2,"John", 20); -- Error for violating check constraint
drop table students;
 create table students (sid int, sname varchar(30), age int, course varchar(30));
 desc students;
alter table students modify column sid int unique not null;
alter table students modify column sname varchar(30) not null;
delete from authors where authorid = 1;
update authors set authorid = 80 where authorid = 8;
-- Auto_increment
drop table students;
create table students (sid int primary key auto_increment, 
                       sname varchar(30), 
                       age int, 
                       course varchar(30));
insert into students (sname, age, course) values ("Tom", 27, "MySql"), ("John", 28, "Mysql");
select * from students;
alter table students auto_increment = 100;
insert into students (sname, age, course) values ("Tom", 27, "MySql"), ("John", 28, "Mysql");
select * from students;
delete from students;
insert into students (sname, age, course) values ("Tom", 27, "MySql"), ("John", 28, "Mysql");
select * from students;
truncate table students;
insert into students (sname, age, course) values ("Tom", 27, "MySql"), ("John", 28, "Mysql");
select * from students;
select First_name, char_length(first_name) as charther_Length from myemp;
select * from students;
select replace('tom', "t", "d");
select concat(first_name," ",last_name) as full_name from myemp;
select * from myemp;
select  replace(first_name,'Neena','leela') as first_name from myemp ;
-- Inner Join
select * from movies;
select * from members;
select * from members inner join movies on members.movieid = movies.id;
select first_name, last_name,title from members join movies on movieid = id;
-- Left Join
select * from members left join movies on id = movieid;
-- Right Join
select * from members right join movies on movieid = id;
-- Cross join
select * from meals;
select * from drinks;
select * from meals cross join drinks;
select mealname, drinkname,rate from meals cross join drinks; -- Error code
select meals.mealname, drinks.drinkname,meals.rate, drinks.rate from meals cross join drinks;
select meals.mealname, drinks.drinkname,meals.rate + drinks.rate from meals cross join drinks;
select meals.mealname, drinks.drinkname,meals.rate + drinks.rate as Total_cost from meals cross join drinks;
-- Full Join
select * from meals full join drinks;
select m.mealname, d.drinkname, m.rate + d.rate as Total_cost from drinks as d cross join meals as m;
-- Self Join
select* from myemp;
select emp.emp_id, emp.first_name as emp, emp.last_name, mgr.first_name as mgr, mgr.last_name
from myemp as emp join myemp as mgr on emp.mgr_id = mgr.emp_id;

select mv.id, mv.title, ifnull(mm.first_name, "Empty") as First_name , ifnull(mm.last_name, "Empty") as last_name
from members as mm right join movies as mv on movieid = id;
-- TCL
-- Rollback
select * from students;
start transaction;
insert into students (sid, sname, age) values (3, "Harry", 80);
insert into students (sid, sname, age) values (4, "Siri", 50);
select * from students;
rollback;
-- Commit
start transaction;
insert into students (sid, sname, age) values (3, "Harry", 80);
insert into students (sid, sname, age) values (4, "Siri", 50);
select * from students;
commit;
-- SavePoint
create table sample (test varchar(20));
drop table sample;
start transaction;
insert into sample values ('A');
insert into sample values ('B');
savepoint save_till_B;
insert into sample values ('C');
insert into sample values ('D');
savepoint save_till_D;
insert into sample values ('E');
insert into sample values ('F');
select * from sample;
rollback to save_till_B;
rollback to save_till_D;
commit;
-- Views
select mv.id, mv.title, ifnull(mm.first_name, "Empty") as First_name , ifnull(mm.last_name, "Empty") as last_name
from members as mm right join movies as mv on movieid = id;

create view test as select mv.id, mv.title, ifnull(mm.first_name, "Empty") as First_name , ifnull(mm.last_name, "Empty") as last_name
from members as mm right join movies as mv on movieid = id;
select * from test;

create view dep_50 as select * from myemp where dep_id = 50;

select * from authors;
create view sample_author as select * from authors where authorid < 10;
select * from sample_author;
insert into sample_author values (1, "Siri");
select * from authors;
select * from sample_author;
insert into sample_author values (20, "Harry");
select * from authors;
select * from sample_author;
drop view sample_author;
create view sample_author as select * from authors where authorid < 10 with check option;
insert into sample_author values (8, "Tom");
-- Indexes
select * from myemp;
desc myemp;
show indexes from myemp;
desc students;
show indexes from students;
select * from myemp 
where Year(hire_date)> 2000;
create index test on myemp (hire_date);
drop table student;
create table student (sid int primary key, sname varchar(30), Phoneno int);
show indexes from student;
create unique index stu on student (sname, phoneno);
insert into student values (1, "Tom", 9550);
insert into student (sid, phoneno) values (2, 9550);
select * from student;
update student set sname = "Tutu" where sid = 2;
select 2+3 as "total number";
select First_name, salary from myemp
union
select last_name, salary from myemp;
desc students;
describe students;
alter table students drop sid, drop sname;
select * from students;
delete from sample_author where authorid = 3;
call sample();
call proc_author(5);
Call new_procedure(@Avg_salary_Myemp);
select @avg_salary_myemp;
select avg(salary) from myemp;
select * from employees;
call test(@President);
call proc_if(1);
select * from authors;
update sample_author set name = "Tom" where authorid = 3;
select * from myemp where emp_id = 100;
call proc_fraud(3, null);
select * from payments;
select * from fraud;
select * from authors;
call proc_cursor();
use learndb;
select * from myemp;
-- User defined Function
select emp_id, first_name, hire_date, experience(emp_id) from myemp;
-- SubQueries
select emp_id, first_name, last_name from myemp where salary = (select max(salary) from myemp);
select avg(salary) from myemp;
select * from myemp where salary > (select avg(salary) from myemp) order by salary ;
select * from myemp as e where salary > (select avg(salary) from myemp where dep_id = e.dep_id);
select dep_id, avg(salary) from myemp group by dep_id ;
select * from books where authorid = (select authorid from authors where name like "sidney%");
select * from members where movieid in (select id from movies where title like "%Safe%");
-- Triggers
-- After Update
select * from books;
select * from book_sales;
desc book_sales;
Alter table books add column saless int default 0;
update books set sales = sales+3 where bookid = 5;
update books set sales = sales + 5 where bookid = 5;
-- Before Insert
create table emp (emp_id int, name varchar(20), working_hrs int);
select * from emp;
insert into emp values (1, "Tom", 30);
insert into emp values (2, "John", -30);
insert into emp values (3, "Harry", -34);
-- CTE
select avg(salary) as avgsal, min(salary) as minsal, max(salary) as maxsal from myemp;
with cte as (select avg(salary) as avgsal, min(salary) as minsal, max(salary) as maxsal from myemp) select
minsal, maxsal from cte;
select first_name as fname, last_name, salary, salary*0.2 as bonus from myemp;
with cte as (select first_name as fname, last_name, salary, salary*0.2 as bonus from myemp) select 
fname, bonus from cte;
-- Window Function
select first_name, last_name, dep_id,salary, avg(salary) over (partition by dep_id) as Avgsal from myemp;
select first_name, last_name, dep_id, mgr_id, salary, avg(salary) over (partition by dep_id, mgr_id) as Avgsal from myemp;
select first_name, last_name, dep_id,salary, row_number() over(order by dep_id) as RowNumber from myemp;
select first_name, dep_id, salary, rank() over(order by salary desc) as Rnk, dense_rank() over(order by salary desc) as dense_rnk from myemp;
select* from (select first_name, last_name, dep_id,salary, rank() over (partition by dep_id order by salary ) as sal_rnk from myemp) as a where sal_rnk=1;
-- Rank
select * from t;
select val, rank() over (order by val desc) as rnk from t;
-- Dense_Rank
select val, dense_rank() over (order by val desc) as rnk from t;
select * from sales;
select sales_employee, fiscal_year, sale, dense_rank() over (partition by fiscal_year order by sale desc) as Rnk from sales;
select * from (select sales_employee, fiscal_year, sale, dense_rank() over (partition by fiscal_year order by sale desc) as Rnk from sales) as a where rnk=1 ;
select * from (select sales_employee, fiscal_year, sale, dense_rank() over (partition by fiscal_year order by sale desc) as Rnk from sales) as a where rnk>2 ;
-- First_value
select emp_id, first_name, last_name, first_value(first_name) over (order by salary desc) as Highest_Paid from myemp ;
-- nth_value
select emp_id, first_name, last_name,salary, nth_value(first_name, 5)over (order by salary desc) as Fifth_Highest_Paid from myemp;
--                                              or
select* from(select emp_id, first_name, Last_name, salary, rank() over(order by salary desc) as Sal from myemp) as a where Sal<6; 

select train_id, station, time, lead(time, 1) over (partition by train_id order by time) as Next_station_time from trains;
-- Lead
select * from tte;
select * from tt;
with s as (select train_id, station, time, lead(time,1) 
over (partition by train_id order by time) as Next_station_time from trains)
select train_id, station, time, next_station_time, subtime(next_station_time, time) as Transit_time from s;

use learndb;
create table tte (sid int,sname varchar(10));
alter table tte modify column sname varchar(30);
desc tte;
drop table tt;
insert into tte values ( 1,'A');
insert into tte values (1,'A');
insert into tte values (2,'B');
insert into tte values (3,'C');
insert into tte values (5,'D');
create table tt (sid int, course varchar (10));
insert into tt values(1,'A');
insert into tt values (2,'B');
insert into tt values (4, 'F');
insert into tt values (4, 'F');
insert into tt values (6,'G');
insert into tt values (7,'H');
select* from tte inner join tt on tte.sid=tt.sid;
select* from tte left join tt on tte.sid=tt.sid;

## SQL Interview Questions ##

select  * from myemp order by salary desc limit 2;
select sum(salary) as a, dep_id from myemp group by  dep_id order by a desc limit 5;
select dep_id, sum(Salary) as total_salary from myemp group by dep_id order by  total_salary desc limit 5;
select dep_id, salary, First_name, rank() over(partition by dep_id order by salary desc) as rn from myemp;
select dep_id, Salary, rank() over(order by salary desc) from myemp  ;
-- Top 5 salary yearwise
select year(hire_date), round(sum(salary),0) as Total_salary from myemp group by year(HIRE_DATE) order by Total_salary desc limit 5;

-- write a sql query to fetch all records from a table
select * from myemp;
select distinct dep_id, first_name, salary from  myemp;
select dep_id, salary from myemp order by salary desc limit 5;
select  count(*) from myemp;
show tables;
select * from orders  join products ;
select * from (select dep_id, First_name, salary, rank() over(order by salary desc) as rnk from myemp) a where rnk = 2;
--                                        vs
select* from(select emp_id, first_name, Last_name, salary, rank() over(order by salary desc) as Sal from myemp) as a where Sal<6;
select dep_id, avg(salary) from myemp group by dep_id;
 
select* from person;
update person set lname = "sherry"  where id=1;
select* from( select  emp_id, First_name,salary, rank() over(order by salary desc) as sal from myemp) as a where sal=5;
select* from(select emp_id, first_name, Last_name, salary, rank() over(order by salary desc) as Sal from myemp) as a where Sal<6; 
select first_name from myemp where FIRST_NAME like 'a%' ;
select sum(salary) as total_sal from myemp;
select dep_id,emp_id, first_name from myemp where dep_id= 100;
select emp_id, first_name, salary from myemp order by salary desc limit 1;
create table mp (uname varchar(30), age int, course varchar(30));
insert into  mp values ("A", 21, "da") ,("b", 32, "da"), ("c", 31, "da"), ("D", 34, "sd");
select* from Mp;
select distinct count(*) as Mcommon from person;
-- most common value from table --
select FIRST_NAME, count(*) as most_comm_V from myemp group by FIRST_NAME order by most_comm_v desc limit 1;
--  create new table from existing table myemp  --
create table emp_n as select first_name, emp_id from myemp;
select* from emp_n;
---      Employee hire in last 60 month ---
SELECT * FROM myemp
WHERE HIRE_DATE >= DATE_SUB(CURDATE(), INTERVAL 60 MONTH);

UPDATE employees SET salary = salary * 1.1 WHERE department = 'Sales';

--  fetch Random order record from table --
select * from emp order by rand();

DELETE p1 FROM person p1 INNER JOIN person p2 
WHERE p1.id > p2.id AND p1.lname = p2.lname;


