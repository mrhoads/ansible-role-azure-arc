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
          SERVICE_PRINCIPAL_ID: <service principal ID>
          SERVICE_PRINCIPAL_SECRET: "{{ lookup('env','SERVICE_PRINCIPAL_SECRET') }}"
          RESOURCE_GROUP: <resource group name>
          TENANT_ID: <tenant ID>
          LOCATION: <Azure region>
          SUBSCRIPTION_ID: <subscription ID>
```

License
-------

BSD

Author Information
------------------

Mike Rhoads
