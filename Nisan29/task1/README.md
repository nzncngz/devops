
# Linux Lab

Lab environment on below



| VM name       | OS      |  Networking     | 
| ------------- |:------: | -----:          |
| vm1           | centos7 | 192.168.135.142 |


# Prerequisites

    Vagrant        2.2.15 
    Virtualbox     6.1.18 
    Centos 7
    
creating a virtual machine(centos 7 OS) and updating with vagrant on virtualbox
add second disk(size 10GB) on vm

{% filename %}adduser nazan.cengiz{% endfilename %}
$ 
$ passwd  nazan.cengiz
$ echo "nazan.cengiz  ALL=(ALL:ALL) ALL" >>  /etc/sudoers
$ usermod -aG sudo nazan.cengiz

before add new disk
[nazan.cengiz@localhost ~]$ lsblk 
NAME   MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
sda      8:0    0  40G  0 disk 
└─sda1   8:1    0  40G  0 part /


#later adding new disk

[nazan.cengiz@localhost ~]$ lsblk 
NAME   MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
sda      8:0    0  40G  0 disk 
└─sda1   8:1    0  40G  0 part /
sdb      8:16   0  10G  0 disk

$ su nazan.cengiz
$ sudo fdisk /dev/sdb
$ sudo mkdir bootcamp
$ sudo mkfs.ext4 /dev/sdb1
$ sudo mount /dev/sdb1 bootcamp/
$ sudo nano /etc/fstab
$ sudo /dev/sdb1    /home/nazan.cengiz/bootcamp/    ext4  defaults 0 0
$ sudo mount -a
$ reboot
$ su nazan.cengiz
$ cd /opt
$ sudo mkdir bootcamp ; sudo touch bootcamp.txt  

$ sudo echo "merhaba trendyol" >> bootcamp.txt

$ sudo su

$ cd /home/nazan.cengiz 

$ find / -iname "bootcamp.txt" -exec mv {} /home/nazan.cengiz/bootcamp/ \;

###show file 

[root@localhost bootcamp]# pwd
/home/nazan.cengiz/bootcamp

[root@localhost bootcamp]# ls
bootcamp.txt  lost+found
