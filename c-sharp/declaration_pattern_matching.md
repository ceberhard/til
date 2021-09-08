## Assign a new variable when matching a declaration type pattern

```C#
// Notice that the "message" variable is assigned as part of the "is" type-match condition
object greeting = "Hello, World!";
if (greeting is string message) {
    Console.WriteLine(message.ToLower());
    // output: hello, world!
}
```

### References:

https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/patterns#declaration-and-type-patterns
