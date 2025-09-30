Ansible dump_postgres_db
=========

Role for creating script for dump postgres db.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

All variables you can see in defaults.
To configure a backup of more than 1 database, you should use the `dump_postgres_databases` variable as a list. For example:
```yaml
dump_postgres_databases:
  - database_name: database
    inform_system: is
    pg_password: pg_password
    pg_user: postgres
    remote_db_address: "127.0.0.1"
    remote_db_port: "5432"
    db_base_path: "/path/for/backup"
    pg_bash_exec: "bash -c"
```

Example Playbook
----------------

run-dump_postgres_db.yml
```yaml
- hosts: postgresql_servers
  become: yes
  roles:
      - ageres210784.dump_postgres_db
```

License
-------

Apache 2.0

Author Information
------------------

[Evseev Sergey](https://github.com/Ageres210784)
