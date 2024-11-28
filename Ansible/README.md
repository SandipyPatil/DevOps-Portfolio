# **Ansible Installation on Ubuntu**

This guide provides step-by-step instructions to install and verify Ansible on an Ubuntu system.

---

## **Prerequisites**
- An Ubuntu system (18.04, 20.04, or later).
- Sudo privileges for the user.

---

## **Installation Steps**

### **Step 1: Update the System**
Update the package repository to ensure you have the latest updates:
```bash
sudo apt update
sudo apt upgrade -y
```

---

### **Step 2: Install Required Dependencies**
Install the required software properties package:
```bash
sudo apt install software-properties-common -y
```

---

### **Step 3: Add Ansible PPA**
Add the official Ansible PPA to your system:
```bash
sudo add-apt-repository --yes --update ppa:ansible/ansible
```

---

### **Step 4: Install Ansible**
Install Ansible using the APT package manager:
```bash
sudo apt install ansible -y
```

---

## **Verification**

### **Check Ansible Version**
To confirm Ansible is installed, check its version:
```bash
ansible --version
```

Expected output:
```
ansible [core X.X.X]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3.X/site-packages/ansible
  executable location = /usr/bin/ansible
  python version = X.X.X
```

### **Test Ansible with a Ping**
1. Create a test **Inventory File**:
   ```bash
   echo "[all]
   localhost ansible_connection=local" > inventory.ini
   ```

2. Run a ping test:
   ```bash
   ansible all -i inventory.ini -m ping
   ```

3. Expected output:
   ```bash
   localhost | SUCCESS => {
       "changed": false,
       "ping": "pong"
   }
   ```

---

## **Uninstall Ansible**
If you need to remove Ansible, use the following command:
```bash
sudo apt remove --purge ansible -y
```

---

## **References**
- [Ansible Documentation](https://docs.ansible.com/)
- [Ansible GitHub Repository](https://github.com/ansible/ansible)

---