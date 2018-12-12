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

**defaults**
  - main.yaml
    > contains default_tcp_listen_port and web_management_listen_port variables

**handlers**
  - main.yaml
    > contains restart rabbitmq-server function.

**tasks**
  - main.yaml
    > include specific setup file for specific os_family

  - setup_Debian.yaml
    > contains steps for rabbitmq-server installation on a Debian server.

**templates**
  - erlang
    > configures apt to install erlang-* packages from Bintray and not standard Debian or Ubuntu repository:

  - rabbitmq.conf
    > contains basic configuration of rabbitmq-server (recommened for version later than 3.7.7)

  - enabled_plugins
    > contains plugins will be enabled for rabbitmq-server
