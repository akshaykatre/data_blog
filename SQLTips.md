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


## Converting from sqlite3 to sql db 

We need to perform a dump of the data, and this is done by literally creating
the SQL scripts required and then running the SQL scripts on the database. 

Open the sqlite database with: ``` sqlite3 <nameofdb>.sqlite3```
```
.output alloutput.sql 
.dump 
```

You may have to perform some small corrections to the SQL script, but essentially
the script is then all you need. 

With ```sqlcmd``` you can now create your tables/ databases as described in the script
```
sqlcmd -S localhost -i alloutput.sql
```
