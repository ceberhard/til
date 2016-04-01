## How to select a random set of rows from Oracle or SQL Server

Solution for selecting a random set of 100 rows from Oracle:
```sql
SELECT    *
FROM    
  (SELECT    t.*
  FROM       table t
  ORDER BY   dbms_random.value)
WHERE rownum <= 100
```

Solution for selecting a random set of 100 rows from SQL Server:
```sql
SELECT    TOP 100 t.*
FROM      table t
ORDER BY  NEWID();
```
In SQL Server, you can also sample percentages easily:
```sql
SELECT    TOP 0.1 PERCENT t.*
FROM      table t
ORDER BY  NEWID();
```

### References:
http://stackoverflow.com/questions/733652/select-a-random-sample-of-results-from-a-query-result
https://msdn.microsoft.com/en-us/library/cc441928.aspx
