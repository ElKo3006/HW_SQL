SQL_DDL
Первая часть.

Таблица employees

1) Создать таблицу employees
- id. serial,  primary key,
- employee_name. Varchar(50), not null
2) Наполнить таблицу employee 70 строками.
```
create table employees (
id serial primary key,
employee_name varchar (50) not null);
```

```insert into employees (employee_name) values ('Alena'),('Vlad'),('Kate'),('Sasha'), ('Alex'),('Sonia'),('Anna'),('Olia'),('Tania'),('Maria');``` - воспроизвести 7 раз

Таблица salary

3) Создать таблицу salary
- id. Serial  primary key,
- monthly_salary. Int, not null
4) Наполнить таблицу salary 15 строками:
- 1000
- 1100
- 1200
- 1300
- 1400
- 1500
- 1600
- 1700
- 1800
- 1900
- 2000
- 2100
- 2200
- 2300
- 2400
- 2500
```
create table salary (
id serial primary key,
monthly_salary int not null);
```
```insert into salary (monthly_salary) values (1000),(1100),(1200),(1300),(1400),(1500),(1600),(1700),(1800),(1900),(2000),(2100),(2200),(2300),(2400),(2500);```
Таблица employee_salary

5) Создать таблицу employee_salary
- id. Serial  primary key,
- employee_id. Int, not null, unique
- salary_id. Int, not null
6) Наполнить таблицу employee_salary 40 строками:
- в 10 строк из 40 вставить несуществующие employee_id
```
create table employee_salary (
id serial primary key,
employee_id int unique not null, 
salary_id int not null
);
```
```
insert into employee_salary (employee_id,salary_id) values 
(1,16),(2,15),(3,14),(4,13),(5,12),(6,11),(7,10),(8,9),(9,8),(10,7),
(11,6),(12,5),(13,4),(14,3),(15,2),(16,1),(17,16),(18,15),(19,14),(20,13),
(21,12),(22,11),(23,10),(24,9),(25,8),(26,7),(27,6),(28,5),(29,4),(30,3),
(71,16),(72,15),(73,14),(74,13),(75,12),(76,11),(77,10),(78,9),(79,8),(80,7);
```
Таблица roles

7) Создать таблицу roles
- id. Serial  primary key,
- role_name. int, not null, unique
8) Поменять тип столба role_name с int на varchar(30)
9) Наполнить таблицу roles 20 строками:
```
create table roles (id serial primary key,
role_name int unique not null);
```
```alter table roles alter column role_name type varchar (30);```

```
insert into roles(role_name) values
('Junior Python developer'),
('Middle Python developer'),
('Senior Python developer'),
('Junior Java developer'),
('Middle Java developer'),
('Senior Java developer'),
('Junior JavaScript developer'),
('Middle JavaScript developer'),
('Senior JavaScript developer'),
('Junior Manual QA engineer'),
('Middle Manual QA engineer'),
('Senior Manual QA engineer'),
('Project Manager'),
('Designer'),
('HR'),
('CEO'),
('Sales manager'),
('Junior Automation QA engineer'),
('Middle Automation QA engineer'),
('Senior Automation QA engineer');
```
Таблица roles_employee

10) Создать таблицу roles_employee
- id. Serial  primary key,
- employee_id. Int, not null, unique (внешний ключ для таблицы employees, поле id)
- role_id. Int, not null (внешний ключ для таблицы roles, поле id)
11) Наполнить таблицу roles_employee 40 строками:

```
create table role_employees (
id serial primary key,
employee_id int unique not null,
role_id int not null,
foreign key (employee_id) references employees (id),
foreign key (role_id) references roles (id)
);
```

```
insert into role_employees (employee_id,role_id) values (1,4), (2,8), (3,6), (4,13),(5,12),(6,5),(7,11),(8,10),(9,16),(10,14),
(40,3),(38,2),(24,9),(20,6),(29,7),(66,1),(39,2),(33,5),(11,4),(15,3),
(35,5),(37,11),(48,4),(58,8),(57,3),(67,7),(32,10),(21,11),(44,16),(65,14),
(30,14),(18,15),(12,7),(13,2),(17,3),(22,1),(28,2),(45,10),(53,5),(70,16);
```
