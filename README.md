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
