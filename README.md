# Windows wsl install
  ## Step 1: Install WSL
  ```powershell
  wsl --install
  ```
  
  # Step 2: List all WSL instances (optional)
  ```powershell
  wsl --list --all
  ```
  
  # Step 3: Delete (unregister) each WSL instance
  ```powershell
  wsl --unregister Ubuntu
  ```
  
  # Step 4: Install a fresh WSL instance
  ```powershell
  wsl --install -d Ubuntu
  ```
# Ubuntu helpful commands
  ```bash
  sudo apt update
  sudo apt install -y software-properties-common
  sudo add-apt-repository --yes --update ppa:ansible/ansible
  sudo apt install -y ansible
  ansible-playbook setup.yml -i localhost --ask-become-pass
  sudo usermod -a -G www-data $USER
  ```