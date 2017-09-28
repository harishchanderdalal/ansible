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
