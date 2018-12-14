# Rabbitmq provisioning on Debian/Ubuntu

-------------------------------------------------------------------------------------------------------------
## How to use:

```
ansible-playbook -i hosts rabbitmq.yaml
```

-------------------------------------------------------------------------------------------------------------
# Usage

**rabbitmq.yaml**
  > now has more options, can be defined with "task_name":
       - install (need to define "debian_distribution" and "rabbitmq_version" too)
       - add_user
       - backup

**handlers**
  - main.yaml
    > contains restart rabbitmq-server function.

**tasks**
  - main.yaml
    > include specific setup file for specific os_family

  - install_rabbitmq_Debian.yaml
    > contains steps for rabbitmq-server installation on a Debian server.

  - add_user_rabbitmq_Debian.yaml
    > contains steps for adding new users to rabbitmq-server, user info are kept in var/list_of_users.yaml

  - backup_rabbitmq_Debian.yaml (only structure)
    > contains steps for backingup Rabbitmq


**vars**
  - installation_info.yaml
    > include variables for related installation information.

  - list_of_users.yaml
    > contains users information to be added in rabbitmq-server

**templates**
  - erlang
    > configures apt to install erlang-* packages from Bintray and not standard Debian or Ubuntu repository:

  - rabbitmq.conf
    > contains basic configuration of rabbitmq-server (recommened for version later than 3.7.7)
    Currently, enable listeners.tcp.default = 5672 and management.listener.port = 15672

  - enabled_plugins
    > contains plugins will be enabled for rabbitmq-server
    Currently, enable [rabbitmq_management]
