Here's a professional README.md for your Ansible project:


# Ansible Infrastructure Automation Project

![Ansible](https://img.shields.io/badge/ansible-%231A1918.svg?style=for-square&logo=ansible&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-square&logo=amazon-aws&logoColor=white)

A comprehensive Ansible automation solution for EC2 instance configuration and web server deployment, implementing best practices from MPrashant's [Ansible Mastery Course](https://www.youtube.com/watch?v=y2TSR7p3N0M).

**Live Demo**: http://ec2-3-108-220-37.ap-south-1.compute.amazonaws.com/

## 🚀 Features

- **EC2 Instance Configuration**
- **Web Server Deployment**
- **Multi-role Architecture**
- **Automated Operations**:
  - User management & password policies
  - File system operations (copy/backup/permissions)
  - Service management (firewall, cron jobs, process control)
  - Package installation & dependency management

## 📦 Project Structure

```
ansible/
├── playbook_first/
│   ├── app_install.yml          # Application installation tasks
│   ├── user_manage.yml          # User creation/management
│   ├── firewall_changer.yml     # Firewall configuration
│   ├── roles.yml                # Main role executor
│   └── ...                      # Other specialized playbooks
│
├── roles/
│   ├── firewall_service/        # Firewall configuration role
│   ├── httpd_setup/             # Web server setup role
│   └── install-python/          # Python environment setup
│
├── ansible.cfg                  # Ansible configuration
├── hosts                        # Inventory definition
├── inventory.ini                # Target environment specification
└── LICENSE                      # Project license
```

## ⚙️ Prerequisites

- Ansible 2.10+
- Python 3.8+
- AWS Configration in terminal
- SSH access to target nodes

## 🛠️ Installation

1. Clone repository:
   ```
   git clone https://github.com//ansible-automation.git
   cd ansible-automation
   ```

2. Configure inventory:
   ```
   # inventory.ini
   [web_servers]
   ec2-3-108-220-37.ap-south-1.compute.amazonaws.com
   ```

3. Set up SSH keys:
   ```
   cp ansible_linux.pem ~/.ssh/
   chmod 600 ~/.ssh/ansible_linux.pem
   ```

## 🚀 Usage

**Deploy full configuration**:
```
cd playbook_first
ansible-playbook -i /etc/ansible/inventory.ini roles.yml
```

**Common Operations**:
```
# Web server setup
ansible-playbook app_install.yml

# User management
ansible-playbook user_manage.yml --tags user_creation

# Firewall configuration
ansible-playbook firewall_changer.yml
```

---

> **Note**: Requires proper AWS credentials setup in `~/.aws/credentials`
```
