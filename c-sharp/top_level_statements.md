## Top-Level Statements

__*Available in C# 9.0 (.NET 5.0)*__

Top-level statements allow you to write code without the usual trappings of a normal C# file (namespace, class-designation, etc.). This creates a "script-like" experience for C#, and is typically used for the `Program.cs` class of a console application.

```C#
using System.Text;
StringBuilder builder = new();
builder.AppendLine("Hello ");
builder.AppendLine("World!");
Console.WriteLine(builder.ToString());
```

### References:

https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/proposals/csharp-9.0/top-level-statements
