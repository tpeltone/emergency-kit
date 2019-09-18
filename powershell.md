# Powershell

## Useful links

[Powershell One-Liner: Creating and Modyfing and environment variable](https://www.itprotoday.com/powershell/powershell-one-liner-creating-and-modifying-environment-variable)

### Environment Variables

 ```powershell
# set environment
Set-Location Env:
Get-ChildItem

# temporary environment variables
$env:MyTestVariable = "My temporary test variable."

# permanent enironment variables
[Environment]::SetEnvironmentVariable("TestVariableName", "My Value", "<option>")

# user level
[Environment]::SetEnvironmentVariable("TestVariableName", "My Value", "User")

# machine level
[Environment]::SetEnvironmentVariable("TestVariableName", "My Value", "Machine")
```
