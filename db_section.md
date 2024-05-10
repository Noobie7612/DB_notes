# DataBase section

## Section 1

### Viewing columns

To select the whole table
```
Select * from employees
```
but you can replace the '*' it with whatever column name u need

Alternatively you can use `Describe [tablename]` to get a better view of the table structure

To view distinct rows without any repeating values we use the 'distinct' keyword

```select distinct department_id, first_name from employees```

You can also use arithmetic operators :
**+ addition, - subtraction, * multiplication, / division** and don't forget the ordering for of arithmetic operators

```
select last_name, salary, 12*(salary+100)
from employees;
```

> Note that NULL values aren't affected by any arithmetic operations

### Column Alias

To change the name viewed for a column there is two ways to choose from:

- By using the 'as' keyword after the column name then specifying the name u want to be shown

```
select last_name as name, commission_pct comm
from employees;
```

- Just typing the name after the column name in double quotation

```
select last_name "name", commission_pct "comm"
from employees;
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
from employees;
```


<br><br>

## Section 2

### Selecting specific rows from a table
you can use the keyword 'Where' to select specific rows according to conditions you set yourself

```
select first_name , last_name, department_id
from employees
where department_id = 90;

select last_name
from employees
where last_name ='King'

select first_name , hire_date
from employees
where hire_date between '01/01/2005' and '01/30/2005'
```

| Operator | Meaning |
| -------- | ------- |
|=                      |Equal to |
|>                      |Greater than|
|>=                     |Greater than or equal to|
|<                      |Less than|
|<=                     |Less than or equal to|
|<>                     |Not equal to|
|between ... and ...    |Between two values (inclusive)|
|in (x,y,z,...)         |Match any of the values in the set|
|like ' '               |Match a character pattern|
|is null                |Is a null value|

The value after between must be the lower not the higher one or else it won't run

Like is used to perform wildcard searches and can contain either literal characters or numbers
- % denotes zero or many characters
- _ denotes one character

**You can also use more than one condition using Logical operators**

| Operator  | Meaning    |
| --------- | ---------- |
|and        |Returns TRUE if both component conditions are true|
|or         |Returns TRUE if either component condition is true|
|not        |Returns TRUE if the condition is false|

```
select first_name , hire_date, last_name, manager_id, salary
from employees
where manager_id not in (100,103)

select first_name , hire_date, last_name, manager_id, salary
from employees
where salary >=5000 and job_id like '%MAN%'
```

**Rules of precedence**
Parentheses -> Arithmetic operators -> Concatenation operator -> Comparison conditions -> IS [NOT] NULL, LIKE, [NOT] IN -> [NOT] BETWEEN -> Not equal to -> NOT logical condition -> AND logical condition -> OR logical condition

### Sorting the rows

The keyword 'order by' can be used to arrange the rows according to certain conditions you set yourself asscendingly or descendingly (the default is ascending tho)

```
/*Order by descending order*/
select first_name , hire_date, last_name, manager_id, salary
from employees
order by salary;

/*Order by column number (Salary column is 5th column, look at the table structure to make sure)*/
select first_name , hire_date, last_name, manager_id, salary
from employees
order by 5 desc;

/*Order by alias name*/
select first_name name , hire_date, last_name, manager_id, salary
from employees
order by name;

/*Order by more than one column*/
select first_name name , hire_date, last_name, manager_id, salary
from employees
order by name , salary;
/**/
/**/
```

Ordering by multiple columns orders the rows by the first argument first (in the example above it's name) then if two rows have the same first value then the second argument is used

**from slide 29 till the end isn't on the test**