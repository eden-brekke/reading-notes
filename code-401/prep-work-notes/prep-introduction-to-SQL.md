# SQL Practice

## Tasks

This prework will introduce you to some of the more common SQL statements and query techniques, allowing you to practice visualizing and querying a relational database.

1. Download the free e-book, [Learn SQL](https://landing.chartio.com/download-learn-sql), which is an excellent introduction to SQL and relational databases.
    * Skim the book.
    * Save this for later reference.

2. Practice running common SQL commands using the following [SQL Bolt](https://sqlbolt.com/) tutorials.
    * Lessons 1 through 6 - SQL Queries
    * Lessons 13 through 18 - Database Management
        * For each of the tutorial sections:
            * Read the guidance.
            * Complete the exercises.
            * Capture a screen shot of the completed task list.


## Chapter 1 Writing SQL Queries

### Ch.1 Guidance Notes

To retrieve data from an SQL DB you use the SELECT Statement (colloquially refered to as *queries*)  
Just refers to what data we are looking for.  
You can think of a table in SQL as an entity and each row as an instance of that entity.  

An example of a basic query:  
SELECT column, another_column, ...  
FROM mytable;  

Where the result of the above query will be a 2D set of rows/columns.  
If you were looking to receive all the columns of a data you would use the * (universal selector)  


Use the DB with dat about pixar movies.

1. Find the title of each Film
2. Find the Director of each film
3. Find the title and Director of each film
4. Find the title and year of each film
5. Find all the info about each film. 

### Ch.1 Screenshot

![Chapter 1 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.1Complete.png)

## Chapter 2: Queries with Constraints (pt.1)

### Ch.2 Guidance Notes

The next step is knowing how to filter certain results from what is being returned.  
To do this we use the WHERE clause in the query.  

Example:  
SELECT column, another_column, ...  
FROM mytable  
WHERE condition  
  AND/OR another_condition  
  AND/OR ...;  

We use the AND or OR logical keywords to make the search more complex.  

Some Useful Operators:  
| Operator| Condition | SQL Example |
|:-------|:--------:|------:|
|=,!=,<,<=,>,>=|Standard numerical Operators|col_name !=4|
|BETWEEN ... AND ... | Number is within range of two values (inclusive)|col_name BETWEEN 1.5 AND 10.5|
|NOT BETWEEN... AND...|Number is not within range of two values (inclusive)| col_name NOT BETWEEN 1 AND 10|
|IN(...)|Number exists in a list|col_name IN (2,4,6)|
|NOT IN(...)| Number does not exist in a list| col_name NOT IN (1, 3 ,5)|

** SQL doesn't require you to write all caps but it's a convention to hlp distinguish SQL keywords from column/table names.  

Exercise 2 — Tasks  
Find the movie with a row id of 6  
Find the movies released in the years between 2000 and 2010  
Find the movies not released in the years between 2000 and 2010  
Find the first 5 Pixar movies and their release year  

### Ch.2 Screenshot

![Chapter 2 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.2Complete.png)

## Chapter 3: Queries with constraints (pt.2)

### Ch.3 Guidance Notes

|Operator|Condition|Example|
|:-------|:--------:|------:|
| = |Case sensitive exact string comparison| col_name="abc"|
| != or <> | Case Sensitive exact string inequality comparison| col_name !="abcd"|
| LIKE | Case insensitive exact string comparison|col_name LIKE "ABC"|
| NOT LIKE | Case insensitive exact string inequality comparison|col_name NOT LIKE "ABCD"|
| % | Used anywhere in a string to match a sequence of zero or more characters (only with LIKE or NOT LIKE)| col_name LIKE "%AT%" (matches "AT "ATTIC" "CAT" BATS" etc.)|
| _ | Used anywhere in a string to match a single character (Only with LIKE or NOT LIKE)|col_name LIKE "AN_" (matches "AND" but not "AN")|
| IN (...) | String exists in a list | col_name IN ("A","B","C")|
| NOT IN (...) | String does not exist in a list | col_name NOT IN ("D", "E", "F")|

All strings must be quotes so the query parses can distinguish words in a string from SQL keywords  

Example:  
SELECT column, another_column, ...  
FROM mytable  
WHERE condition  
  AND/OR another_condition  
  AND/OR ...;  

Exercise 3 — Tasks  
Find all the Toy Story movies  
Find all the movies directed by John Lasseter  
Find all the movies (and director) not directed by John Lasseter  
Find all the WALL-* movies  

### Ch.3 Screenshot

![Chapter 3 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.3Complete.png) 

## Chapter 4: Filtering and Sorting Query Results 

### Ch.4 Guidance Notes

Though the data in the DB may be unique the results may not be.  
SQL allows you to discard rows that have duplicate column values with the DISTINCT keyword  

Example:  
SELECT DISTINCT column, another_column, ...  
FROM mytable  
WHERE condition(s);  

Since DISTINCT will blindly remove duplicate rows, later we'll learn the GROUP BY clause for further specificity 

Ordering results: most DB are added in no particular order, so the results could be difficult to read.  
SQL has an ORDER BY clause which sorts results from a given column in ascending or descending order  

Example:  
SELECT DISTINCT column, another_column, ...  
FROM mytable  
WHERE condition(s)  
ORDER BY column ASC/DESC;  

each row is sorted alpha-numerically based on columns value.  

Limiting results to a subset: often used with ORDER BY are the LIMIT and OFFSET clauses.  
LIMIT will reduce number of rows  
OFFSET will specify where to begin counting the rows from  

Example:  
SELECT DISTINCT column, another_column, ...  
FROM mytable  
WHERE condition(s)  
ORDER BY column ASC/DESC  
LIMIT num_limit OFFSET num_offset;  

LIMIT and OFFSET are generally applied last.  

Exercise 4 — Tasks  
List all directors of Pixar movies (alphabetically), without duplicates  
List the last four Pixar movies released (ordered from most recent to least)  
List the first five Pixar movies sorted alphabetically  
List the next five Pixar movies sorted alphabetically  

### Ch.4 Screenshot

![Chapter 4 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.4Complete.png)

## Chapter 5: Review Simple SELECT Queries 

### Ch.5 Guidance Notes

Example:  
SELECT column, another_column, ...  
FROM mytable  
WHERE conditions(s)  
ORDER BY column ASC/DESC  
LIMIT num_limit OFFSET num_offset;  

Review 1 — Tasks  
List all the Canadian cities and their populations  
Order all the cities in the United States by their latitude from north to south  
List all the cities west of Chicago, ordered from west to east  
List the two largest cities in Mexico (by population)  
List the third and fourth largest cities (by population) in the United States and their population  


### Ch.5 Screenshot

![Chapter 5 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.5Complete.png)

## Chapter 6: Multi-table queries with JOINS

### Ch.6 Guidance Notes

Data Normalization:  
useful to minimize duplicate data in a single table and allows DB to grow independently of each other  
Need a query that can combine all data and pull out exactly the info we need  

Multi-table queries with JOINs :  
tables that share info need to have a *primary key* that identified the entity uniquely across the DV  
One common primary key type is an auto-incrementing integer  
Using **JOIN** clause in a query can combine row data across two separate tables.  
The first of the JOINs we'll talk about is **INNER JOIN** 

Example:  
SELECT column, another_table_column, …  
FROM mytable  
INNER JOIN another_table  
    ON mytable.id = another_table.id  
WHERE condition(s)  
ORDER BY column, … ASC/DESC  
LIMIT num_limit OFFSET num_offset;  

The **INNER JOIN** is process that matches row from first to second table, which have the same key (defined by **ON** constraint) to create a result row with combined columns.  
Then other clauses we've learned can be applied.  

Exercise 6 — Tasks  
Find the domestic and international sales for each movie  
Show the sales numbers for each movie that did better internationally rather than domestically  
List all the movies by their ratings in descending order  

### Ch.6 Screenshot

![Chapter 6 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.6Complete.png)

## Chapter 13: Inserting Rows 

### Ch.13 Guidance Notes

Time to learn a bit about SQL schemas and how to add new data.  

What is a Schema?  
The Schema is what describes the structure of each table and the datatypes that each column of the table can contain  

The fixed structure is what allows a database to be efficient, and consistent.

Inserting New Data:

To insert data into the database you use **INSERT** statement.  
This declares which table to write into, the columns of data that are being filled and one or more rows of data to insert.  
You can insert multiple rows at a time by just listing them sequentially.  

Example:  
INSERT INTO mytable  
VALUES (value_or_expression, another, ...),  
       (value_or_expression_2, another, ...),  
       ...;  

In some cases, if you have incomplete data and the table contains columns that can store default values, you can insert rows with only the olumns of data you have by specifying them.  

Example:  
INSERT INTO mytable  
(column, another_column, ...)  
VALUES (value_or_expression, another, ...),  
       (value_or_expression_2, another, ...),
       ...;

in those cases the values need to match the number of columns specified.  
inserting values this way has the benefit of being forward compatible  

You can also use mathematical and string expressions with the values that you're inserting  
this can be useful to ensure that all data inserted is formatted a certain way  

Example:  
INSERT INTO boxoffice
(movie_id, rating, sales_in_millions)
VALUES (1, 9.9, 283742034/1000000);

Exercise 13 — Tasks  
Add the studio's new production, Toy Story 4 to the list of movies (you can use any director)  
Toy Story 4 has been released to critical acclaim! It had a rating of 8.7, and made 340 million domestically and 270 million internationally. Add the record to the BoxOffice table.  

### Ch.13 Screenshot

![Chapter 13 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.13Complete.png)

## Chapter 14: Updating Rows

### Ch.14 Guidance Notes

Using the **UPDATE** statement you can update a row.  
Similar to **INSERT** you have to specify exactly which table, column, and row to update.  
And the data you are updating with must match the existing data.

Example:  
UPDATE mytable  
SET column = value_or_expression,  
    other_column = another_value_or_expression,  
    ...  
WHERE condition;

The statement works by taking multiple column/value pairs and applying those changes to each and every row that satisfies the constraint in the **WHERE** clause.  

Taking Care:  
if you leave out the **WHERE** clause you'll update all the rows which is rarely what you want.  
So write the constraint first then test it in a SELECT query to make sure you're updating the correct rows.  

Exercise 14 — Tasks  
The director for A Bug's Life is incorrect, it was actually directed by John Lasseter  
The year that Toy Story 2 was released is incorrect, it was actually released in 1999  
Both the title and director for Toy Story 8 is incorrect! The title should be "Toy Story 3" and it was directed by Lee Unkrich  

### Ch.14 Screenshot

![Chapter 14 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.14Complete.png)

## Chapter 15: Deleting Rows

### Ch.15 Guidance Notes

To delete data from a database you can use the **DELETE** statement, specifying a constraint with the **WHERE** clause.

Example:  
DELETE FROM mytable  
WHERE condition;  

Exercise 15 — Tasks  
This database is getting too big, lets remove all movies that were released before 2005.  
Andrew Stanton has also left the studio, so please remove all movies directed by him.  

### Ch.15 Screenshot

![Chapter 15 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.15Complete.png)

## Chapter 16: Creating Tables

### Ch.16 Guidance Notes

You can create a new Database table using the **CREATE TABLE** statement  

Example:  
CREATE TABLE IF NOT EXISTS mytable (  
    column Datatype TableConstraints DEFAULT default_value,  
    another_column Datatype TableConstraints DEFAULT default_value,  
    ...  
);

The structure of the new table is defined by its *table schema*  
each column has:  
a name and the type of data allowed within the column  
an optional table constraint on values being inserted,  
as well as an optional default value  

If there already exists a table with the same name, SQL implementation will throw an error.  
to skip the creating of a table it it already exists you can throwth **IF NOT EXISTS** clause  

Table Data Types:  

|Data Type|Description|
|:--------|:----------|
|INTEGER, BOOLEAN| The integer datatypes can store whole integer values like the count of a number or an age. In some implementations, the boolean value is just represented as an integer value of just 0 or 1.|
|FLOAT, DOUBLE, REAL| The floating point datatypes can store more precise numerical data like measurements or fractional values. Different types can be used depending on the floating point precision required for that value.|
|CHARACTER(num_chars), VARCHAR(num_chars), TEXT|The text based datatypes can store strings and text in all sorts of locales. The distinction between the various types generally amount to underlaying efficiency of the database when working with these columns. Both the CHARACTER and VARCHAR (variable character) types are specified with the max number of characters that they can store (longer values may be truncated), so can be more efficient to store and query with big tables.|
|DATE, DATETIME| SQL can also store date and time stamps to keep track of time series and event data. They can be tricky to work with especially when manipulating data across timezones.|
|BLOB|Finally, SQL can store binary data in blobs right in the database. These values are often opaque to the database, so you usually have to store them with the right metadata to requery them|


Table Constraints:  
Each column can have additional table constraints to limit what values can be inserted into that column.

|Constraint|Description|
|:---------|:----------|
|PRIMARY KEY|This means that the values in this column are unique, and each value can be used to identify a single row in this table.|
|AUTOINCREMENT|For integer values, this means that the value is automatically filled in and incremented with each row insertion. Not supported in all databases.|
|UNIQUE|This means that the values in this column have to be unique, so you can't insert another row with the same value in this column as another row in the table. Differs from the `PRIMARY KEY` in that it doesn't have to be a key for a row in the table.|
|NOT NULL|This means that the inserted value can not be `NULL`.|
|CHECK (expression)|This allows you to run a more complex expression to test whether the values inserted are valid. For example, you can check that values are positive, or greater than a specific size, or start with a certain prefix, etc.|
|FOREIGN KEY|This is a consistency check which ensures that each value in this column corresponds to another value in a column in another table. For example, if there are two tables, one listing all Employees by ID, and another listing their payroll information, the `FOREIGN KEY` can ensure that every row in the payroll table corresponds to a valid employee in the master Employee list.|

Example:  
CREATE TABLE movies (
  id INTEGER PRIMARY KEY,
  title TEXT,
  director TEXT,
  year INTEGER,
  length_minutes INTEGER
);


Exercise 16 — Tasks  
Create a new table named Database with the following columns:  
– Name A string (text) describing the name of the database  
– Version A number (floating point) of the latest version of this database  
– Download_count An integer count of the number of times this database was downloaded  
This table has no constraints.  

### Ch.16 Screenshot

![Chapter 16 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.16Complete.png)

## Chapter 17: Altering Tables

### Ch.17 Guidance Notes

You can update your tables and your database schema by using the **ALTER TABLE** statement to add, remove, or modify columns and table constraints

Adding Columns:  
Syntax for adding new column requires you to specify the data type along with any potential constraints and default values to be applied to both existing and new rows. 

Example:  
ALTER TABLE mytable  
ADD column DataType OptionalTableConstraint  
  DEFAULT default_value;  

Removing Columns:  
Dropping columns is just as easy as specifying new ones, but not all DB's support this feature.  
In those cases you create a new table and migrate the data you want to keep over.  

Example:  
ALTER TABLE mytable  
DROP column_to_be_deleted;  

Renaming the Table:  
If you need to rename the table itself, you can do that by using the **RENAME TO** clause.

Example:  
ALTER TABLE mytable  
RENAME TO new_table_name;  

Exercise 17 — Tasks  
Add a column named Aspect_ratio with a FLOAT data type to store the aspect-ratio each movie was released in.  
Add another column named Language with a TEXT data type to store the language that the movie was released in. Ensure that the default for this language is English.  

### Ch.17 Screenshot

![Chapter 17 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.17Complete.png)

## Chapter 18: Dropping Tables

### Ch.18 Guidance Notes

To remove an entire table you can use the **DROP TABLE** statement, it also removes the Schema from the database entirely.  

Example:  
DROP TABLE IF EXISTS mytable; 

Like the **CREATE TABLE** statement, the database can throw an error if the table doesn't exist, to skip this error use the **IF EXISTS** clause  

If you have another table that is dependent on columns in table you are removing (such as a **FOREIGN KEY** dependency) then you'll have to update all dependent tables first or those remove those dependent rows/tables, 

Exercise 18 — Tasks  
We've sadly reached the end of our lessons, lets clean up by removing the Movies table  
And drop the BoxOffice table as well  

### Ch.18 Screenshot

![Chapter 18 Exercise Complete](/code-401/prep-work-notes/SQLimg/Ch.18Complete.png)
