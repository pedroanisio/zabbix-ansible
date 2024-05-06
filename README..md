# Zabbix Ansible

```text
ansible-project/
├── ansible.cfg              # Main configuration file for Ansible
├── inventory                # Inventory directory
│   ├── hosts                # Default inventory file, can be YAML or INI
│   ├── production.yml       # Production environment inventory
│   └── staging.yml          # Staging environment inventory
├── playbooks                # Directory containing all your playbooks
│   ├── site.yml             # Main playbook that includes others
│   ├── webservers.yml       # Playbook for webserver setup
│   └── databases.yml        # Playbook for database setup
├── roles                    # Directory for Ansible roles
│   ├── common               # Role for common tasks across all nodes
│   │   ├── tasks            # Tasks subdirectory
│   │   │   └── main.yml     # Main list of tasks to be executed
│   │   ├── handlers         # Handlers subdirectory
│   │   │   └── main.yml     # Handlers for service restarts, etc.
│   │   ├── defaults         # Default variables
│   │   │   └── main.yml     # Default variables for the role
│   │   ├── vars             # Other variables
│   │   │   └── main.yml     # Main variables file for the role
│   │   ├── files            # Files for deployment
│   │   ├── templates        # Jinja2 templates
│   │   │   └── ntp.conf.j2  # Sample template file
│   │   └── meta             # Role dependencies
│   │       └── main.yml     # Metadata about role, including dependencies
│   └── webserver            # Role specific to webserver setup
│       ├── ...
├── group_vars               # Directory for group-specific variables
│   ├── group1.yml           # Variables for 'group1'
│   └── all.yml              # Variables that apply to all groups
└── host_vars                # Directory for host-specific variables
    ├── host1.yml            # Variables specific to 'host1'
    └── host2.yml            # Variables specific to 'host2'
```

## Commands

```shell
ansible-playbook -i inventories/hosts.yaml playbooks/deploy_zabbix_agent2.yaml
```

###  Fix role into playbooks

```shell
cd playbooks
ln -s ../roles roles
```
