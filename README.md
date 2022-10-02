Ansible role: Provision - Generic
=================================

Provision generic host.
Provision a machine that already has an operating system
installed, contains a provision user with sudo permissions,
and has sshd installed and running. If using SSH public key
authentication then the provision user's public key must be
included in their authorized keys file.

Requirements
------------

This role depends on the [base provision role](https://github.com/wandansible/provision).

Installation
------------

This role can either be installed manually with the ansible-galaxy CLI tool:

    ansible-galaxy install git+https://github.com/wandansible/provision,main,wandansible.provision
    ansible-galaxy install git+https://github.com/wandansible/provision.generic,main,wandansible.provision.generic
     
Or, by adding the following to `requirements.yml`:

    - name: wandansible.provision
      src: https://github.com/wandansible/provision
    - name: wandansible.provision.generic
      src: https://github.com/wandansible/provision.generic

Roles listed in `requirements.yml` can be installed with the following ansible-galaxy command:

    ansible-galaxy install -r requirements.yml

Example Playbook
----------------

    - hosts: all
      roles:
         - role: wandansible.provision.generic
           become: true
           vars:
             root_password: "hunter2"
