# PostgreSQL-Case-Expression

## This repository is about PostgreSQL case expressions. Happy coding!

## The SQL CASE expression is a generic conditional expression, similar to if/else statements in other programming languages. Please follow this link to learn more about Postgresql case.

https://www.postgresql.org/docs/current/functions-conditional.html

### 1) `CASE`

##### Case is like if-else in programming language. If a person understand if-else then he/she will understand this concept.

###### Situation # 01:- I want that if an employee salary is greater than 50000 say it high otherwise low. For example:-

```
select name, salary,
case when salary > 50000
Then 'High'
when salary < 50000 Then 'low'
End as SalaryType
from employees
```

###### Situation # 02:- I want that if an employee salary is greater than or equal to 50000 say it high otherwise low. For example:-

```
select name, salary,
case when salary >= 50000
Then 'High'
when salary < 50000 Then 'low'
End as SalaryType
from employees
```

###### Situation # 03:- I want that if an employee salary is greater than or equal to 50000 say it high if between 40000 and 500000 say it mid otherwise low. For example:-

```
select name, salary,
case when salary >= 50000
Then 'High'
when salary > 40000 And salary < 50000 Then 'mid'
when salary < 40000 Then 'low'
End as SalaryType
from employees
```

###### Situation # 04:- I want to calculate all persons on the base of salary types like how many people are in high salary type. For example:-

```
SELECT
CASE
WHEN salary >= 50000 THEN 'High'
WHEN salary BETWEEN 40000 AND 50000 THEN 'mid'
WHEN salary < 40000 THEN 'low'
END AS SalaryType,
COUNT(*)
FROM
employees
GROUP BY
CASE
WHEN salary >= 50000 THEN 'High'
WHEN salary BETWEEN 40000 AND 50000 THEN 'mid'
WHEN salary < 40000 THEN 'low'
END
```

###### Situation # 04:- I want to calculate only 5% of every employee salary. For example:-

```
select name, salary,
case when salary > 0 Then Round(salary*.10)
else 404
end as bonus
from employees
```

### 2) `IS NULL`

#### It is used to check whether the specific thing is null. For example:-

```
select * from employees
where name IS NULL
```

### 3) `IS NULL`

#### It is used to check whether the specific thing is not like the specific condition like not equal to in programming languages. For example:-

```
SELECT * FROM employees
WHERE fname NOT LIKE 'A%';
```
