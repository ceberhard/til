## Variable Scope in PowerShell

*Based on PowerShell 7.1 Documentation*

Basic Rules:
- Scopes may nest
- Items are visible in the scope in which it was created and any child scopes
- __An item created in a scope can only be changed in the scope in which it was created__

*If you create an item that shares a name with an item in a different scope, the original item might be hidden, but it is not overridden or changed*

Supported Scopes:
- Global: root parent scope of the session
- Local: current scope
- Script: scope created when a script file runs

Inheritance:
The child scope does not inherit the variables, aliases, and functions from the parent scope. The child can view and change the the items by explicitly specifying the parent scope, but the items are not a part of the child scope.

Scope Modfiers:
- `global:` - Specifies __Global__ scope
- `local:` - Specifies __Local__ scope
- `script:` - Specifies __Script__ scope
- `private:` - Limits visibility to the current scope

Using Scope Modifiers:
```PowerShell
$global:envVars = @{}
```
```PowerShell
$script:a = "one"
```
```PowerShell
# Private Module Function
Function private:LoadEnvValues($envFilePath) {
    # Do something ...
}
```

### References:
- https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_scopes

