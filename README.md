Redis
=========

This is an Ansible playbook to install redis
Redis Setup 5.0.5


Requirements
------------
On RedHat-based distributions, this role might requires the EPEL repository.


Role Variables
--------------
There is a large list of configurable variables for setting up redis tha can be found in
vars.yml

The role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------
None

Example Playbook
----------------
```
    - hosts: all
      roles:
         - { role: tedleyem.redis }
```

## Test Playbook
 This playbook can be tested with ansible molecule and/or hashicorp vagrant with the Vagrantfile in the root of the repo.

  Run Molecule
```
  $ molecule init scenario role --driver-name=podman
  $ molecule create

```
  Run Vagrant
```
  $ vagrant up --provision
```

License
-------

BSD


---
## RESOURCES
[Cache vs Session store ](https://redislabs.com/blog/cache-vs-session-store/)



Author Information
------------------
This role was created in 2018 and recently updated in 2023