
# Ansible Docker Lab

Lab environment on below



| VM name       |   Role                    | OS      |  Networking     | 
| ------------- |   :-------------:         | -----:  | -----:          |
| control       |   Ansible Host            | centos7 | 192.168.135.140 |
| wordpress     |   Wordpress, Mysql, Nginx | centos7 | 192.168.135.141 |


All applications run on the virtual machine as a container.



# Prerequisites

    Vagrant        2.2.15 
    Virtualbox     6.1.18 
    Docker         20.10.6
    Docker-compose 1.25
 
# Installation

git clone https://github.com/nzncngz/devops.git

<!-- vm creating --> 

vagrant up &

cd devops/Nisan29/task/ansible

<!-- all application run  --> 

ansible-playbook -i hosts wordpress.yml

# Role Variables

This role has multiple variables. The descriptions and defaults for all these variables can be found in the roles/wordpress-docker/tasks folder in the following files:

| Name           |   Description                         
| -------------  |   :-------------:          
| main.yml       |   deploy WordPress Nginx virtual host           

