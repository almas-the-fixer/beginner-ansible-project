# Beginner Ansible Project — Install Go on Windows

This is a simple Ansible playbook project designed to install the Go programming language on a remote Windows machine.

## 📦 What's Included

- `install-go.yml`: Ansible playbook to:
  - Download Go MSI installer
  - Install Go
  - Add Go to system PATH
- `inventory.example.ini`: Example inventory file structure
- `.gitignore`: Protects sensitive data like `inventory.ini`

## ⚙️ Requirements

- Ansible (on controller Linux machine)
- A remote **Windows** machine with:
  - WinRM enabled (basic auth over HTTP)
  - Administrator access
- Python 3 on controller
- Network access between controller and Windows machine

## 🚀 Usage

1. **Clone the repo**  
   ```bash
   git clone https://github.com/yourusername/beginner-ansible-project.git
   cd beginner-ansible-project
   ```

2. **Create your own `inventory.ini`** (do NOT commit it):
   ```ini
   [windows]
   your.windows.ip

   [windows:vars]
   ansible_user=your-username
   ansible_password=your-password
   ansible_connection=winrm
   ansible_winrm_transport=basic
   ansible_winrm_port=5985
   ```

3. **Run the playbook**:
   ```bash
   ansible-playbook -i inventory.ini install-go.yml
   ```

## ⚠️ Security Note

Do NOT share `inventory.ini` or real credentials. This repo includes `.gitignore` to help prevent accidental exposure.

---

Happy Automation! ⚙️🚀
