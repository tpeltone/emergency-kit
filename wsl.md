# WSL

## Useful links

[Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install)

[Set Linux Distro Version to WSL 1 or WSL 2 in Windows 10](https://winaero.com/set-linux-distro-version-to-wsl-1-or-wsl-2-in-windows-10/)

### Useful Commands

```powershell

# Open Powershell ad administrator

# List available Distros
wsl --list --online

# Install WSL
wsl --install

# Install specifik distro
wsl --install -d <DistroName>

# Find WSL Versions for Installed Linux Distros
PS C:\Users\alpha> wsl --list --verbose
  NAME                   STATE           VERSION
* Ubuntu-20.04           Running         1
  docker-desktop         Stopped         2
  docker-desktop-data    Stopped         2


# Set Linux Distro Version to WSL 1 or WSL 2 for new instances

# WSL 2 as default version for new instances
wsl --set-default-version 2

# WSL 1 as default version for new instances
wsl --set-default-version 1


# To Set Linux Distro Version to WSL 1 or WSL 2 in Windows 10

# WSL 2 as the distro version for the specific instance
wsl --set-version Ubuntu-20.04 2

# WSL 1 as the distro version for the specific instance
wsl --set-version Ubuntu-20.04 1


```
