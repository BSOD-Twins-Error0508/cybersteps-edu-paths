Welcome back to SQL! In the previous lesson, we learned the basics of retrieving data from a single table using `SELECT`, filtering with `WHERE`, sorting with `ORDER BY`, and limiting results with `LIMIT`. That's a great start, but most real-world databases organize information across _multiple_ tables. Why? It avoids redundancy (like storing a customer's full address with every single order they make) and keeps data consistent.

This lesson focuses on how to work with data from multiple tables simultaneously and how to perform calculations and summaries directly within your SQL queries. We'll cover techniques essential for extracting more complex and meaningful information.

## Combining Tables with JOINs

The core idea behind relational databases is the "relation" – how different pieces of data connect. SQL provides `JOIN`clauses to combine rows from two or more tables based on a related column between them. This lets you pull together a complete picture from scattered information.

![image.png](attachment:acfdfcd4-4893-4bba-8759-125436b05523:image.png)

### INNER JOIN

The most fundamental join is the `INNER JOIN`. It returns only the rows where there is a match in _both_ tables based on the specified join condition. If a row in one table doesn't have a corresponding match in the other, it's left out of the result.

Think of it like the overlapping area in a Venn diagram.

**Syntax:**

```sql
SELECT table1.column_name, table2.column_name
FROM table1
INNER JOIN table2 ON table1.common_column = table2.common_column;
```

- `FROM table1`: The first table (sometimes called the "left" table).
- `INNER JOIN table2`: The second table (the "right" table) you want to connect.
- `ON table1.common_column = table2.common_column`: The **join condition**. This tells the database _how_ to link the tables. It compares the values in `common_column` from both tables and combines rows where these values are equal. Often, this `common_column` is an ID field (like `user_id`).

**Example:**

Imagine we have `Employees` and `Departments` tables.

**Employees:**

|employee_id|name|dept_id|
|---|---|---|
|101|Alice|10|
|102|Bob|20|
|103|Charlie|10|
|104|David|NULL|

**Departments:**

|dept_id|dept_name|location|
|---|---|---|
|10|Engineering|Building A|
|20|Sales|Building B|
|30|Marketing|Building C|

To list employees alongside their department names:

```sql
SELECT Employees.name, Departments.dept_name
FROM Employees
INNER JOIN Departments ON Employees.dept_id = Departments.dept_id;
```

**Result:**

|name|dept_name|
|---|---|
|Alice|Engineering|
|Bob|Sales|
|Charlie|Engineering|

_Notice:_ David is missing because his `dept_id` is `NULL`, which doesn't match any `dept_id` in `Departments`. The Marketing department is missing because no employee in the `Employees` table has `dept_id` 30.

### OUTER JOINs (LEFT, RIGHT, FULL)

Sometimes you want to keep all rows from one table, even if they don't have a match in the other. `OUTER JOIN`s are used for this.

- **LEFT JOIN (or LEFT OUTER JOIN):** Returns _all_ rows from the left table (`FROM` table) and the matched rows from the right table (`LEFT JOIN` table). If there's no match in the right table, the columns selected from the right table will have `NULL` values for that row.
- **RIGHT JOIN (or RIGHT OUTER JOIN):** Returns _all_ rows from the right table and the matched rows from the left table. If there's no match in the left table, its columns will be `NULL`. (Often, you can rewrite a `RIGHT JOIN`as a `LEFT JOIN` by swapping the table order, which many find more intuitive).
- **FULL OUTER JOIN:** Returns _all_ rows when there is a match in either the left or right table. If a row from one table doesn't have a match in the other, the columns from the non-matching table will be `NULL`. (Not all database systems support `FULL OUTER JOIN`).

**LEFT JOIN Example (Employees and Departments):**

Find all employees and their department names, including employees without an assigned department.

```sql
SELECT Employees.name, Departments.dept_name
FROM Employees
LEFT JOIN Departments ON Employees.dept_id = Departments.dept_id;
```

**Result:**

|name|dept_name|
|---|---|
|Alice|Engineering|
|Bob|Sales|
|Charlie|Engineering|
|David|NULL|

_Notice:_ David is now included, with `NULL` for `dept_name` because his `dept_id` didn't match any department.

### Think about it

Using the `Employees` and `Departments` tables:

1. How would you write a query to show all departments and the names of employees in them, including departments that currently have no employees listed? (Hint: Which table should be the "left" table if using `LEFT JOIN`, or consider `RIGHT JOIN`?)
2. What practical scenario might lead you to prefer a `LEFT JOIN` over an `INNER JOIN` when analyzing employee data?

## A Short Note on NULLs

As seen above, `NULL` represents a missing or unknown value. It's crucial to remember `NULL` is not zero, not an empty string, and not a space. It's the absence of information.

- **Comparisons:** Comparing anything to `NULL` using standard operators (`=`, `!=`, `<`, `>`) results in `UNKNOWN`, which usually acts like `FALSE` in filtering (`WHERE`). Even `NULL = NULL` is not considered true.
- **Checking for NULL:** To find rows where a value is missing, use `IS NULL`. To find rows where a value is present, use `IS NOT NULL`.

**Example:** Find employees _not_ assigned to a department.

```sql
SELECT name
FROM Employees
WHERE dept_id IS NULL;
```

**Result:**

name

---

David

---

### Think about it

Why is it important that `NULL = NULL` evaluates to `UNKNOWN` (effectively false)? How might database operations behave unexpectedly if `NULL` was treated as equal to other `NULL`s in standard comparisons?

## Queries with Expressions

You can perform calculations and manipulate data directly within your `SELECT` statement. This is useful for creating derived information on the fly.

