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
