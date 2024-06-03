Clone this Code
```
gitr clone https://github.com/atulkamble/ansible-ec2.git
cd ansible-ec2
```
// Check file-tree
tree
```
.
├── ansible.cfg
├── aws
│   └── aws_keys
│       └── ansible.pem
├── inventory
│   └── hosts
├── playbooks
│   └── ping.yml
└── roles
```
// Ansible.cfg
```
[defaults]
inventory = ./inventory
remote_user = ec2-user
private_key_file= aws/aws_keys/ansible.pem
host_key_checking=False
retry_files_enabled=False

[privilege_escalation]
become = true
become_method = sudo
become_user = root
become_ask_pass = false
```
// launch host machines
launch ec2 | host1 | t2 micro | same keypair
launch ec2 | host2 | t2 micro | same keypair

// copy public ip machine and paste it in inventory/host file
```
sudo nano hosts
```
```
[all]

[webservers]
13.201.104.118

[dbservers]
65.2.69.215

[dev]
13.201.104.118

[qa]
65.2.69.215

[test]
65.2.69.215
```

// copy your keypair and save it  and  then paste path of it in ansible.cfg. 

// sign in as root | Server-machine
```
sudo -i passwd
// enter password 2 times
su
```
// then try for following commands
```
ansible all --list-hosts
ansible webservers --list-hosts
ansible dbservers --list-hosts
ansible dev --list-hosts
ansible test --list-hosts
ansible qa --list-hosts

// check host connection
```
ansible all -m ping
```
