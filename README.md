<p><img src="https://raw.githubusercontent.com/grafana/agent/main/docs/sources/assets/logo_and_name.png" alt="gagent-logo" title="gagent" align="top" height=75 /></p>

*Grafana Agent is a telemetry collector for sending metrics, logs, and trace data to the opinionated Grafana observability stack*

### General informations

This Ansible role is designed to deploy and configure the Grafana Agent on target server(s).

**Table of Contents**

  - [Roles variables](#role-variables)
  - [Examples](#examples)
  - [Install and use this role](#install-and-use-this-role)

**References**

  - Grafana Agent : https://github.com/grafana/agent

### Role variables

| Name                              | Default                      | Description                                                      |
| :-------------------------------- | :--------------------------- | :--------------------------------------------------------------- |
| `grafana_agent_version`           | `0.31.3`                     | Defines the version of Grafana Agent to install                  |
| `grafana_agent_config_dir`        | `/etc/grafana-agent`         | Defines the Grafana Agent configuration directory                |
| `grafana_agent_config_path`       | `{{ grafana_agent_config_dir }}/config.yaml`| Defines the absolute path to the Grafana Agent configuration file |
| `grafana_agent_wal_dir`           | `/var/lib/grafana-agent`     | Defines the Grafana Agent WAL directory                          |
| `grafana_agent_custom_args`       | `[]`                         | Defines the extra arguments to pass to the Grafana Agent process when starting the service |
| `grafana_agent_custom_env`        | `[]`                         | Defines the extra environment variables to pass to the Grafana Agent process when starting the service |
| `grafana_agent_restart_on_upgrade`| `true`                       | If set to `true`, allow package manages to restart the Grafana Agent after a package upgrade |
| `grafana_agent_server_config`     | see [defaults](defaults/main.yml)| Defines the Grafana Agent server configuration               |
| `grafana_agent_server_http_address`| `127.0.0.1:9090`            | Defines the Grafana Agent listen HTTP address                    |
| `grafana_agent_server_grpc_address`| `127.0.0.1:9091`            | Defines the Grafana Agent listen GRPC address                    |
| `grafana_agent_metrics_config`     | see [defaults](defaults/main.yml)| Defines the Grafana Agent metrics configuration             |
| `grafana_agent_integrations_config`| see [defaults](defaults/main.yml)| Defines the Grafana Agent integrations configurations       |

### Examples

You can find some configurations examples :

  - [Example](docs/examples.md)

### Install and use this role

* Install the role using the command-line :

  ```shell
  $ ansible-galaxy role install git+https://github.com/f-bn/grafana-agent-role.git grafana_agent
  ```

* You can also install the role in your projects using a `requirements.yml` file and `ansible-galaxy` command-line :

  ```YAML
  $ cat requirements.yml
  ---
  roles:
    - name: grafana_agent
      src: https://github.com/f-bn/grafana-agent-role.git
      scm: git
      version: '1.0.0'

  $ ansible-galaxy install-f -r requirements.yml
  ```

* Once the role is installed, you can use it in your playbooks :

  ```yaml
  - name: Deploy
    hosts: <hosts>
    roles:
      - role: grafana_agent
  ```
