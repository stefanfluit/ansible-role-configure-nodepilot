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

* `home_ip`
The IP address you will use to access SSH on the NodePilot server.
###
* `nodepilot_version`
The version of NodePilot to install. You can find versions [here](https://docs.decentralizedauthority.com/install).
###
* `systemd_setup`
If set to `true`, the role will configure systemd to start NodePilot on boot. If not, you will have to start nodepilot yourself.
###
* `ufw_setup`
If set to `true`, the role will configure ufw to allow NodePilot related ports.
###
* `docker_setup`
If set to `true`, the role will install Docker. This is a requirement for NodePilot, but you might have already taken care of it.

Dependencies
------------

- Curl
- Ansible

Installation
------------

`ansible-galaxy install stefanfluit.ansible_role_configure_nodepilot`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

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