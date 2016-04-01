## How to Determine the Folder Where a Script is Executing
To find the folder where a powershell script is being executed from:
```PowerShell
$scriptpath = split-path -parent $MyInvocation.MyCommand.Definition
echo $scriptpath
```
Uses the "split-path" cmdlet with the -parent parameter to return the directory path.

### References:
http://stackoverflow.com/questions/5466329/whats-the-best-way-to-determine-the-location-of-the-current-powershell-script
