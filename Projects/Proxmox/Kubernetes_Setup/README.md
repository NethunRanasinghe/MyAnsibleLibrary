# Kubernetes (K8s) Installation Script

- Introduction
- Why?
- Prerequisites
- Execution Instructions

## Introduction
> The objective of this playbook is to automate the installation and setup of a kubernetes instance. The playbook consist of 3 main plays. For both controller and nodes, for controller only and for nodes only. It will ask user confirmation before moving on to each stage. By the end of the playbook two files will be created on the controller node named **worker_conn_string** and locally inside the playbook directory with the name **Remote_Files/worker_conn_string**. This will have the **connection string** to connect new nodes/controllers. (Note:- for controllers use **--control-plane** flag)

## Why?

>My first choice was K3s, but after trying to get it to work for 3 days I just gave up. I've being getting a CA certificate error that I couldn't manage to fix. I'm pretty sure it's a load balancer issue but after trying to fix it for a while I decided to go with K8s instead.

### References
---

**Youtube** - https://youtu.be/U1VzcjCB_sY <br>
(This is a fantastic video and it explains everything perfectly. It helped me to setup a basic template on how to start automating the process) <br><br>
**Documentation** - https://kubernetes.io/docs/setup/

## Prerequisites

1. Atleast 2 VMs  (1 For Control Node and 1 For Worker Node).
1. Static IPs should be set along with unique host names.
1. Inventory should be in this format <br>
```ini
    [controllers]
    host_name ansible_ssh_host=<IP> ansible_user='<USERNAME>' ansible_become_pass='<PASSWORD>'

    [nodes]

    [instance:children]
    controllers
    nodes
```
(If you want to change this, don't forget to change the `k8s.setup` as well)

## Execution Instructions

```bash
ansible-playbook -i <INVENTORY> <PLAYBOOK>
```
### Optional Flags
| Flag  | Use Case |
|-------|-----------|
| --ask-vault-pass | If the vault is encrypted |
| --start-at-task | If you want to start from a specific task|
| --tags | If you want to only run a specific group of tasks|
