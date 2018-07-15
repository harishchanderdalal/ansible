# Middle office

Ansible Playbook for diffrent apps of middle office.

## Ansible 3.0.0.0
* AWS
    * RHEL 7
* VAGRANT
    * CENTOS 7

## Playbook Nodes
* Vagrant
    * Solaris
    * CENTOS 7
* AWS
    * RHEL 7

## Playbook Core Steps
1. Download Deploy Package
2. Stop Process
3. Deploy Package
4. Start Service

## Roles
1. middleoffice

## Dependencies
1. JAVA
2. Ansible 3.0.0.0

## Variables
### environments/ENVIRONMENT
``` 
[dev_ppl]
0.0.0.0

[dev_tman]
1.1.1.1
```

### roles/APPNAME/vars
``` 
1. BUILD:  Build number that we are passsing over command line
2. BUILD_FILE: The actual zip file name
3. SVN_EXPORT_DIR: Temporary download diretory
4. TEMP_DIR:  Temporary directory for downloading and cross checking the build confirmation file
5. log_file_ansible: The log file creating on Ansible machine for sending to distribuition list
6. java_loc: Java location for symlink 
```

### group_vars/ENVIRONMENT_APPNAME.yml
``` 
1. JAVA_LOC_ORIG: "Original java location"
2. PROCESS_NAME : "Need to replace with process name"
3. APP_PROGRAM_FILE: Jar file name for running fuser command, ex: fuser /opt/tomcat8/bin/bootstrap.jar
4. svn_trunk_url: The main SVN URL
5. APP_PORT: APplication port  for checking the port binding status
6. HOME: Application home directory, ex: /local/apps/tman   
7. LOG_DIR: Ansible logs of deployment
8. BUILD_CONFIRMATION_FILE: File 
9. APP_OWNER: application owner
10. APP_GROUP: application group
11. var_file_name:  The file that we need to store all the variables during the deployment
12. DIST_LIST_success: email address to which we need to send the successful deployment mails
13. DIST_LIST_failed: email address to which we need to send the failure deployment mails
14. MAIL_PORT: Mail port 
```

### deploy.yml
``` 
remote_user: EXAMPLE
```

# RUN Playbook
```
EXAMPLE -
ansible-playbook --extra-vars '{"app_name":"tmanserver","build_no":"44456"}' site.yml -i environments/dev  
```

License
-------
UST Global india pvt ltd
