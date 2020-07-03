# Ansible playbook to install redis
Redis-Sentinel HA Setup

This role is designed to setup a Parent/Child High Availability
cluster with 3 sentinel instances running for a fault tolerant Redis Environment.

## Requirements

## Cache vs Session store
LINK: https://redislabs.com/blog/cache-vs-session-store/

This playbook also requires specific host variables
 Example:
 [redis-nodes]
 dolly01 redis_role=master
 dolly02 redis_role=slave
 dolly03 redis_role=sentinel

## Role Variables
### all variables can be found under group_vars/all.yml file
- redis_version: "5.0.5"
- redis_url: "http://download.redis.io/releases/redis-{{ redis_version }}.tar.gz"
- redis_dir: "/opt/redis-{{ redis_version }}"
- install_dir: "/opt/"
- redis_cache: Adding any vaule will setup redis for LRU cache only cluster
- redis_session: # Adding any value witll setup redis for session store cluster

## Dependencies
 tcl and cmake tools are required to install redis from sources.

## Test Playbook
 ansible-playbook -i tests/inventory roles/redis-sentinel-HA/main.yml

License
GNU GPLv3


Author Information
 Twitter: @TechGameTeddy
