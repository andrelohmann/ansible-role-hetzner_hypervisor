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

    hetzner_hypervisor_gateway: __YOUR_HYPERVISORS_MAIN_IP_GATEWAY_ADDRESS__
    hetzner_hypervisor_libvirt_members:
    - __YOUR_MEMBER__
    hetzner_hypervisor_vms_path: __PATH_TO_YOUR_QCOW2_IMAGES__
    # available network: e.g. 10.10.10.64 - 10.10.10.71
    hetzner_hypervisor_vms:
    - name: __YOUR_VM_NAME__
      ip: 10.10.10.64
      size: 10 # size in GB
      ram: 4096 # size in MB
      cores: 2
      mac: "10:10:00:00:00:01"
      distro: debian/ubuntu
      release: jessie/stretch/trusty/xenial
      state: present/absent
    - name: __YOUR_VM_NAME__
      ip: 10.10.10.65
      size: 10
      ram: 4096
      cores: 2
      mac: "10:10:00:00:00:02"
      distro: debian/ubuntu
      release: jessie/stretch/trusty/xenial
      distro: debian/ubuntu
    - name: __YOUR_VM_NAME__
      ip: 10.10.10.66
      size: 10
      ram: 4096
      cores: 2
      mac: "10:10:00:00:00:03"
      distro: debian/ubuntu
      release: jessie/stretch/trusty/xenial
      distro: debian/ubuntu

Example Playbook
----------------

    - hosts: hypervisor
      roles:
         - { role: andrelohmann.hetzner_hypervisor }

License
-------

MIT

Author Information
------------------

https://github.com/andrelohmann
