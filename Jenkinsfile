node('master') {
   stage 'Version Control'
        git 'https://github.com/harishchanderdalal/ansiblePlaybookSingleRoleMultiAPP.git'
            echo 'checkout done'

   stage 'Ansible Run'
        ansiblePlaybook colorized: true, inventory: 'environments/development', playbook: 'site.yml', extras: '-e app_name=tmanserver -e build_no=44456', sudoUser: null
            echo 'Ansible Done'    
}
