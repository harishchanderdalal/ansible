## Ansible
- Start
#### Create file with inventory
```
10.0.0.20
10.0.0.30
```

### Test Connection with Inventory HOST
```
ansbile all -i inventory -u vagrant -m ping -k

-i = variable (Inventory File Name)
-u = username
-m = module
-k = password
```

- debug mode
#### v 1st level
#### vv 2nd level
#### vvvv 3rd level
```
ansbile 10.0.0.20 -i inventory -u vagrant -m ping -k -v
```
#### connection using SSH
#### Compile Ping module
#### Make Directory change permission
#### echo ansible and know details
#### put module that compile Directory
#### python binary excute module
#### Remove in last that module

1. connection using SSH
2. Compile Ping module
3. Make Directory change permission
4. echo ansible and know details
5. put module that compile Directory
6. python binary excute module
7. Remove in last that module
