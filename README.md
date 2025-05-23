Sure! Here's the corrected content formatted as a complete `README.md` Markdown file:

````markdown
# 🛠️ Ansible Automation Playbooks

Welcome to my **Ansible** repository — a growing collection of playbooks to automate common AWS and Linux tasks. These playbooks are designed for ease of use and assist in provisioning, managing, and tearing down infrastructure like EC2 instances.

---

## 📁 Repository Structure

```bash
.
├── ec2
│   ├── ec2_deployment
│   │   ├── ec2_deploy.yml           # Provisions EC2 instances with public IP and SSH access
│   │   └── group_vars
│   │       └── all
│   │           └── pass.yml         # Encrypted vault file containing AWS credentials
│   └── ec2_stop
│       ├── ec2_stop.yml            # Stops running EC2 instances
│       └── inventory.ini           # Inventory file listing target EC2 instances
└── README.md
````

✨ *More tasks and modules will be added soon (user management, package installation, service configuration, etc.)*

---

## ✅ Prerequisites

Ensure the following are installed:

* Python 3.x
* Ansible
* Boto3 & Botocore (required for AWS modules)

Install via pip:

```bash
pip install ansible boto3 botocore
```

---

## 🔐 Vault Setup

Sensitive AWS credentials are securely stored using **Ansible Vault**.

To create or edit the encrypted vault file:

```bash
ansible-vault edit ec2/ec2_deployment/group_vars/all/pass.yml
```

Example vault contents:

```yaml
ec2_access_key: YOUR_ACCESS_KEY
ec2_secret_key: YOUR_SECRET_KEY
```

You'll be prompted for a vault password when running any playbook that references this file.

---

## 🚀 Usage

### ▶️ Deploy EC2 Instances

```bash
ansible-playbook ec2/ec2_deployment/ec2_deploy.yml --ask-vault-pass
```

This playbook provisions EC2 instances with:

* Custom AMIs
* Key pair: `sid-key`
* Public IP assignment
* Secure credentials via Ansible Vault

### ⏹️ Stop EC2 Instances

```bash
ansible-playbook -i ec2/ec2_stop/inventory.ini ec2/ec2_stop/ec2_stop.yml
```

Ensure that `inventory.ini` lists the instances you want to stop.

---

## 🌟 Features

* 🚀 Launch EC2 instances with public IPs and SSH access
* 🔐 Secure AWS credential management using Ansible Vault
* ⏹️ Easily stop instances via a simple inventory
* 📦 Modular structure for easily extending functionality
* 🧩 Ready for expansion (user management, software installs, service configuration, etc.)

---

## 📝 To-Do (Coming Soon)

* Create Linux users and manage SSH keys
* Install packages (e.g., Docker, NGINX)
* Perform system updates and restart services
* Add playbooks for full EC2 teardown and cleanup

---

## 🙋‍♂️ Author

**Siddhartha Gaurav**
I'm passionate about automation and cloud infrastructure.
Feel free to connect with me or contribute to this project!

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 🤝 Contributions

Contributions, issues, and feature requests are welcome!
To contribute:

* Fork the repo
* Create a new branch
* Commit your changes
* Submit a pull request

---

```

Let me know if you’d like me to create a `LICENSE` and `.gitignore` file to match this project.
```
