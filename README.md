# ansible
Create three ec2 linux instances
1st Ansible server
2nd Node1
3rd Node2  
Connect server node
$ Sudo su
$ wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
$ ls
$ yum install (copy the above line) 
yum install git python python-level python-pip openssl ansible -y
Check for ansible installed
$ ansible --version
$ vi /etc/ansible/hosts
To give the hosts name and (enter add node1 node 2 private ips in groups)
vi /etc/ansible/ansible.cfg
uncomment remove # for inventory and sudo_user
adduser ansible  (#ansible user name) do on node 1, and node 2 also
su – ansible
exit 
go to root
Visudo
Add oneline 
ansible ALL=(ALL) NOPASSWD: ALL (same will be done to node 1 and node 2)
save
adduser ansible  (#ansible user name) do on node 1, and node 2 also
vi /etc/ssh/sshd_config   (same will be done to node 1 and node 2)
remove #
Remove # and add #to last
Now , 
service sshd restart
su – ansible
ssh (pivate ip of node 1) repeat for node2 also create file and check

create files1 2 3 
Check the are present in node1 similarly create for node 2 also and check for it
Login without password
$ ssh-keygen
Just enter without password
ssh-copy-id ansible@172.31.90.42  (private ip of any node1 or node2)
Same do for another node also
We see we can login without password
Check for number of hosts added
Playbook
Go to Server
Vi target.yml
To run command
ansible-playbook target.yml  
Vi task.yml
ROLES
STEP1: INSTALL TREE
sudo yum install tree -y
tree
Step 2: make a directory
mkdir -p playbook/roles/webserver/tasks
cd  playbook/
touch roles/webserver/tasks/main.yml
ls
Touch master.yml
Tree
vi roles/webserver/tasks/main.yml

- name: install apache on RedHat
  yum: pkg=httpd state=latest

Httpd will installed installed
$which httpd
$sudo yum remove httpd -y
$vi master.yml
We see again httpd is installed


