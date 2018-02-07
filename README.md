# ansible-redis

ansible-redis helps to install redis in RHEL Linux servers and manage them.The default values of the roles can be overridden by the user which reflects in redis.conf file.

## Requirements

The role requires minimum ansible version of 2.0 and python to be installed in the remote servers.

## Role Default Variable

The following variables can be customized according to the user needs

```
  redis_bind_ip:0.0.0.0                   # Redis Network address
  redis_port: 6379                        # Redis Default Port
  redis_log_file: /var/log/redis          # Redis Log directory
  redis_dbs: 10                           # Redis Max number of Databases
  redis_db_save_time:                     # Redis Persistent save freq  
    - [900,1]
    - [300,10]
    - [60,10000]
  redis_db_file_name: dump.rdb            # Redis snapshot file name
  redis_db_dir: /var/lib/redis            # Redis db default directory
  redis_role: master                      # Redis cluster role
  redis_requirepass: false                # Redis Password config
  redis_pass: None                        # Redis Password
  redis_protected_mode: no                # Redis Protected mode setup
  redis_max_client: 1000                  # Redis max clients 
  redis_max_memory: 1024                  # Redis max memory
  redis_max_memory_policy: volatile-lru   # Redis memory policy when max memory reaches
  redis_append_fsync: everysec            # Redis append functionality setup
  redis_timeout: 0                        # Redis timeout setup
```


## Supported OS Family

Redhat Linux

## How to use the role

The example code is as follows,

```
- hosts: all
	  sudo: true
	  roles:
	  - {role: kanapuliAthavan.redis}
```
