
[PORTSWIGGER SQL injection cheat sheet] https://portswigger.net/web-security/sql-injection/cheat-sheet

This SQL injection cheat sheet contains examples of useful syntax that you can use to perform a variety of tasks that often arise when performing SQL injection attacks.

String concatenation
--------------------

You can concatenate together multiple strings to make a single string.

| Oracle | `'foo'||'bar'` |
| Microsoft | `'foo'+'bar'` |
| PostgreSQL | `'foo'||'bar'` |
| MySQL | `'foo' 'bar'` [Note the space between the two strings]\
`CONCAT('foo','bar')` |
