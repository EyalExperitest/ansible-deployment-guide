
# SSH Login

## Login to remote machine without password

Perform the following step to ensure connectivity from the executor to the target machine.

* create ssh key - `ssh-keygen`\
  follow the step in the cli

* copy the ssh public key - `ssh-copy-id username@machine-ip`\
  enter credentials of the target machine and confirm

## Elevating permissions without password

Login is not enough, we also (need in some cases) to perform commands as sudo.

Perform the following command in the target machine to avoid password request when elevating permissions (becoming sudo)

* open sudoers file - `sudo visudo`
* add the user to no password - in the end of the file\
  `username ALL=(ALL) NOPASSWD:ALL`

NOTE:\
If NOPASSWD is not allowed (for security reasons), the alternative is adding the following variable to the ansible inventory file:

```
[mac-instance]
1.2.3.4

[mac-instance:vars]
ansible_user=myusername
ansible_become_user=myusername  <---
ansible_password=123
ansible_become_password=123     <---
```
