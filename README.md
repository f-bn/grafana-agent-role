### General informations

A brief description of the role goes here.

**Table of Contents**

  - [Roles variables](#role-variables)
  - [Examples](#examples)
  - [Install and use this role](#install-and-use-this-role)

**Supported Platforms**

  - \<platform\>

**Requirements**

  - \<requirement\>

**References**

  - \<reference : [Link]()\>

### Role variables

The role variables documentation are available here :

  - [General](docs/variables.md)

### Examples

You can find some configurations examples :

  - [Example](docs/examples.md)

### Install and use this role

* Install the role using the command-line :

  ```shell
  $ ansible-galaxy role install git+https://github.com/f-bn/ansible-role-template.git ansible_role_template
  ```

* You can also install the role in your projects using a `requirements.yml` file and `ansible-galaxy` command-line :

  ```YAML
  $ cat requirements.yml
  ---
  roles:
    - name: ansible_role_template
      src: https://github.com/f-bn/ansible-role-template.git
      scm: git
      version: '1.0.0'

  $ ansible-galaxy install-f -r requirements.yml
  ```

* Once the role is installed, you can use it in your playbooks :

  ```yaml
  - name: Deploy
    hosts: <hosts>
    roles:
      - role: ansible_role_template
  ```
