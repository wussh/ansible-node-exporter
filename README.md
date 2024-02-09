# Ansible-Node-Exporter

## Description
This project is designed to streamline server management using Ansible. It includes various commands and configurations to automate tasks such as inventory management, host pinging, file manipulation, role initialization, and playbook execution.

## Getting Started

### Prerequisites
- Ansible installed on the control machine
- Access to remote hosts via SSH
- Basic knowledge of YAML syntax and Ansible concepts

### Installation
Clone this repository to your local machine:
```bash
git clone https://github.com/wussh/ansible-node-exporter.git
```

## Usage

### Inventory Management
To list all hosts defined in the inventory:
```bash
ansible all -i inventory/hosts --list-hosts
```

### Host Pinging
To ping all hosts in the inventory:
```bash
ansible all -i inventory/hosts -m ping
```

### File Manipulation
To create a file named `test.log` with specific permissions and ownership on hosts belonging to the `aws` group:
```bash
ansible aws -i inventory/hosts -m ansible.builtin.file -a "path=/var/log/test.log state=touch owner=root mode=600"
```

### Role Initialization
To initialize a new Ansible role named `node-exporter`:
```bash
ansible-galaxy init node-exporter
```

### Playbook Execution
To execute the playbook `app.yaml` using the hosts defined in the inventory:
```bash
ansible-playbook -i inventory/hosts provision/app.yaml
```