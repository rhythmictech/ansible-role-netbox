# Ansible Role Netbox
![Molecule Test](https://github.com/rhythmictech/ansible-role-netbox/workflows/Molecule%20Test/badge.svg)

Installs and configures [Netbox](https://github.com/netbox-community/netbox)


## Requirements
This role requires Ansible 2.8 or higher.
This role was designed for and tested on CentOS 7.x or CentOS 8.x and Amazon Linux 2.

## Dependencies
None.

## Example Playbook
```
- hosts: netbox_server
  vars_files:
    - vars/main.yml
  roles:
    - ansible-role-netbox
```

Inside vars/main.yml:
```
bitbucket_start_service: True
bitbucket_enable_service: True
bitbucket_wait_for_server_startup: True
bitbucket_place_config: True
bitbucket_config:
	jdbc:
		driver: org.h2.Driver
		url: jdbc:h2:${bitbucket.shared.home}/data/db;MVCC=TRUE;DB_CLOSE_DELAY=-1;DB_CLOSE_ON_EXIT=FALSE;TRACE_LEVEL_FILE=4
		username: sa
		password: password
	server:
		address: 127.0.0.1

```

## License
MIT
