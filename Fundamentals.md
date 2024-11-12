#Learning SQL

###CREATE

```SQL
create table customers(
	customer_id int primary key auto_increment,
	first_name varchar(25), 
	last_name varchar(25),
	hire_date date
);
```

###INSERT
```SQL
insert into customers (first_name, last_name)
values 	("Karlis", "Zarins"),
	("Anna", "Loba"),
        	("Burbulis", "Ozols");
select * from customers;
```

###FOREIGN KEY
```SQL
create table transactions (
	transaction_id int primary key auto_increment,
	amount decimal (5, 2), 
	customer_id int, 
    foreign key (customer_id) references customers(customer_id)
);
```

###ALTER
```SQL
alter table transactions
drop foreign key transaction_id;
```
```SQL
alter table transactions
add constraint key_customer_id
foreign key (customer_id) references customers(customer_id);
```

###INSERT
```SQL
insert into customers (first_name, last_name)
values ("Janis", "Berzins");
select * from customers;
```

###SELECT
```SQL
select * from transactions inner join customers
on transactions.customer_id = customers.customer_id;
```
   
###UPDATE
```SQL
update employees
set job = "cook"
where employee_id = 3;
select * from employees;
```

###OPERATORS
```SQL
select *
from employees 
where hire_date < "2023-01-04";
```

###WILD_CARDS
```SQL
select * from employees 
where first_name like "A%";
```
```SQL
select * from employees 
where first_name like "_anis";
```
###ORDER
```SQL
select * from employees
order by last_name asc;
```

###LIMIT
```SQL
select * from customers
limit 2;
```

###UNION
```SQL
select * from table1
UNION
select * from table2;
```

###UNION ALL(allow duplicates)
```SQL
select * from table1
UNION ALL
select * from table2;
```
