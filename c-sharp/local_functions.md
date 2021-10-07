## Local Functions

Private methods that can be nested in another member and can only called from within their member. Can be nested within:
- Methods
- Constructors
- Property accessors
- Event accessors
- Anonymous methods
- Lambda expressions
- Finalizers
- Other local functions
*As of C# 9.0 (.NET 5), local functions can be assigned attributes.*

```C#
private static string GetText(string path, string filename) {
    var reader = File.OpenText($"{AppendPathSeparator(path)}{filename}");
    var text = reader.ReadToEnd();
    return text;

    // Local function below
    string AppendPathSeparator(string filepath) {
        return filepath.EndsWith(@"\") ? filepath : filepath + @"\";
    }
}

```

### References:

https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/local-functions
