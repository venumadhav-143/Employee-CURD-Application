-- Employee CRUD Application

-- 1. Create Database
CREATE DATABASE company_db;
USE company_db;

-- 2. Create Employee Table
CREATE TABLE employee (
    emp_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    age INT CHECK (age >= 18),
    department VARCHAR(50) DEFAULT 'IT',
    salary DECIMAL(10,2) NOT NULL CHECK (salary > 0)
);

-- 3. Insert 5 Employee Records
INSERT INTO employee (name, email, age, department, salary)
VALUES
('Rahul', 'rahul@gmail.com', 25, 'HR', 35000),
('Priya', 'priya@gmail.com', 28, 'Finance', 45000),
('Arjun', 'arjun@gmail.com', 24, 'Development', 50000),
('Sneha', 'sneha@gmail.com', 30, 'Testing', 40000);

-- Record using DEFAULT department 'IT'
INSERT INTO employee (name, email, age, salary)
VALUES ('Kiran', 'kiran@gmail.com', 26, 38000);

-- 4. Display All Employees
SELECT * FROM employee;A

-- 5. Update Employee Salary
UPDATE employee
SET salary = 55000
WHERE emp_id = 3;

-- 6. Verify Updated Record
SELECT * FROM employee
WHERE emp_id = 3;

-- 7. Delete One Employee
DELETE FROM employee
WHERE emp_id = 4;

-- 8. Verify Changes
SELECT * FROM employee;