remove_digitalocean_droplet
=========

A role to delete a DigitalOcean droplet.

Requirements
------------

You must use DigitalOcean, have a DO API key setup and have DigitalOcean droplet (VPS) that you would like to delete / destroy.

Role Variables
--------------

Host Name of the droplet, also the droplet name as shown in DigitalOcean
```
	remove_digitalocean_droplet_host_name: "your-hostname-here"
```

You must have your DigitalOcean API token saved into this environment variable
```
	remove_digitalocean_dns_entries_do_token: "{{ lookup('env', 'DO_API_TOKEN') }}"
```

(Default) How long before wait gives up, in seconds
```
	remove_digitalocean_droplet_wait_timeout: 500
```

(Default) Recommend keeping this setting. Makes the creation of the droplet idempotent.
```
	remove_digitalocean_droplet_unique_name: yes
```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:


	- hosts: localhost ansible_connection=local ansible_python_interpreter=python
	  vars_files:
	    - vars/main.yml
	  roles:
	    - stancel.remove_digitalocean_dns_entries


or 


	- hosts: localhost ansible_connection=local ansible_python_interpreter=python 
	  vars:
		remove_digitalocean_droplet_host_name: "your-hostname-here"
		remove_digitalocean_dns_entries_do_token: "{{ lookup('env', 'DO_API_TOKEN') }}"
	  roles:
	    - stancel.remove_digitalocean_dns_entries


License
-------

BSD

Author Information
------------------

[Brad Stancel](https://github.com/stancel)

