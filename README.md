# 🛠️ Ansible Hello World Sandbox
This is a hello world Ansible project, meant for beginners. Nothing to complex going on here, and is meant to test out different concepts as a way of learning ansible

## 📌 Overview
This project uses **Ansible** to automate the provisioning, configuration, and management of infrastructure and applications.

### Goals
- Automate infrastructure setup
- Ensure consistent configuration
- Reduce manual intervention
- Enable repeatable deployments


## ⚙️ Requirements
- Ansible >= 2.10
- Python >= 3.x
- pipx
- SSH access to target machines

Install pipx
```sh
python3 -m pip install --user pipx
python3 -m pipx ensurepath
```

Install Ansible
```sh
pipx install --include-deps ansible
```

## 🔑 Inventory
Example inventory file:
```ini
[web]
web1 ansible_host=192.168.1.10
web2 ansible_host=192.168.1.11

[db]
db1 ansible_host=192.168.1.20
```

## ▶️ Usage
Example of running the `hello_world` playbook:
```sh
ansible-playbook -i inventories/dev/hosts.ini hello_world.yml
```

## 🧪 Testing
Test connectivity:
```sh
ansible all -i inventories/dev/hosts.ini -m ping
```

Dry run:
```sh
ansible-playbook playbooks/site.yml --check
```

## 🐛 Troubleshooting
Checking verbose logs:
```sh
ansible-playbook playbooks/site.yml -vvv
```

Verify Inventory:
```sh
ansible-inventory --list
```