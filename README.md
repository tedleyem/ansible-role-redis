Redis
=========

This is an Ansible playbook to install redis
Redis Setup 5.0.5


Requirements
------------
On RedHat-based distributions, this role might requires the EPEL repository.

molecule ~> 5.0
[updated molucule version](https://dailystuff.nl/blog/2023/switch-to-molecule-plugins)

pip3 install flake8
pip3 install yamllint
pip3 install ansible
pip3 install ansible-lint
pip3 install -molecule
pip3 install ansible docker
pip3 install ansible openshift
pip3 install ansible python-vagrant
pip3 install ansible netaddr
pip3 install ansible molecule-docker
pip3 install ansible molecule-podman
pip3 install ansible molecule-vagrant

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

  Run Molecule test with vagrant
```
  $ molecule init scenario role --driver-name=vagrant
  $ molecule create

```
  Run isolated Vagrant test
```
 $ cd tests
 $ vagrant up --provision
```

License
-------

BSD


---
## RESOURCES
[Ansible testing with Vagrant](https://blog.meralus.com/Ansible-testing-with-Vagrant/)
[Cache vs Session store ](https://redislabs.com/blog/cache-vs-session-store/)



Author Information
------------------
This role was created in 2018 and recently updated in 2023