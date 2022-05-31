ansible-role-configure-nodepilot
=========

Ansible role that installs Node Pilot and configures user, firewall and Docker.
###
Do note, this role is somehwat tested but is not completely done. I will build in more checks and all.
###
If you have any remarks, please let me know or just create a pull request.

Requirements
------------

Debian should work but is not tested. Ubuntu 20.04, 21.10 and 22.04 are tested.

Role Variables
--------------

* **Variable**: `home_ip:`
  * **Description**: The IP address of the home server.
  * **Required**: no
  * **Type**: string
  * **Default**: `empty`
#####
* **Variable**: `nodepilot_version:`
  * **Description**: The version of Node Pilot to fetch from the NodePilot S3 bucket. This will be automated later.
  * **Required**: yes
  * **Type**: string
  * **Default**: `"v0.12.12"`
#####
* **Variable**: `systemd_setup:`
  * **Description**: Set to true if you want to configure a systemd service file for node-pilot.
  * **Required**: no
  * **Type**: boolean
  * **Default**: `true`
#####
* **Variable**: `ufw_setup:`
  * **Description**: If set to `true`, the role will configure ufw to allow NodePilot related ports.
  * **Required**: yes
  * **Type**: boolean
  * **Default**: `true`
#####
* **Variable**: `docker_setup:`
  * **Description**: If set to `true`, the role will install Docker. This is a requirement for NodePilot, but you might have already taken care of it.
  * **Required**: yes
  * **Type**: boolean
  * **Default**: `true`
#####

Dependencies
------------

- Curl
- Ansible

Installation
------------

`ansible-galaxy install stefanfluit.ansible_role_configure_nodepilot`

Example Playbook
----------------

```
---
- hosts: all
  become: true

  roles:
    - ansible-role-node-pilot-configurator

```

License
-------

MIT

Author Information
------------------

Name: Stefan Fluit
###
Email: [info+pokt-ansible@fluit-online.nl](mailto://info+pokt-ansible@fluit-online.nl)