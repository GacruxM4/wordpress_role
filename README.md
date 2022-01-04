Role Name : wordpress_role
=========

Install wordpress with an Ansible role using docker_container.

Requirements
------------

- Ansible

You'll need docker installed on the hosts you want to deployed this role. You can either do it yourself using the convenience script (https://get.docker.com/) and delete the role 'gacruxm4.docker' line from the **Example Playbook**. 
Or you can use my own Ansible role as depencencies : `ansible-galaxy install gacruxm4.docker`.

Role Variables
--------------

All the default variables for this role are available in `defaults/main.yml`.

Dependencies
------------

As per requiements, you'll need to use my docker role for this one to work : `ansible-galaxy install gacruxm4.docker`

Example Playbook
----------------

```yaml
---
- hosts: all
  vars:
    wp_version: 5.0.3
    wp_mysql_db: 'database_name_here'
    wp_mysql_user: 'username_here'
    wp_mysql_password: 'password_here'
    wp_webserver: nginx
    wp_sitename: example.com
    wp_admin_email: 'your@email.com'
    wp_install_dir: "/var/www/{{ wp_sitename }}"
  roles:
    - gacruxm4.docker
    - gacruxm4.wordpress_role
```

License
-------

BSD

Author Information
------------------
Aurélien Daix a.k.a GacruxM4 :)
