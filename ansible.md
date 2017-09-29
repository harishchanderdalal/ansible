# Ansible
- Start

### Create file with inventory
```
10.0.0.20
10.0.0.30
```

## Test Connection with Inventory HOST
```
ansbile all -i inventory -u vagrant -m ping -k


Parameter Use in CMD:
* -i = variable (Inventory File Name)
* -u = username
* -m = module
* -k = password
```

- debug mode
1. v 1st level
2. vv 2nd level
3. vvvv 3rd level

```
ansbile 10.0.0.20 -i inventory -u vagrant -m ping -k -v
```
- Process Work

1. connection using SSH
2. Compile Ping module
3. Make Directory change permission
4. echo ansible and know details
5. put module that compile Directory
6. python binary excute module
7. Remove in last that module

## AD HOC
```
ansbile all -i inventory -u vagrant -m command -a "/usr/sbin/reboot"
ansbile all -i inventory -u vagrant -m command -a "/usr/sbin/ yum update -y"
```

## Ansbile Inventory Example 1
```
ansible datacenter -i inventory -m ping
```
- inventory
```
web1 ansible_ssh_host=10.0.0.20
db1 ansible_ssh_host=10.0.0.30

[webservers]
web1

[dbservers]
db1

[datacenter:children]
webservers
dbservers

[datacenter:vars]
ansible_ssh_user=vagrant
ansible_ssh_pass=vagrant
```
