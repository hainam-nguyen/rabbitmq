# Rabbitmq installation on Debian/Ubuntu

-------------------------------------------------------------------------------------------------------------
## How to use:

```
ansible-playbook -i hosts rabbitmq.yaml
```

-------------------------------------------------------------------------------------------------------------
# Usage

**rabbitmq.yaml**
  > contains debian distribution and version of rabbitmq-server.

**handlers**
  - main.yaml
    > contains restart rabbitmq-server function.

**tasks**
  - main.yaml
    > include specific setup file for specific os_family

  - setup_Debian.yaml
    > contains steps for rabbitmq-server installation on a Debian server.

**vars**
  - main.yaml
    > include variables for related installation information.

**templates**
  - erlang
    > configures apt to install erlang-* packages from Bintray and not standard Debian or Ubuntu repository:

  - rabbitmq.conf
    > contains basic configuration of rabbitmq-server (recommened for version later than 3.7.7)
    Currently, enable listeners.tcp.default = 5672 and management.listener.port = 15672

  - enabled_plugins
    > contains plugins will be enabled for rabbitmq-server
    Currently, enable [rabbitmq_management]
