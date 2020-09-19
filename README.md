# ansible_tutorial
Following along with the LearnLinuxTV Ansible tutorial series.

Ansible is an automation and configuration management technology used to
provision, deploy, and manage compute infrastructure across cloud, virtual, and
physical environments.


## Setting up `ssh`

First step was to set up ssh key-pairs using type ed25519, with "general" keys
as well as ansible-specific.  Author suggests using passphrase for the general
key but no passphrase for the ansible-specific.

Create an alias on the local machine 'ssha' as follows:
```
alias ssha='eval $(ssh-agent) && ssh-add'
```

## Setting up `ansible`

To set up `ansible`:
1. Install ansible
   `sudo zypper install ansible`
2. Create `inventory` file of ansible hosts
3. Run a command against these hosts:
   `ansible all --key-file ~/.ssh/id_ed25519_ansible -i inventory -m ping`
4. Simplify this by creating an `ansible.cfg` configuration file to specify the
   inventory file and the ssh key, then
   `ansible all -m ping`


## Getting started with Ansible

List all ansible hosts
   `ansible all --list-hosts`
Check out all configuration
   `ansible all -m gather_facts`

Running an ad-hoc command with elevated privileges.
    `ansible all -m apt -a update_cache=true --become --ask-become-pass`

