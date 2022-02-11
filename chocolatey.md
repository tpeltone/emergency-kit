# Chocolatey

## Useful links

[Choco Commands](https://docs.chocolatey.org/en-us/choco/commands/)

### Useful Commands

 ```powershell
 # List locally installed packages
 choco list --local-only

#
 choco list -li
 choco list -lai
 choco list --page=0 --page-size=25


# Check outdated packages
choco outdated
```

### Install/uninstall packages

```powershell
# Install
choco install python3

# Uninstall
choco uninstall python3
```
