
# Ansible Best Practices

Here you can read about the recommeded best practices when working with ansible to deploy our software.

Here are the best practices by categories:

1. Security
    - setup ssl encryption for windows hosts
    - using keys to remote login (instead of password)
    - security considirations when allowing sudo ALL:NOPASSWD
    - storing secrets
2. Deployments
    - increase performance
    - use ansible as source of truth
3. Backups
    - backup periodically
4. Modularity
    - splitting roles and inventories
    - extract parameters from tasks
