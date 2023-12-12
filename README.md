```markdown
# Bike Showroom Database SQL Queries

This repository contains SQL queries to set up and manage a bike showroom database. The database schema includes tables for bikes available, bike features, employees, customers, orders, insurance, inventory, sales, and triggers for enforcing business rules.

## Table Structure

### 1. bikes_available Table

Stores information about available bikes in the showroom.

```sql
CREATE TABLE bikes_available (
    bid INT PRIMARY KEY,
    company VARCHAR(50),
    name VARCHAR(50),
    status VARCHAR(20),
    price DECIMAL(10, 2)
);
```

### 2. bike_features Table

Contains detailed features for each bike.

```sql
CREATE TABLE bike_features (
    bid INT,
    type VARCHAR(50),
    engine_cc VARCHAR(20),
    milage VARCHAR(10),
    colors VARCHAR(100),
    weight VARCHAR(10),
    height VARCHAR(10),
    ground_clearence VARCHAR(10),
    FOREIGN KEY (bid) REFERENCES bikes_available(bid)
);
```

### 3. employee Table

Stores employee details for the showroom.

```sql
CREATE TABLE employee (
    eid INT PRIMARY KEY,
    job VARCHAR(50),
    salary DECIMAL(10, 2),
    age INT,
    gender VARCHAR(10),
    email VARCHAR(50),
    ename VARCHAR(20)
);
```

...(Continue with creating other tables and constraints as per your SQL queries)...

## Data Insertion

The provided SQL statements include sample data insertion for different tables:

- **bikes_available**
- **bike_features**
- **employee**
- **customer**
- **orders**
- **insurance**
- **inventory**
- **sales**

## Triggers

Several triggers are included in the SQL script to enforce business rules:

- **enforce_minimum_bike_price**: Ensures the minimum price for bikes is met.
- **update_inventory_on_sale**: Updates inventory after a sale.
- **calculate_total_sales_amount**: Calculates total sales amount for each employee.
- **auto_assign_job_title**: Automatically assigns job titles to employees based on salary.
- **update_customer_interest**: Updates
