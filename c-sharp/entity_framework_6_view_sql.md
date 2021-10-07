## How to Get Entity Franework 6 to Show the Executing SQL

To display the sql which being executed for a specific DbContext, you simply need to add the following line within the using statement:

``` C#
using (var context = new MyDataContext())
{
    context.Database.Log = s => System.Diagnostics.Debug.WriteLine(s);
}
```

### References:

http://stackoverflow.com/questions/1412863/how-do-i-view-the-sql-generated-by-the-entity-framework

