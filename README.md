Role Name
=========

Ansible Galaxy role to install and configure a private Burp Collaborator server.

Requirements
------------

A licensed version of Burp is required and `files/burpsuite_pro.jar` must be present.

Role Variables
--------------

* `subdomain` - The domain for your collaborator server.
* `external_ip` - The external IP for your collaborator server. Defaults to the hostname.
* `burp_location` - Defaults to '/opt'
* `burp_jar_name` - The name for the JAR in `files/`

Dependencies
------------

None

Example Playbook
----------------

```yml
- hosts: servers
  roles:
      - leesoh.collaborator
```

After the playbook runs, you'll need to manually run: `sudo letsencrypt certonly -n -d *.<DOMAIN> --agree-tos -m <EMAIL> --manual --server https://acme-v02.api.letsencrypt.org/directory`

License
-------

BSD-3

Reference
---------

Largely built from [this guide](https://www.nuharborsecurity.com/creating-a-private-burp-collaborator-in-amazon-aws-with-a-letsencrypt-wildcard-certificate/).