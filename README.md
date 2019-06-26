# Ansible playbook to install redis

Redis-Sentinel HA Setup

This role is designed to setup a Master/Slave High Availability
cluster with 3 sentinel instances running for a fault tolerant Redis Environment.

## Requirements

This playbook prompts for Session or Cache cluster
This only affects the parameters saved in the redis.conf file.

Cache Cluster: saves redis data in memory (normal behavior in an LRU/Memcached setup)
Session Cluster: saves data on disk (Setup for using Redis as a Sesssion store)

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
- redis_run_dir: "/var/run/redis"
- redis_config_dir: "/etc/redis"
- redis_lib_dir: /var/lib/redis
- redis_logfile: /var/log/redis.log
- redis_port: "6379"
- sentinel_port: "26379"
- redis_bind_loop: 127.0.0.1
- redis_requirepass: password123
- redis_master_auth: master
- redis_master_name: redis-node-master
- sentinel_requirepass: password123
- sentinel_deny_scripts_reconfig: yes
- protected_mode: yes
- supervised_mode: yes # set to yes or no to allow
- sentinel_pid: /var/run/redis-sentinel.pid
- sentinel_logfile: /var/log/redis-sentinel.log
- sentinel_quorum: 2
- sentinel_down_ms: 6000
- sentinel_failtime: 800

## Dependencies
----------
 tcl and cmake tools are required to install redis from sources.

## Test Playbook

 ansible-playbook -i tests/inventory roles/redis-sentinel-HA/main.yml

License
GNU GPLv3


Author Information
 Twitter: @TechGameTeddy
