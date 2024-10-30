sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install -y ansible
ansible-playbook setup.yml -i localhost --ask-become-pass
sudo usermod -a -G www-data $USER
