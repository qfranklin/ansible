Plan:
1. Add new content directly in the README format
2. Keep existing commands 
3. Add clear sections and descriptions
4. Maintain existing triple backtick blocks

```markdown
# Ansible Dev Environment Manager

Automated setup for Laravel + Vue.js development and production environments. Configures local WSL development and remote production deployment using Ansible playbooks.

## Prerequisites
- Windows with WSL2 support (for development)
- Ubuntu server (for production)
- Git
- Ansible

## Windows WSL Setup
### Step 1: Install WSL
```powershell
wsl --install
```

### Step 2: List all WSL instances (optional)
```powershell
wsl --list --all
```

### Step 3: Delete (unregister) each WSL instance
```powershell
wsl --unregister Ubuntu
```

### Step 4: Install a fresh WSL instance
```powershell
wsl --install -d Ubuntu
```

## Initial Ubuntu Setup
Run these commands to prepare the environment:
```bash
sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install -y ansible
```

## Development Environment
Sets up local development with:
- Laravel + Composer
- Vue.js + Vite
- MySQL database
- Nginx on port 8082
- Hot-reloading enabled

Run:
```bash
sudo usermod -a -G www-data $USER
git config core.fileMode false
ansible-playbook setup.yml -i inventory/dev.yml --ask-become-pass
```

Restart WSL after setup:
```powershell
wsl --shutdown
```

## Production Environment
Deploys to remote server with:
- Optimized production builds
- Nginx on port 80
- Secure MySQL configuration
- System service configuration

Run:
```bash
ansible-playbook setup.yml -i inventory/prod.yml --ask-become-pass
```

## Environment Differences
Development:
- Uses local directories
- Development server ports
- Debug enabled
- Hot-reloading

Production:
- Deploys to /var/www
- Production ports
- Optimized builds
- Service configuration
```