- **Arithmetic:** Use `+`, `-`, `*`, `/`. Be mindful of integer division vs. floating-point division (e.g., `5 / 2` might be `2` in some SQL dialects, while `5 / 2.0` would be `2.5`).
- **String Concatenation:** Often `||` or `+` (depends on the SQL dialect) or functions like `CONCAT()`.
- **Aliases (`AS`):** Give your calculated columns meaningful names using `AS`.

**Example:** Suppose a `Products` table has `item_name` and `price`. Show the price including a 19% tax.

```sql
SELECT
    item_name,
    price,
    price * 1.19 AS price_incl_tax
FROM Products;
```

The result will have three columns: `item_name`, `price`, and the calculated `price_incl_tax`.

### Try it yourself

Given a `LogEvents` table with `event_id`, `start_timestamp`, and `end_timestamp`, write a query to show the `event_id`and the duration of the event in seconds. Assume your SQL dialect allows subtracting timestamps to get an interval, and you might need a function to extract seconds from that interval (the exact function varies, e.g., `TIMESTAMPDIFF(SECOND, start_timestamp, end_timestamp)` in MySQL, or direct subtraction might yield an interval type in PostgreSQL). Name the duration column `duration_seconds`. (Focus on the structure, don't worry about the exact time function name).

## Queries with Aggregates

Aggregate functions perform calculations across a set of rows, returning a single summary value.

**Common Aggregate Functions:**

- `COUNT(column)`: Counts rows where `column` is not `NULL`.
- `COUNT(*)`: Counts the total number of rows selected.
- `SUM(column)`: Sums the values in `column` (ignores `NULL`s).
- `AVG(column)`: Calculates the average of values in `column` (ignores `NULL`s).
- `MIN(column)`: Finds the minimum value in `column`.
- `MAX(column)`: Finds the maximum value in `column`.

**Example:** Find the total number of employees and the highest `employee_id`.

```sql
SELECT COUNT(*) AS total_employees, MAX(employee_id) AS highest_id
FROM Employees;
```

**Result:**

|total_employees|highest_id|
|---|---|
|4|104|

**Grouping Aggregates with `GROUP BY`**

Aggregates become much more powerful when combined with `GROUP BY`. This clause groups rows that share the same value in specified columns, and then applies the aggregate function(s) to each group separately.

**Syntax:**

```sql
SELECT column_to_group_by, AGGREGATE_FUNCTION(column_to_aggregate) AS alias
FROM table_name
WHERE /* optional: filter rows *before* grouping */
GROUP BY column_to_group_by
HAVING /* optional: filter *groups* after aggregation */
ORDER BY /* optional: sort the final grouped results */ ;
```

**Key Rule:** Any column in the `SELECT` list that is _not_ an aggregate function _must_ be included in the `GROUP BY` clause.

**Example:** Count the number of employees in each department.

```sql
SELECT dept_id, COUNT(*) AS num_employees
FROM Employees
WHERE dept_id IS NOT NULL -- Exclude David before grouping
GROUP BY dept_id;
```

**Result:**

|dept_id|num_employees|
|---|---|
|10|2|
|20|1|

_How it works:_

1. `FROM Employees`: Selects the table.
2. `WHERE dept_id IS NOT NULL`: Filters out the row for David.
3. `GROUP BY dept_id`: Groups the remaining rows based on their `dept_id` (one group for `10`, one for `20`).
4. `SELECT dept_id, COUNT(*)`: For each group, selects the `dept_id` and counts the rows within that group.

### Think about it

1. What would the result of the previous query be if we removed the `WHERE dept_id IS NOT NULL` clause? Would `NULL` form its own group? (The behavior might vary slightly between SQL databases, but often `NULL`s are grouped together).
2. How could you modify the query to show the department _name_ instead of the `dept_id`, along with the employee count? (Hint: You'll need a `JOIN`).

## Order of Execution of a Query

While you write SQL in a specific sequence (`SELECT`, `FROM`, `WHERE`, `GROUP BY`, `HAVING`, `ORDER BY`), the database logically processes it in a different order. Understanding this helps troubleshoot and write correct queries.

**Logical Processing Order (Simplified):**

1. **`FROM` / `JOIN`**: Determines the source tables and how they are combined.
2. **`WHERE`**: Filters individual rows based on conditions.
3. **`GROUP BY`**: Groups the filtered rows based on common values.
4. **`HAVING`**: Filters the _groups_ themselves based on conditions (often involving aggregate functions).
5. **`SELECT`**: Determines the final columns and calculates expressions/aggregates for the remaining rows/groups.
6. **`DISTINCT`**: Removes duplicate rows from the result (if specified).
7. **`ORDER BY`**: Sorts the final result set.
8. **`LIMIT` / `OFFSET`**: Selects a subset of the sorted rows.

_Key takeaway:_ `WHERE` filters _before_ grouping, `HAVING` filters _after_ grouping. You can't use an aggregate function (like `COUNT(*)`) in the `WHERE` clause because aggregation hasn't happened yet. You _can_ use aggregates in the `HAVING` clause.

This pre-class material covers joining tables, handling missing data (`NULL`), calculating values within queries, and summarizing data using aggregates and grouping. These are powerful tools for data analysis using SQL. Review these concepts to prepare for the hands-on session.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Technical-Foundations-9-Advanced-SQL-4ekdk0q36xvq7l0?mode=doc](https://gamma.app/docs/Technical-Foundations-9-Advanced-SQL-4ekdk0q36xvq7l0?mode=doc)

Try not to peek before class - spoilers inside!

</aside>