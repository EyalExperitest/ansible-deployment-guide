
# Local Example

## Assumptions

- ***postgres*** is installed on the machine, on port ***5432***
- postgres user exists
- the dbs 'cloudserver' and 'reporter' ***exists*** and ***accessible*** by postgres user
- ***ports*** 80, 443, 8080-8086, 51234-51238 are free on the target machine

## Limitations

- NV cannot be installed on the same machine (os support matrix)
- it doens't make sense to install SeleniumAgent on the same instance

## Step to install

- install ansible on control machine

- make sure node machine is accessible to controller

- create project folder - you can copy the current folder

- edit the inventory file to match the ip and username, password for the machine

- install ansible dependencies \
`ansible-galaxy install -r requirements.yml --force`

- run the deployment \
`ansible-playbook site.yml -i inventories/local/hosts.ini`
