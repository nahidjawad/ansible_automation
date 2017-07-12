# Automatic Deployment with Ansible
This repo containts playbooks, roles to deploy popular web apps and their stacks. For example the playbook for wordpress include roles to install LAMP on a RHEL/CentOS 7.x system.

## List of playbooks
 - Wordpress
 - Drupal (TODO)
 - Joomla (TODO)

### How to run a playbook

Make sure the hosts.yml file containts a hostname/IP address of your target host.

```
ansible-playbook -i hosts.yml plays/wordpress.yml
```

#### hosts
A typical host file to run wordpress on a system called www.test.com may look like

```
[wordpress]
www.test.com 
```
#### vars
Variables are stored in groupvars/ directory. For example to install version 4.7, edit groupvars/wordpress file as

```
wordpress:
  version: 4.7
```

#### Passwords
Passwords are stored outside the ansible directory. Credentials for each host as its own directory. An example directory structure can be

```
ansible/
credentials/
+-- www.test.com
|   mysql_root_password
|   +-- test/
|   |   +-- user_test/
|   |   |   +-- db_pass
```
Here, ansible stored the mysql root password in mysql_root_password file under the directory named after inventory host www.test.com.

Inside www.test.com directory, each directory is the name of a mysql database created by Ansible. Each of these mysql database directories contains directories named as the database user (i.e. user_test is a database user of the database test). 

The password for user_test is stored inside the directory in the text file db_pass.



