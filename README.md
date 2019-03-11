# SQL-Course-Notes

## Select Query

Select columns example:

```
SELECT column_one, column_two, column_three FROM table_one;
```

Select all columns:

```
SELECT *
FROM table_name;
```


## Where Condition

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

## Logical Conditions (AND, OR)

Add logical conditions AND or OR to do multiple conditions. 

```
SELECT column_one, column_two
FROM table_name
WHERE column_three = 'value1' OR column_three = 'value2';
```

```
SELECT column_one, column_two
FROM table_name
WHERE column_three = 'value1' AND column_four = 'some_other_value';
```


## Using Wildcards

To find an attribute that contains a word:

```
SELECT column_one, column_two
FROM table_name
WHERE column_three LIKE '%value%';
```

If we don't know whether upper or lower-case, we can use LOWER():

```
SELECT column_one, column_two
FROM table_name
WHERE LOWER(column_three) LIKE '%value%';
```

To search for numeric value where first digit is "4" with 4 unknown digits following it:

```
SELECT column_one, column_two, column_three
FROM table_name
WHERE column_three LIKE '4____';
```

To find all values where first digit is not 4 in this sequence, we use NOT LIKE:

```
SELECT column_one, column_two, column_three
FROM table_name
WHERE column_three NOT LIKE '4____';
```

## Comments in PostgreSQL

Single-line

```
-- Comment
```

Multi-line

```
/*
Comment line one
line two
line three
blah
*/
```

# Working with Data

## Alter Table

Add column. Remember to specify datatype (e.g. float8). 

```
ALTER TABLE table_name
ADD COLUMN new_column_name float8;
```

Set value of new column to sum of some other columns:

```
UPDATE table_name
SET new_column = old_column_1 + old_column_2 + old_column_3;
```

Avoid divide by zero error with WHERE clause:

```
UPDATE table_name
SET new_column_pct = (column_1 / column_4) * 100
WHERE column_4 > 0;
```

## Order By

View by ascending order (ASC) or descneding order (DESC) by column:

```
SELECT * 
FROM table_name
ORDER BY column_1 ASC;
```

Order by multiple columns:

```
SELECT * 
FROM table_name
ORDER BY column_1 ASC, column_2 ASC;
```

Default order is ascending, so the below code will do the same as above:

```
SELECT * 
FROM table_name
ORDER BY column_1, column_2;
```

## String Operations

Length function returns length of string:

```
SELECT column1, len(column1)
FROM table_name;
```

Left / right functions returns only x number of characters from the left / right side:

```
SELECT left(column1, 4)
FROM table_name;
```

Reverse function reverses the string:

```
SELECT reverse(column1)
FROM table_name;
```

## Dates

