# 02. Ansible Installation & Setup

## Install Ansible

Ansible is installed on the **Control Node**.

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install ansible -y
```
### RHEL / Fedora

```bash
sudo dnf install ansible-core -y
```
Verify:

```bash
ansible --version
```
---

## SSH Setup

Ansible commonly uses `SSH` to connect to Linux managed nodes.

Generate an SSH key on the Control Node:

```bash
ssh-keygen -t ed25519
```
Copy the public key to the managed node:

```bash
ssh-copy-id user@<managed-node-ip>
```
Test the connection:

```bash
ssh user@<managed-node-ip>
```
> **Passwordless SSH is commonly used for Ansible automation.**

---

## Ansible Project Structure

A simple Ansible project can look like:

```text
ansible-project/
├── ansible.cfg
├── inventory.ini
└── playbook.yml
```
---

## Ansible Configuration

Ansible uses `ansible.cfg` for configuration.

Common configuration locations include:

```bash
./ansible.cfg
~/.ansible.cfg
/etc/ansible/ansible.cfg
```
Example:

```ini
[defaults]
inventory = ./inventory.ini
remote_user = ubuntu
interpreter_python = auto_silent
```
Check the active configuration:

```bash
ansible-config dump --only-changed
```
---

## Verify the Setup

Check the Ansible version:

```bash
ansible --version
```
Check the inventory:

```bash
ansible-inventory --graph
```
Test connectivity:

```bash
ansible all -m ansible.builtin.ping
```
Expected:

```text
web01 | SUCCESS => {
    "ping": "pong"
}
```
---

## Setup Flow

```text
Install Ansible
      ↓
Configure SSH
      ↓
Create Inventory
      ↓
Configure ansible.cfg
      ↓
Test Connectivity
      ↓
Ready for Automation
```
## Key Takeaways

- **Control Node** → Machine where Ansible is installed and executed
- **SSH** → Common connection method for Linux managed nodes
- **ansible.cfg** → Ansible configuration
- **Inventory** → Defines managed hosts
- **Ping module** → Quick connectivity test

---

## Remember

```text
Inventory → Where?
Playbook  → What?
Task      → One action
Module    → How?
Role      → Reusable structure
Variable  → Dynamic value
Vault     → Secret
```

