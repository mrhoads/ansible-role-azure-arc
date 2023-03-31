Role Name
=========

Onboard machines to Azure Arc

Requirements
------------

This role requires that an appropriately scoped service principal is created in order to be onboarded.

Role Variables
--------------

This role requires the following vars:
- RESOURCE_GROUP <-- which resource group the server(s) will be onboarded to
- SUBSCRIPTION_ID <-- the subscription the server(s) will be onboarded to
- LOCATION <-- the Azure region in which the server(s) will be onboarded to
- SERVICE_PRINCIPAL_ID <-- the service principal ID doing the onboarding
- SERVICE_PRINCIPAL_SECRET <-- the service principal client secret doing the onboarding


Dependencies
------------

This role has no external dependencies.

Example Playbook
----------------

Below is an example of using this role to onboard the group *arc* to Azure with the SERVICE_PRINCIPAL_SECRET set as an environment variable 


```
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
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
