# LAMP Stack Deployment with Ansible

This repository contains Ansible playbooks and configurations to automate the deployment of a **LAMP stack** (Linux, Apache, MySQL, PHP) on AWS EC2 instances.

---

## **Features**
- Automated installation and configuration of:
  - **Apache** (Web Server)
  - **MySQL** (Database Server)
  - **PHP** (Server-side scripting)
- Modularized roles for better reusability.
- Dynamic inventory support for scaling infrastructure.
- Passwordless SSH configuration for seamless deployment.

---

## **Prerequisites**
1. **AWS EC2 Instances**:
   - Ensure you have at least two EC2 instances running Ubuntu (or your preferred Linux distribution).
2. **Ansible Installed**:
   - Install Ansible on your local machine:
     ```bash
     sudo apt update
     sudo apt install ansible -y
     ```
3. **Passwordless SSH**:
   - Configure passwordless SSH access to your EC2 instances.

---

## **Project Structure**
```plaintext
.
├── inventory.ini          # Inventory file with target EC2 IPs
├── site.yml               # Main playbook to orchestrate tasks
├── roles/
│   └── lamp/
│       ├── tasks/
│       │   ├── main.yml   # Main task file
│       │   ├── apache.yml # Apache installation and configuration
│       │   ├── mysql.yml  # MySQL installation and configuration
│       │   ├── php.yml    # PHP installation and configuration
│       ├── handlers/
│       │   └── main.yml   # Handlers for restarting services
│       ├── vars/
│       │   └── main.yml   # Variables for the LAMP stack
│       ├── defaults/
│       │   └── main.yml   # Default variables
│       ├── templates/
│       │   ├── index.html.j2  
│       │ 
│       └── meta/
│           └── main.yml   # Role metadata
└── README.md              # Project documentation
└── check_dependencies.yml  # To check dependencies for MySQL 
