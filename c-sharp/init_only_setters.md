## Init Only Setters

__*Available in C# 9.0 (.NET 5.0)*__

The `init` property syntax provides for a consistent way to initialize members of an object. After initializing the object, the property becomes immutable.

```C#
public struct WeatherObservation {
    public DateTime RecordedAt { get; init; }
    public decimal TemperatureInCelsius { get; init; }
    public decimal PressureInMillibars { get; init; }
}
```

### References

https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/proposals/csharp-9.0/init
