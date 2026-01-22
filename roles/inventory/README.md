inventory
=========
```
This role will update the inventory on the Controller
```
Requirements
------------
```
Admin Account on your Ansible Controller
```
Role Variables
--------------
```
# Use a Red Hat Ansible Automation Platform credential type
# CONTROLLER_HOST: example.com
# CONTROLLER_USERNAME: mickey.mouse
# CONTROLLER_PASSWORD: password
inventory_managed_inventory_name: AAP Managed Inventory
inventory_region: us-west-1
ansible_python_interpreter: /usr/bin/python3

```
Dependencies
------------

Example Playbook
----------------
```
---
- name: Update inventory
  hosts: localhost
  connection: local

  tasks:

    - name: Include the inventory role
      tags:
        - create
      ansible.builtin.include_role:
        name: inventory

or

---
- name: Remove a vms from our inventory
  hosts: localhost
  connection: local

  tasks:

    - name: Include the vm role
      tags:
        - remove
      ansible.builtin.include_role:
        name: inventory
```
License
-------

https://opensource.org/license/mit