
# Creating Simple Ansible Project

project folder structure:

```
my-deployment-project
├── inventories (1)
│   ├── dev
│   │   ├── group_vars
│   │   │   └── all.yml
│   │   └── hosts.ini (2)
│   └── prod
│       ├── group_vars
│       │   └── all.yml
│       └── hosts.ini
├── roles (3)
│   └── my_custom_logic
│       └── tasks
│           └── main.yml
├── requirements.yml (4)
└── site.yml (5)
```

1. inventories folder: \
contains the folder per environment.\
useful if you have multiple \ complex envs.

2. hosts.ini file: \
the \"main\" file in the inventory.\
contains the list of hosts, the connection method, and the credentials to the hosts.\
also contains the mapping of application -> host, listing what application needs to be installed on each host.

3. roles folder: \
the place to have custom logic.
it can be logger config, monitoring agent, etc.

4. requirements.yml file: \
yml file containing an array of dependencies. \
will contain the list of the dependencies and where to fetch them from.
__usage__: _ansible-galaxy install -r FILENAME_

5. site.yml file: \
the main file of the project. \
used to link all the pieces. \
this file will specify what application whould be installed on what machine, \
order of execution, \
special pre \ post task step to perform, etc.

