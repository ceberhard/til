## Record Data Types

__*Available in C# 9.0 (.NET 5.0)*__

Used for encapsulating data elements similar to a class or a struct. Primarily used for immutable data entities.

Create immutable properties:

```C#
public record Person(string FirstName, string LastName);
```

or

```C#
public record Person {
    public string FirstName { get; init; }
    public string LastName { get; init; }
}
```

Built-in formatting for display:

```C#
Person person = new("Nancy", "Davolio");
Console.WriteLine(person);
// output: Person { FirstName = Nancy, LastName = Davolio }
```

### Value equality

Two record variables are equal if all types match and all property/field values match. This is different from other reference type variables where equality means they refer to the same object

### References

https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/record

