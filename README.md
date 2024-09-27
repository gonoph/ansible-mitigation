# ansible-mitigation
Ansible Playbooks to mitigate certain CVEs

## Usage

1. clone or download the needed mitigation
2. configure your inventory
3. run the mitigation as a playbook
4. set `apply_mitigation=False` if you want to unapply the mitigation

## Examples

Clone the git repo
```bash
git clone https://github.com/gonoph/ansible-mitigation.git
cd ansible-mitigation
```

### Run the playbook in ad-hoc mode

```bash
ansible-playbook -i host1.example.com, mitigate.cve-2024-47176.yml
```

### Run the playbook w an inventory

Create an `inventory` file
```ini
[all]
host1.example.com
host2.example.com
host3.example.com

[all:vars]
ansible_user=ansible
```

Run the playbook with the inventory
```bash
ansible-playbook -i inventory mitigate.cve-2024-47176.yml
```

### Unapply the mitigation

```bash
ansible-playbook -i inventory mitigate.cve-2024-47176.yml -e apply_mitigation=False
```


## DISCLAIMER

This is provided for educational purposes only. Use at your own risk!

Please refer to your official documentation and patching poliices before
attempting to run this in production.
