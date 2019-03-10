# SQL-Course-Notes

# Select Query

* Queries written to retrive info from database must contain SELECT and FROM clauses
* SELECT clause specifies columns should be in result table
* FROM clause specifies tables to be used

Select columns example:

```
SELECT column_one, column_two, column_three FROM table_one;
```

Select all columns:

```
SELECT *
FROM table_name;
```


# Where Condition

Allows us to narrow down select query to specific condition. 

```
SELECT column_one, column_two
FROM table_name
WHERE column_three = 'value1';
```

Can also equal another column

```
SELECT column_one, column_two
FROM table_name
WHERE column_three = column_four;
```

# Logical Conditions (AND, OR)

Add logical conditions AND or OR to do multiple conditions. 

```
SELECT column_one, column_two
FROM table_name
WHERE column_three = 'value1' OR column_three = 'value2';
```

# Using Wildcards

```
SELECT column_one, column_two
FROM table_name
WHERE column_three = 'value1' AND column_four = 'some_other_value';
```

