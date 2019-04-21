
# How to use WINRM with ssl

This guide will walk you through how to get winrm working with ssl.
After setting it, traffic between executor and remote machine will be encrypted.

## STEPS

1. create (self-signed) certificate: \
use [the following script](./create_self_signed.sh) to create self-signed certificate

2. copy the public key to the remote (windows) machine

3. import cert to windows machine \
use [the following script](./import-public-cert.ps1) to import the certificate.

4. refer to private key in ansible playbook \
change the inventory file accordingly:

FROM

```ini
[instance1]
1.2.3.4

[instance1:vars]
ansible_connection: winrm 

ansible_user: <username> 
ansible_password: <password> 
ansible_become_method: runas 

# insecure
ansible_winrm_server_cert_validation: ignore    
```


TO
```ini
[instance1]
1.2.3.4

[instance1:vars]
ansible_connection: winrm

ansible_user: <username>
ansible_password: <password>
ansible_become_method: runas

# add certificate to host / group vars
ansible_winrm_transport: certificate
ansible_winrm_cert_pem: path/to/public.pem
ansible_winrm_cert_key_pem: path/to/private.pem
```
