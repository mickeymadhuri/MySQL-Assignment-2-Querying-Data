<img width="1863" height="885" alt="24-01" src="https://github.com/user-attachments/assets/084e7ac2-0e03-417a-9e77-ed18834c00d0" />
# MySQL-Assignment-2-Querying-Data

Select distinct salary
From employees;
SELECT
    age AS Employee_Age,
    salary AS Employee_Salary
FROM employees;
SELECT *
FROM employees
WHERE salary > 50000
  AND hire_date < '2016-01-01';
SELECT * FROM Employees
WHERE designation IS Null;
UPDATE Employees
SET designation = 'Data Scientist'
WHERE designation IS Null
   OR designation = '';
   
   SELECT * FROM Employees
ORDER BY department_id ASC, salary DESC;
SELECT * FROM Employees
WHERE hire_date BETWEEN '2018-01-01' AND '2018-12-31'
ORDER BY hire_date ASC
LIMIT 5;
SELECT SUM(e.salary) AS Total_Finance_Salary
FROM Employees e
JOIN Departments d
ON e.department_id = d.department_id
WHERE d.department_name = 'Finance';
SELECT MIN(age) AS Minimum_Age
FROM Employees;
SELECT employee_name,
MAX(salary) AS Maximum_Salary
FROM Employees
GROUP BY employee_name;
SELECT
    designation,
    AVG(salary) AS Average_Salary
FROM Employees
WHERE designation LIKE '%Analyst%'
GROUP BY designation;
SELECT
    employee_name,
    COUNT(employee_id) AS Employee_Count
FROM Employees
GROUP BY employee_name
HAVING COUNT(employee_id) < 3;
SELECT
    employee_name,
    AVG(age) AS Average_Age
FROM Employees
WHERE gender = 'F'
GROUP BY employee_name
HAVING AVG(age) < 30;

SELECT
    e.employee_name,
    e.designation,
    d.department_name
FROM employees e
INNER JOIN Departments d
ON e.department_id = d.department_id;
SELECT
    d.department_name,
    COUNT(e.employee_id) AS Total_Employees
FROM Departments d
LEFT JOIN Employees e
ON d.department_id = e.department_id
GROUP BY d.department_id, d.department_name;

SELECT
    l.location_name,
    e.employee_name
FROM Locations l
LEFT JOIN Employees e
ON l.location_id = e.location_id;
