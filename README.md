# 🚀 Ansible LAMP Stack Deployment on Fedora

This project automates the deployment and configuration of a full **LAMP stack (Linux, Apache, MariaDB, PHP)** on Fedora-based systems using **Ansible**. It's designed with **clean role-based structure** and includes support for **multiple environments** like dev and prod using separate inventory files.

---

## 📁 Project Structure
.
├── inventory
│   ├── dev
│   └── prod
├── playbook.yml
├── README.md
└── roles
    ├── apache
    │   ├── files
    │   │   └── index.php
    │   ├── handlers
    │   │   └── main.yml
    │   └── tasks
    │       └── main.yml
    ├── firewall
    │   └── tasks
    │       └── main.yml
    ├── mysql
    │   ├── tasks
    │   │   └── main.yml
    │   └── vars
    │       └── main.yml
    └── php
        ├── files
        │   └── index.php
        ├── handlers
        │   └── main.yml
        └── tasks
            └── main.yml

---

## 🔧 What It Does

✅ Installs and configures Apache  
✅ Installs and configures PHP  
✅ Installs and secures MariaDB  
✅ Deploys a sample `index.php`  
✅ Opens HTTP and HTTPS ports using firewalld  
✅ Uses handlers to restart services after changes  
✅ Supports dev/prod environments via separate inventories  

---

📜 How to Use
1. Install Ansible (if not already installed)
sudo dnf install ansible -y

2. Run the playbook (example for dev)
ansible-playbook -i inventory/dev playbook.yml

3. Check the Web Server
Visit http://localhost (or your server IP) to verify the PHP page.

🔐 Password Configuration
MariaDB root password is stored in:
roles/mysql/vars/main.yml

Example:
mariadb_root_password: secret

This is used to create /root/.my.cnf for easier future logins.

🔥 Handlers Used
Handlers restart Apache after:
  - Installing Apache
  - Deploying index.php
  - Installing PHP

🚧 To-Do / Improvements
  -  Use ansible-vault to encrypt sensitive data like database passwords
  -  Add additional PHP modules and monitoring tools

📘 Notes
This solution uses MariaDB (MySQL-compatible). You can switch to MySQL if needed.

Tested on Fedora 41+

Designed to be beginner-friendly and easy to extend.

