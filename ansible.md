# Ansible
- What is ansible Diagram
![what_is_ansible](https://user-images.githubusercontent.com/22466745/31009645-d9c434a6-a525-11e7-8351-091d10752f5a.PNG)

- How ansible works
![ansible_works](https://user-images.githubusercontent.com/22466745/31009780-3f096908-a526-11e7-948b-1ec211939974.PNG)

## Roles Structure
```
mkdir -p project && touch production staging site.yml ansible.cfg && mkdir -p group_vars host_vars && mkdir -p roles/common/{tasks,handlers,templates,files,vars,defaults,meta} && touch roles/common/{tasks,handlers,templates,files,vars,defaults,meta}/main.yml
```
## Inventory

- Create inventory

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

## Ansbile Inventory 
- Global Variable ALL With Keygen
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

[all:vars]
ansible_ssh_user=vagrant
ansible_ssh_private_key_file=~/.vagrant.d/insecure_private_key
```

- Global Variable ALL with Plan Text UserName Password
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

[all:vars]
ansible_ssh_user=vagrant
ansible_ssh_pass=vagrant
```

- Global Variable with Group
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


## Inventory Manage
![env inventory](https://user-images.githubusercontent.com/22466745/31010986-5caedad4-a52a-11e7-8c47-71b005652b0c.PNG)

- Priority
1. (Host_Vars) Hostname
2. (Group_vars) GroupName
3. (Group_Vars) All

