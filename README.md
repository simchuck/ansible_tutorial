# ansible_tutorial
ride-along with LearnLinuxTV ansible series

Following along with the Ansible tutorial series.

First step was to set up ssh key-pairs using type ed25519, with "general" keys
as well as ansible-specific.  Author suggests using passphrase for the general
key but no passphrase for the ansible-specific.

Create an alias on the local machine 'ssha' as follows:
```
alias ssha='eval $(ssh-agent) && ssh-add'
```
