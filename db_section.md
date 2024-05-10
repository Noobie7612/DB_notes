# DataBase section

## Section 1

### Viewing columns

`Select * from employees` selects the whole table but u can replace it with whatever column name u need

> Alternatively you can use `Describe [tablename]` to display the structure of the table

To view distinct rows without any repeating values we use the 'distinct' keyword

`select distinct department_id, first_name from employees`

You can also use arithmetic operators :
**+ addition, - subtraction, * multiplication, / division** and don't forget the ordering for of arithmetic operators

### Column Alias

To change the name viewed for a column there is two ways to choose from:

- By using the 'as' keyword after the column name then specifying the name u want to be shown
```
SELECT last_name AS name, commission_pct comm
FROM employees;
```

- Just typing the name after the column name in double quotation

```
SELECT last_name "Name" , salary*12 "Annual Salary"
FROM employees;
```
### Concatenation

To show to multiple branches in the same column we use '||' and we can also use alisases with it

```
select first_name||' is '|| job_id as "Description"
from employees;
```

You can also use different delimiting characters by using ' q'' '

```
select first_name || q'#'s salary is: #' ||salary as "Employee salary"
from employees
```

### 

<br><br>

## Section 2