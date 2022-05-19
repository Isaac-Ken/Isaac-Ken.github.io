
[PORTSWIGGER SQL injection cheat sheet] https://portswigger.net/web-security/sql-injection/cheat-sheet

This SQL injection cheat sheet contains examples of useful syntax that you can use to perform a variety of tasks that often arise when performing SQL injection attacks.

String concatenation
--------------------

You can concatenate together multiple strings to make a single string.

| Oracle  `'foo'||'bar'` |
| Microsoft  `'foo'+'bar'` |
| PostgreSQL  `'foo'||'bar'` |
| MySQL  `'foo' 'bar'` 
        `CONCAT('foo','bar')` |

Substring
---------

You can extract part of a string, from a specified offset with a specified length. Note that the offset index is 1-based. Each of the following expressions will return the string `ba`.

| Oracle  `SUBSTR('foobar', 4, 2)` |
| Microsoft  `SUBSTRING('foobar', 4, 2)` |
| PostgreSQL  `SUBSTRING('foobar', 4, 2)` |
| MySQL  `SUBSTRING('foobar', 4, 2)` |

Comments
--------

You can use comments to truncate a query and remove the portion of the original query that follows your input.

| Oracle  `--comment\` |
| Microsoft  `--comment\
/*comment*/` |
| PostgreSQL  `--comment\
/*comment*/` |
| MySQL  `#comment`\
`-- comment` 
`/*comment*/` |

Database version
----------------

You can query the database to determine its type and version. This information is useful when formulating more complicated attacks.

| Oracle | `SELECT banner FROM v$version\
SELECT version FROM v$instance\
` |
| Microsoft | `SELECT @@version` |
| PostgreSQL | `SELECT version()` |
| MySQL | `SELECT @@version` |

Database contents
-----------------

You can list the tables that exist in the database, and the columns that those tables contain.

| Oracle | `SELECT * FROM all_tables\
SELECT * FROM all_tab_columns WHERE table_name = 'TABLE-NAME-HERE'` |
| Microsoft | `SELECT * FROM information_schema.tables\
SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE'\
` |
| PostgreSQL | `SELECT * FROM information_schema.tables\
SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE'\
` |
| MySQL | `SELECT * FROM information_schema.tables\
SELECT * FROM information_schema.columns WHERE table_name = 'TABLE-NAME-HERE'` |
