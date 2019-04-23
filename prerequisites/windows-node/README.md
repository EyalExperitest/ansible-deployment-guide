
# Prepare Node - Windows Machine

## Prerequisites
* powershell 5.1 is installed - [see file](./Upgrade-PowerShell.ps1)

## Remote Login
* winrm is installed and firewall ports are open - [see file](./Install-WinRM.ps1)

## Connecting to domain connected windows machine
if the windows host to connect is associated with domain, you might not be able to connect to it.\
possible solution to this problem is the change the transform protocol to NTLM.

for further explanation visit [the following link](https://docs.ansible.com/ansible/latest/user_guide/windows_winrm.html#ntlm).

```ini
[instance1]
1.2.3.4

[instance1:vars]
ansible_connection=winrm 

# add domain to username 
ansible_user=<username>@<domain-name>
ansible_password=<password> 
ansible_become_method=runas 
ansible_winrm_server_cert_validation=ignore

# add this
ansible_winrm_transport=ntlm
```

<br>

### Credentials Rejected

If you get an error that the server has rejected you credentials, use the following command to print the username to use:

```ps1
$env:UserName
```

In some cases, using ___ansible_winrm_transport=basic___ is the only working login method.


### Additional Configuration
See the official ansible documentation [for further instructions](https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html).
