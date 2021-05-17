### Creating a random sample in T-SQL 

To select random rows from an SQL table, try the following: 

```
SELECT TOP 1 column FROM table 
ORDER BY NEWID()
```
Note: there is no option to use a 'seed', therefore, it is 
hard to reproduce the same sample.

### Searching for a column across all tables on the server

```
EXECUTE sp_MSForEachDB 
        'USE ?; 
        SELECT *, 
        FROM information_schema.columns
        WHERE column_name = <search_col_name>'
```

