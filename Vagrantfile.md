## VAGRANT

- vagrant file
```
Vagrant.configure(2) do |config|
	
	config.vm.define "ansible" do |ansible|
		ansible.vm.box = "ubuntu/trusty64"
		ansible.vm.hostname = "ansible"
		ansible.vm.network "private_network", ip:10.0.0.10"
	end

	config.vm.define "web" do |web|
		web.vm.box = "nrel/CentOS-6.5-x86_64"
		web.vm.hostname = "web"
		web.vm.network "private_network", ip: "10.0.0.20"
		web.vm.network "forword_port", guest: 80, host: 8080
	end

	config.vm.define "db" do |db| 
		web.vm.box = "nrel/CentOS-6.5-x86_64"
		web.vm.hostname = "db"
		web.vm.network "private_network", ip: "10.0.0.30"
	end

end
```

- VAGRANT RUN AND TEST
```
vagrant up
vboxmanage list runningvms
```

## VAGRANT ANSBILE - UBUNTU
```
vagrant ssh ansible
sudo apt-get install ansible -y
```

## VAGRANT WEB - CENTOS
```
sudo ssh web
sudo yum install epel-release -y
sudo yum install ansible -y
```

## VAGRANT DB COMPILE UBUNTU
```
vagrant ssh db
sudo yum install gcc -y
sudo yum install python-setuptools -y
sudo easy_install pip -y
sudo yum install python-devel -y
sudo pip install ansible -y
```

## VAGRANT DB COMPILE Ubuntu
```
sudo apt-get update
sudo apt-get install -y software-properties-common
sudo apt-get install -y python-setuptools python-dev libffi-dev libssl-dev git sshpass tree
sudo easy_install pip
sudo -H pip install cryptography
sudo -H pip install ansible==2.1.1.0 
```
## VAGRANT COMPLILE CENTOS7/REDHAT7
```
sudo yum update
sudo yum install python-pip python-wheel python-devel
sudo yum install gcc libffi-devel
sudo pip install ansible==2.1.1.0
ansible --version
```

