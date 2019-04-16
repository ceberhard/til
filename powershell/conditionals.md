## How to Use Conditionals in PowerShell
```PowerShell
$base = $PSScriptRoot + "\..";

$authpath = $base + '\.auth';
if (Test-Path $authpath) {
    Remove-Item $authpath;
    Write-Output "Removed .auth file";
    Write-Output "----------------------------------";
}

$envpath = $base + '\.env';
if (!(Test-Path $envpath)) {
    $deploypath = $base + "\config\env.deploy";
    Copy-Item $deploypath $envpath;
    Write-Output "Created .env file";
    Write-Output "----------------------------------";
}
```
Both positive and negated conditionals shown above.

### References:
https://stackoverflow.com/questions/8095638/how-do-i-negate-a-condition-in-powershell
