# Volume Activation Error

| Key | Value |
|----|-------|
|Error| `TASK ERROR: activating LV 'Section-02/Section-02' failed: Activation of logical volume Section-02/Section-02 is prohibited while logical volume Section-02/Section-02_tmeta is active.` |
|Solution Type | `Temporary` |
|Permenant Solution| `Run a SMART Scan and even if the SMART didn't return errors, backup all valuable data and replace the hard drive.` |


## Sample Host Config
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