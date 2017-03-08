hetzner_hypervisor
====================

[![Build Status](https://travis-ci.org/andrelohmann/ansible-role-hetzner_hypervisor.svg?branch=master)](https://travis-ci.org/andrelohmann/ansible-role-hetzner_hypervisor)

Use this role to provision your hetzner pizzabox with a libvirt hypervisor and kvm based virtual machines.

Requirements
------------

This role requires you to have a dedicated, unmanaged root server at hetzner.de that is allready base provisioned for the usage of ansible.

It is strongly suggested, to rely on my hetzner_installimage role for the baseprovisioning.

Role Variables
--------------

The following mandatory variables need to be set in group_vars/host_vars

    hetzner_hypervisor_install_from_backports: True
    hetzner_hypervisor_gateway: __YOUR_HYPERVISORS_MAIN_IP_GATEWAY_ADDRESS__
    hetzner_hypervisor_libvirt_members:
    - __YOUR_MEMBER__
    hetzner_hypervisor_vms_path: __PATH_TO_YOUR_QCOW2_IMAGES__
    # available network: e.g. 10.10.10.64 - 10.10.10.71
    hetzner_hypervisor_vms:
    - name: __YOUR_VM_NAME__
      ip: 10.10.10.64
      size: 10G
      ram: 4096
      cores: 2
      mac: "10:10:00:00:00:01"
      distro: debian/ubuntu
      release: jessie/stretch/trusty/xenial
    - name: __YOUR_VM_NAME__
      ip: 10.10.10.65
      size: 10G
      ram: 4096
      cores: 2
      mac: "10:10:00:00:00:02"
      distro: debian/ubuntu
      release: jessie/stretch/trusty/xenial
    - name: __YOUR_VM_NAME__
      ip: 10.10.10.66
      size: 10G
      ram: 4096
      cores: 2
      mac: "10:10:00:00:00:03"
      distro: debian/ubuntu
      release: jessie/stretch/trusty/xenial

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: hypervisor
      roles:
         - { role: andrelohmann.ansible-role-hetzner_hypervisor }

License
-------

MIT

Author Information
------------------

https://github.com/andrelohmann
