## Updated Syntax for Switch Statement for Pattern Matching

```C#
public static decimal GetGroupTicketPrice(int visitorCount) => visitorCount switch {
    1 => 12.0m,
    2 => 20.0m,
    3 => 27.0m,
    4 => 32.0m,
    0 => 0.0m,
    _ => throw new ArgumentException($"Not supported number of visitors: {visitorCount}", nameof(visitorCount)),
};
```

### References:

https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/patterns#constant-pattern