Role Name
=========

Onboard machines to Azure Arc

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:


---
- hosts: arc
  become: true
  roles:
    - role: mrhoads.ansible-role-azure-arc
      vars:
        azure:
          SERVICE_PRINCIPAL_ID: ba152a4f-d0f3-4ce5-9971-c14d71f2f4f7
          SERVICE_PRINCIPAL_SECRET: "{{ lookup('env','SERVICE_PRINCIPAL_SECRET') }}"
          RESOURCE_GROUP: demo-arc-rg
          TENANT_ID: 98ad103d-bc7c-44ec-b169-22f8543c27ba
          LOCATION: centralus
          SUBSCRIPTION_ID: ff6ad0fe-2e20-4569-9e84-fa4654519a40
  
License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
