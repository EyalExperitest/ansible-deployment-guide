
# Prepare Linux Control Machine - Without internet

## Requirements:

- Make sure python2.7, pip and unzip tools is already installed on Linux and Mac control machines

- On any machine which has internet connection, download offline ansible installation from below url <br>
https://devops-artifacts.experitest.com/ansible/onpremise/experitest-ansible-offline-installation.zip

- Copy and unzip the downloaded experitest-ansible-offline-installation.zip file to ansible master (control machine) and go to the extracted folder "experitest-ansible-offline-installation"


## Install Ansible:

* Go to the downloaded extracted folder and install ansible (depending on distribution) using below commands.


```sh
# using pip
pip install ./pip-offline/ansible-offline/*

# centos / rhel
sudo yum localinstall -y ./yum-offline/*/*
sudo pip install ./pip-offline/pywinrm-offline/*

# ubuntu
pip install ./pip-offline/ansible-offline/*
pip install ./pip-offline/pywinrm-offline/*

# debian
pip install ./pip-offline/ansible-offline/*
pip install ./pip-offline/pywinrm-offline/*

# fedora
pip install ./pip-offline/ansible-offline/*
pip install ./pip-offline/pywinrm-offline/*

# mac
pip install ./pip-offline/ansible-offline/*
pip install ./pip-offline/pywinrm-offline/*
```

* check the ansible version <br>
`ansible --version`

* [make sure git is installed on the machine](../../appendix/install-git.md)

* [genereate \ add ssh key](../SSH.md#passwordless-login)
* [add hosts to known_hosts file](../SSH.md#known-hosts)


* connecting to ***windows*** node machines requires
```sh
pip install ./pip-offline/pywinrm-offline/*
```

## Install Roles to Ansible Project:

* From machine which has internet connection, download ansible-deployment-guide repository.
```
git clone https://github.com/ExperitestOfficial/ansible-deployment-guide.git -b onpremise-deployment-project-example
```

* Go to roles folder under onpremise-deployment-project-example
```
cd ./ansible-deployment-guide/onpremise-deploy-without-internet/onpremise-deployment-project-example/roles
```

* Download all the following Experitest Official roles to the roles folder (change to required version branch):

```
git clone https://github.com/ExperitestOfficial/ansible-role-cloud-server.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-app-signer.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-file-storage.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-regional-proxy.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-cloud-agent.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-reporter.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-cloud-nv.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-selenium-agent.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-cloud-emulator-host.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-audioservice-cloudagent.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-java8.git -b feature/onpremise-deploy
git clone https://github.com/ExperitestOfficial/ansible-role-disk-space-validator.git
```

* Copy the onpremise-deployment-project-example folder to ansible control.
* Update the hosts.ini file (add server ip) and go to onpremise-deployment-project-example folder and check the connections with the target machines.

```
cd onpremise-deployment-project-example
ansible-playbook -i inventories/prod/hosts.ini check-connection.yml
```