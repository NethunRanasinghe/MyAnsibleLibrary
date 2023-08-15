# VMs and Container Updater

> The purpose of this playbook is to simply update cache (apt-update) and upgrade all the packages (apt-upgrade) of mentioned hosts.

> Hosts file is encrypted using
<br>`ansible-vault encrypt inventory_name`

> Inside the inventory file hosts are in the format
<br>`hostname ansible_ssh_user=user ansible_become_password=pass`

> ssh keys were added to the lxc containers and vms using
<br>`ssh-copy-id user@remote_host`