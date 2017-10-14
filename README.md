# Ansible
- What is ansible Diagram
![what_is_ansible](https://user-images.githubusercontent.com/22466745/31009645-d9c434a6-a525-11e7-8351-091d10752f5a.PNG)

- How ansible works
![ansible_works](https://user-images.githubusercontent.com/22466745/31009780-3f096908-a526-11e7-948b-1ec211939974.PNG)

## Vagrant with ansible
- Vagrantfile.md

## Ansible Hands On
- ansible.md

## Roles Structure
```
mkdir -p project && touch production staging site.yml ansible.cfg && mkdir -p group_vars host_vars library filter_plugins && mkdir -p roles/common/{tasks,handlers,templates,files,vars,defaults,meta} && touch roles/common/{tasks,handlers,templates,files,vars,defaults,meta}/main.yml
```
