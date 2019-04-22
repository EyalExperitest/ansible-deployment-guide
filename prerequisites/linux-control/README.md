
# Prepare Linux Control Machine

* install ansible (depending on distribution) \
[see additional explanation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-the-control-machine)

```sh
# using pip
pip install ansible

# centos / rhel
sudo yum install ansible

# ubuntu
sudo apt-get update
sudo apt-get install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt-get install ansible

# debian
echo "deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main" >> /etc/apt/sources.list
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367
sudo apt-get update
sudo apt-get install ansible

# fedora
sudo dnf install ansible
```

* [genereate \ add ssh key](../SSH.md#passwordless-login)
* [add hosts to known_hosts file](../SSH.md#known-hosts)

* connecting to ***windows*** node machines requires
```sh
pip install pywinrm
```
