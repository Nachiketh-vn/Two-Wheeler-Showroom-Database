```markdown
# Bike Showroom Database SQL Queries

This repository contains SQL queries to create a database for a bike showroom. The database schema includes tables for available bikes, bike features, employees, customers, orders, and insurance.

## SQL Queries

### 1. Create Database

```sql
create database Bike_Showroom;
use Bike_Showroom;
```

### 2. Create `bikes_available` Table

This table stores information about the bikes available in the showroom.

```sql
create table bikes_available (
    bid int primary key,
    company varchar(50),
    name varchar(50),
    status varchar(20),
    price decimal(10,2)
);
```

### 3. Create `bike_features` Table

This table stores information about the features of each bike.

```sql
create table bike_features (
    bid int,
    type varchar(50),
    engine_cc varchar(20),
    milage varchar(10),
    colors varchar(100),
    weight varchar(10),
    height varchar(10),
    ground_clearence varchar(10),
    foreign key (bid) references bikes_available(bid)
);
```

### 4. Create `employee` Table

This table stores information about the showroom employees.

```sql
create table employee (
    eid int primary key,
    job varchar(50),
    salary decimal(10,2),
    age int,
    gender varchar(10),
    email varchar(50)
);
```

### 5. Create `customer` Table

This table stores information about the showroom customers.

```sql
create table customer (
    cid int primary key,
    cname varchar(50),
    caddress varchar(100),
    email varchar(50),
    phone_number int(10),
    interested_bike varchar(50),
    age int(10),
    gender varchar(10)
);
```

### 6. Create `orders` Table

This table stores information about customer orders.

```sql
create table orders (
    cid int,
    ordered_bike_id int,
    price decimal(10,2),
    delivery_date date,
    color varchar(10),
    employee_assigned_id int,
    foreign key (cid) references customer(cid),
    foreign key (ordered_bike_id) references bikes_available(bid),
    foreign key (employee_assigned_id) references employee(eid)
);
```

### 7. Add Primary Key to `orders` Table

This SQL command adds a primary key to the `orders` table.

```sql
alter table orders add oid int primary key;
```

### 8. Create `insurance` Table

This table stores information about insurance associated with orders.

```sql
create table insurance (
    oid int,
    insurance_price decimal(10,2),
    insurance_end_date date,
    foreign key (oid) references orders(oid)
);
```

## How to Use

1. Copy and paste the SQL queries into your preferred SQL database management tool (e.g., MySQL, PostgreSQL, etc.).
2. Execute the queries in the order presented above to create the database and tables.
3. You can then use this database for managing data related to the bike showroom.

Feel free to fork this repository and modify the SQL queries to suit your specific requirements. If you have any questions or encounter issues, please create an issue in this repository.

Happy coding!
```

You can create a new GitHub repository and add this README file to it, along with the SQL queries, for easy sharing and documentation.
