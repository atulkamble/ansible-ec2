Clone this Code
```
gitr clone https://github.com/atulkamble/ansible-ec2.git
cd ansible-ec2
```
// Check file-tree
tree

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

// Ansible.cfg
```
```
// launch host machines
launch ec2 | host1 | t2 micro | same keypair
launch ec2 | host2 | t2 micro | same keypair

// copy public ip machine and paste it in inventory/host file
```
sudo nano hosts
```
```
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
