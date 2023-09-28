# Ex. No: 6 Creating Cursors using PL/SQL
## AIM:
To create a cursor using PL/SQL.

## Steps:
1.Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);

2.Create a cursor named as employee_cursor

3.Using cursor read each record and display the result

4.Close the cursor

## Program:
```
Create employee table
CREATE TABLE employd (
  empid NUMBER,
  empname VARCHAR(10),
  dept VARCHAR(10),
  salary NUMBER
);
select * from employd;
INSERT INTO employd VALUES (1, 'John Doe', 'Sales', 100000);
INSERT INTO employd VALUES (2, 'Jane Doe', 'Marketing', 120000);
```
## PLSQL Cursor code
```
DECLARE
   CURSOR employd_cursor IS
   SELECT empid,empname,dept,salary
   FROM employd;
   emp_id NUMBER;
   emp_name VARCHAR(50);
   emp_dept VARCHAR(50);
   emp_salary NUMBER;
BEGIN
  OPEN employd_cursor;

  LOOP
    FETCH employd_cursor INTO emp_id, emp_name, emp_dept, emp_salary;

    EXIT WHEN employd_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
    DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
  END LOOP;

  CLOSE employd_cursor;
END;
/
```
## Output:
![image](https://github.com/Niroshassithanathan/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/121418437/f7b8a475-4cba-4460-bbe7-01c035918502)

## Result:
Thus this program executed successfully.
