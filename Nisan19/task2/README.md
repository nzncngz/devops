
# Ansible Docker Lab

Lab environment on below



| VM name       |   Role                             | OS      |  Networking     | 
| ------------- |   :-------------:                  | -----:  | -----:          |
| control       |   Ansible Host                     | ubuntu | 192.168.135.140 |
| wordpress     |   Wordpress, Mysql(MariaDB), Nginx | ubuntu | 192.168.135.141 |


All applications run on the virtual machine as a container.



# Prerequisites

    Vagrant        2.2.15 
    Virtualbox     6.1.18 
    Docker         20.10.6
    Docker-compose 1.25
 
# Installation

``` bat  
$ git clone https://github.com/nzncngz/devops.git
```

vm creating 

``` bat  
$ vagrant up &
$ cd devops/Nisan29/task/ansible
```

docker role with ansible galaxy

``` bat
$ ansible-galaxy install -r requirements.yml
$ ansible-galaxy install -r playbooks/install-docker-with-role.yml

```
all application run  

``` bat  
$ ansible-playbook -i hosts wordpress.yml
```


# Role Variables

This role has multiple variables. The descriptions and defaults for all these variables can be found in the roles/wordpress-docker/tasks folder in the following files:

| Name           |   Description                         
| -------------  |   :-------------:          
| main.yml       |   deploy WordPress Nginx virtual host  

roles/docker/tasks folder in the following files:

| Name           |   Description                         
| -------------  |   :-------------:          
| main.yml       |   install docker,docker compose and current user add to docker group    

roles/docker/tasks folder in the following files:

| Name           |   Description                         
| -------------  |   :-------------:          
| wordpress.yml  |   via file wordpress enviroment variable


# Result
In incoming request if bootcamp = devops header it redirects to "Welcome Devops" static page

![Vertical](https://github.com/nzncngz/devops/blob/main/Nisan29/task2/results/check_header_with_postman.png)

# Reference

https://github.com/bilalcaliskan/vagrant-ansible-lab/

https://www.happycoders.eu/devops/ansible-tutorial-setup-docker-mysql-wordpress/



