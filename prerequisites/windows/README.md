
# Prepare Windows Machine

## Prerequisites
* powershell 5.1 is installed - [see file](./Upgrade-PowerShell.ps1)

## Remote Login
* winrm is installed and firewall ports are open - [see file](./Install-WinRM.ps1)

## Connecting from mac to windows machine (winrm)
- pip install "pywinrm"
- *export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES*

<br>

### Additional Configuration
See the official ansible documentation [for further instructions](https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html).