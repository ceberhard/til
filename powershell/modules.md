## PowerShell Modules

*Based on PowerShell 7.1 Documentation*

If you want to create common module functions to access from other `.ps1` script files, you can create them in PowerShell module files: `.psm1`.

For example, `env.psm1`:
```PowerShell
$global:envVars = @{}

Function GetEnvValue($key) {
    $val = $global:envVars[$key]
    if ([string]::IsNullOrWhiteSpace($val)) {
        throw [System.NullReferenceException] "$key env variable not set..."
    }
    return $val
}

Function LoadEnvValues($envFilePath) {
    if (!(Test-Path $envFilePath)) {
        throw [System.IO.FileNotFoundException] "$envFilePath not found..."
    }

    $global:envVars = @{}
    $sr = New-Object System.IO.StreamReader($envFilePath)
    while ($null -ne ($current = $sr.ReadLine())) {
        $vars = $current -split '='
        $global:envVars = $envVars + @{$vars[0] = $vars[1]}
    }
    Write-Host "Loaded $envFilePath variables..."
}

LoadEnvValues(".\.env")
```

Can then be referenced in other `.ps1` files via:
```PowerShell
Import-Module .\env.psm1 -Force

$ServerName = GetEnvValue("TargetServerName")
```

### References:

- https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_modules
- https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-7.1#modules

