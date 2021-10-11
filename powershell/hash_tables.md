## PowerShell Hashtables

Hashtables are powershell dictionaries, where objects are stored in a collection using corresponding keys. It's a basic key/value store.

Creating an empty Powershell hashtable:

```PowerShell
$myHashtable = @{}
```

Creating a PowerShell hashtable with values:

```PowerShell
$myHashtable = @{ Index = 1; Color = "Green"; Time = "Now" }
```

To access values in a hashtable, use square brackets and the item key:

```PowerShell
$myHashtable["Index"]
```

To add an item to a hashtable, just set the value via the new key. If the item does not already exist, then the item is added. Also, there is an Add method and you can use the addtion operator (`+`).

```PowerShell
# Three ways to add to a hashtable
$myHashtable.NewValue = "myNewValue"

$myHashtable.Add("NewValue", "myNewValue")

$myHashtable = $myHashtable + @{NewValie = "myNewValue"}
```

To remove an item from a hashtable, use the `remove` method:

```PowerShell
$myHashtable.Remove("NewValue")
```

You can iterate a hashtable either via the `keys` or `values` properties:

```PowerShell
foreach($key in $myHashtable.keys) {
    $val = $myHashtable[$key]
}

foreach($val in $myHashtable.values) {
    # Do something with each value
}
```

You can also iterate using `GetEnumerator()`:

```PowerShell
$myHashtable.GetEnumerator() | ForEach-Object{
    $key = $_.key
    $val = $_.value
}
```






### References:

- https://docs.microsoft.com/en-us/powershell/scripting/learn/deep-dives/everything-about-hashtable?view=powershell-7.1

