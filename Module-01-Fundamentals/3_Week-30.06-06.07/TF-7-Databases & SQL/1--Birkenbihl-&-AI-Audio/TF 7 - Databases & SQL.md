Welcome! Before our live session on Databases and SQL, please go through this material. We'll explore how data is organized and accessed efficiently, a fundamental skill in many tech roles, including cybersecurity.

## What is Data?

In the context of computers, data is essentially information. This could be anything: text, numbers, dates, images. Think about your contacts list – it contains names (text), phone numbers (numbers, maybe text), and maybe birthdays (dates). A shopping website stores information about products (names, descriptions, prices), customers (names, addresses), and orders (product IDs, quantities, dates). All of this is data.

## Why Organize Data?

Imagine trying to find a specific friend's phone number if all your contacts were just scribbled randomly on pieces of paper scattered around your room. It would be slow and frustrating! Computers face a similar challenge when dealing with large amounts of data. We need ways to:

1. **Store** data reliably so it doesn't get lost.
2. **Organize** data logically so it makes sense.
3. **Retrieve** specific pieces of data quickly and easily.
4. **Update** data when things change (like a friend's phone number).
5. **Manage** access to data (who can see or change what).

This is where databases come in.

## What is a Database?

A **database** is an organized collection of data, stored electronically, designed for efficient storage, retrieval, and management. Think of it as a highly organized digital filing cabinet.

Instead of random pieces of paper, a database uses structures to keep things tidy. A very common structure, especially in what we call **relational databases**, is the **table**.

![image.png](attachment:a7dc3332-7546-4c36-8019-e4b08c62f26a:image.png)

## Relational Databases and Tables

A **relational database** organizes data into one or more tables.

- **Table:** A collection of related data entries organized in rows and columns. Think of a spreadsheet. For example, we could have a `Customers` table.
- **Column (or Field):** Represents a specific type of information within a table. Each column has a name and holds a particular data type (like text, number, date). In our `Customers` table, columns might be `FirstName`, `LastName`, `Email`, `SignupDate`. Note: We often add a unique identifier column, like `CustomerID`.
- **Row (or Record):** Represents a single entry or item in the table. Each row contains the specific values for each column for that particular entry. A row in the `Customers` table would represent one specific customer.

Here's a simplified example of a `Customers` table:

|CustomerID|FirstName|LastName|Email|SignupDate|
|---|---|---|---|---|
|1|Alice|Smith|[alice.s@email.com](mailto:alice.s@email.com)|2023-01-15|
|2|Bob|Jones|[b.jones@domain.org](mailto:b.jones@domain.org)|2023-02-10|
|3|Charlie|Brown|[charlie@mailservice.net](mailto:charlie@mailservice.net)|2023-01-15|

### Key Concepts:

- **Structured Data:** Data organized in a predefined format, like tables with rows and columns. Relational databases primarily deal with structured data.
- **Primary Key:** A column (or set of columns) whose value uniquely identifies each row in a table. In the example above, `CustomerID` is likely the primary key because each customer has a unique ID. No two rows can have the same `CustomerID`.
- **Relational:** The "relational" part comes from the ability to link (or relate) data between different tables. For instance, we might have another table called `Orders` with a `CustomerID` column. We could use this `CustomerID` to link an order back to the specific customer in the `Customers` table who placed it.

![image.png](attachment:389d3ca5-95cc-4efc-9ca1-c82f82f0af32:image.png)

### Think about it

- What other tables might a simple online store need besides `Customers` and `Orders`? What columns might those tables have?
- Why is it useful to have separate tables instead of putting all information (customer details, order details, product details) into one giant table?

## What is SQL?

Okay, we have this organized data in tables within a database. How do we actually _interact_ with it? How do we ask the database questions like "Show me all customers who signed up in January?" or "Add a new customer"?

We use a special language called **SQL** (Structured Query Language), often pronounced "sequel" or "S-Q-L".

SQL is the standard language for managing and manipulating data in relational databases. It allows you to:

- **Query data:** Retrieve specific information (e.g., `SELECT`).
- **Insert data:** Add new rows (e.g., `INSERT INTO`).
- **Update data:** Modify existing rows (e.g., `UPDATE`).
- **Delete data:** Remove rows (e.g., `DELETE FROM`).
- **Manage the database structure:** Create tables, define columns, etc. (e.g., `CREATE TABLE`).

## Basic SQL Queries: SELECT

The most common SQL command is `SELECT`. It's used to retrieve data. Its basic structure looks like this:

```sql
SELECT column1, column2, ...
FROM TableName
WHERE condition;
```

- `SELECT`: Specifies the columns you want to retrieve. Using  means "all columns".
- `FROM`: Specifies the table you want to retrieve the data from.
- `WHERE`: (Optional) Filters the rows based on a specific condition. Only rows that meet the condition are returned.

**Examples using our `Customers` table:**

1. **Get all information for all customers:**
    
    ```sql
    SELECT *
    FROM Customers;
    ```
    
2. **Get only the first name and email of all customers:**
    
    ```sql
    SELECT FirstName, Email
    FROM Customers;
    ```
    
3. **Get all information for the customer with CustomerID 2:**
    
    ```sql
    SELECT *
    FROM Customers
    WHERE CustomerID = 2;
    ```
    
    _(Note: Text values in WHERE clauses usually need single quotes, like `WHERE FirstName = 'Alice'`)_
    
4. **Get the email addresses of customers who signed up on '2023-01-15':**
    
    ```sql
    SELECT Email
    FROM Customers
    WHERE SignupDate = '2023-01-15';
    ```
    

### Try it yourself

Look at the example `Customers` table again. Write down (on paper or a text file) the SQL queries you would use to:

1. Get the `LastName` and `Email` for all customers.
2. Get all columns for the customer whose `FirstName` is 'Charlie'.
3. Get the `FirstName` of the customer with `CustomerID` 1.

Don't worry about running these yet; just practice thinking in SQL terms.

## Setup: DB Browser for SQLite

Before the hands-on section, please install DB Browser for SQLite. This tool lets you work with simple databases stored in a single file.

**Installation Steps (macOS):**

1. **Download:** Go to [https://sqlitebrowser.org/dl/](https://sqlitebrowser.org/dl/) and download the latest stable `.dmg` file for macOS.
2. **Install:** Open the downloaded `.dmg` file and drag the "DB Browser for SQLite" icon into your Applications folder.
3. **Verify:** Open the application from your Applications folder to ensure it launches correctly. You might need to approve opening an app downloaded from the internet the first time.

## Hands-On: Your First Database Interaction

Now that you have DB Browser for SQLite installed, let's use it to create and query a simple database.

1. **Launch DB Browser for SQLite:** Open the application from your Applications folder.
2. **Create a New Database:**
    - Click the "New Database" button.
    - Choose a location (like your Desktop or Documents).
    - Enter a file name, e.g., `my_first_db.sqlite`, and click "Save".
3. **Create a Table:**
    - An "Edit table definition" window will pop up.
    - Table name: `Friends`.
    - Click "Add field" three times.
    - Configure the fields:
        - Field 1: Name: `FriendID`, Type: `INTEGER`. Check `PK` (Primary Key).
        - Field 2: Name: `Name`, Type: `TEXT`.
        - Field 3: Name: `Hobby`, Type: `TEXT`.
    - Click "OK".
4. **Add Some Data:**
    - Go to the "Browse Data" tab.
    - Ensure "Table:" shows `Friends`.
    - Click "New Record".
    - Enter data for a few friends (double-click cells):
        - Name: `Alex`, Hobby: `Gaming`
        - Name: `Bea`, Hobby: `Reading`
        - Name: `Chris`, Hobby: `Gaming`
    - Click "Write Changes" to save the data.
5. **Query Your Data with SQL:**
    - Go to the "Execute SQL" tab.
        
    - Type this query in the top editor:
        
        ```sql
        SELECT * FROM Friends;
        ```
        
    - Click the "Execute" button (blue triangle). See the results below.
        
6. **Try Another Query:**
    - Replace the query with:
        
        ```sql
        SELECT Name FROM Friends WHERE Hobby = 'Gaming';
        ```
        
    - Click "Execute". You should see the names 'Alex' and 'Chris'.
        

Congratulations! You've created a database, defined a table, added data, and used SQL to query it. Keep the `my_first_db.sqlite` file handy.

That's it for the pre-class preparation. Make sure you've read through the concepts, installed DB Browser for SQLite, and completed the hands-on exercise. See you in class!

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Technical-Foundations-8-Databases-and-SQL-u7rphwkg1uivnf2?mode=doc](https://gamma.app/docs/Technical-Foundations-8-Databases-and-SQL-u7rphwkg1uivnf2?mode=doc)

Try not to peek before class - spoilers inside!

</aside>