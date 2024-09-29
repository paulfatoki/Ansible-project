# updates for master controller and target machines
#update  sudo apt update -y
sudo apt install net-tools
# passwordless authentication
ssh-keygen  for master controller

cd .ssh/
cat id_ed25519.pub
# traget machine -01 do cd .ssh/
vi authorisedkeys
put in ssh-ed25519
# go back to ansible controller
ansible -i inventory all -m ping
adhoc command : ansible -i inventory all -a "ls",  ansible -i inventory all -a "ls -lart"
ansible -i inventory all -a "mkdir cloud"
to remove the folder called t
to create a folder in ansible contrller,, ansible -i inventory all -a "touch cloud/text1.txt"
 ansible -i inventory webservers -a "ls"
 ansible -i inventory all -m shell -a 'df -h'
 #ansible ad hoc command to check the free memory or memory usage of hosts
ansible -i inventory all -a "free -m"
touch /tmp/my-file.txt
# to add file to all the machines : 
ansible -i inventory webservers -m copy -a "src=/tmp/my-file.txt dest=/tmp/my-file.txt"
# to install apache on all machines
ansible -i inventory webservers -m apt -a 'name=apache2 state=present'
# how to handle multiple tasks: using a playbook (apache , nginx e.t.c)
# ansible variable optimizing your code
#To kill all the running process on the port 80

sudo apt-get install psmisc
 sudo fuser 80/tcp sudo lsof -i tcp:80 
sudo lsof -i tcp:80 -s tcp:listen 
sudo lsof -t -i tcp:80 -s tcp:listen | sudo xargs kill


=====

#To purge apache2

sudo apt-get purge apache2
# to create a user and group in ansible
# to grep (narrow down)  cat /etc/group | grep pkadmin, cat /etc/passwd | grep tk
# Ansible Roles (encapsulate your codes)
# install java and jenkins.yml
