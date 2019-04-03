
# Prepare Machine For Ansible

## Target Machine

Target machine is a machine to which we want on which we want to install software

The following resources describe how to configure a machine (physical \ virtual) before deploying software to it - using ansible.

* for windows machines - [click here](./windows)
* for mac os machines - [click here](./mac-os)
* for linux machines - [click here](./linux)

## Executor Machine

Executor machine is the machine from which we run ansible deployment.

Linux and Mac OS are supported out of the box. \
Using windows to run ansible is more tricky. \
Windows subsystem works, but if it is not available - installation [gets technical](./windows/Ansible-On-Windows.md).

When using winrm - you will need to install:
`pip install pywinrm`
