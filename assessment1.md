# Assesment 1

### creating the tables and inserting the records

```sql
create table Students (
   student_id  INT PRIMARY KEY,
   first_name varchar(40),
   last_name varchar(40),
   date_of_birth varchar(20),
   email varchar(40),
   phone_number bigint);

insert into students (student_id, first_name, last_name, date_of_birth, email, phone_number)
values
(1, 'neha', 'reddy', '2003-10-18', 'neha.reddy@gmail.com', 7989857793),
(2, 'keth', 'smily', '2003-03-13', 'keth.smily@gmail.com', 9876543210),
(3, 'nikku', 'bro', '2005-07-09', 'nikku.bro@gmail.com', 1234567890);

create table Teachers(
   teacher_id int Primary Key,
   first_name varchar(40),
   last_name varchar (40),
   email varchar(40));

insert into teachers (teacher_id, first_name, last_name, email)
values
(1, 'raghav', 'kumar', 'raghav.kumar@proclink.com'),
(2, 'saranya', 'allu', 'saranya.allu@proclink.com'),
(3, 'srinivas', 'kudikala', 'srinivas.kudikala@proclink.com')


create table Courses(
   course_id int Primary Key,
   course_name varchar(40),
   credits int ,
   teacher_id  int,
   FOREIGN KEY (teacher_id) REFERENCES Teachers(teacher_id)
   );

insert into courses (course_id, course_name, credits, teacher_id)
values
(101, 'html', 3, 1),
(102, 'sql', 4, 2),
(103, 'javasrcript', 3, 1);


create table Enrollments(
   enrollment_id int  Primary Key,
   student_id int,
   course_id int,
   enrollment_date date,
   foreign key (student_id) REFERENCES Students(student_id),
   foreign key (course_id) REFERENCES Courses(course_id)
   );

insert into enrollments (enrollment_id, student_id, course_id, enrollment_date)
values
(1, 1, 101, '2023-01-10'),
(2, 2, 102, '2023-01-15'),
(3, 3, 103, '2023-01-20');

create table Payments(
   payment_id  int Primary Key,
   student_id int ,
   amount int ,
   payment_date varchar(20),
   FOREIGN KEY (student_id) REFERENCES Students(student_id)
   );

insert into payments (payment_id, student_id, amount, payment_date)
values
(1, 1, 50000, '2023-02-05'),
(2, 2, 60000, '2023-02-10'),
(3, 3, 45000, '2023-02-15');

drop table Students;
drop table Teachers;
drop table Courses;
drop table Enrollments;
drop table Payments;

```

## 1. Write an SQL query to insert a new student named John Doe into the "Students" table.

```sql
insert into Students (student_id, first_name, last_name, date_of_birth, email, phone_number)
values
(4, 'John', 'Doe', '2002-09-04', 'john.doe@gmail.com', 5564646590);
```
