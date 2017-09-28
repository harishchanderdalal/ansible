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
