
# Linux Lab

Lab environment on below



| VM name       | OS      |  Networking     | 
| ------------- |:------: | -----:          |
| vm1           | centos7 | 192.168.135.142 |


# Prerequisites

    Vagrant        2.2.15 
    Virtualbox     6.1.18 
    Centos 7
    
# Linux Commands  

creating a virtual machine(centos 7 OS) and updating with vagrant on virtualbox
add second disk(size 10GB) on vm

``` bat
$ sudo -i
$ adduser nazan.cengiz; passwd  nazan.cengiz; echo "nazan.cengiz  ALL=(ALL:ALL) ALL" >>  /etc/sudoers; usermod -aG root nazan.cengiz; su nazan.cengiz

```

before add new disk
``` bat  
$ lsblk 
```
![Vertical](https://github.com/nzncngz/devops/blob/main/Nisan29/task1/results/before_add_disk.png)


#later adding new disk
``` bat  
$ lsblk 
```
![Vertical](https://github.com/nzncngz/devops/blob/main/Nisan29/task1/results/later_disk_adding.png)

``` bat  
$ su nazan.cengiz
$ sudo fdisk /dev/sdb; sudo mkdir bootcamp; sudo mkfs.ext4 /dev/sdb1; sudo mount /dev/sdb1 bootcamp/

$ sudo nano /etc/fstab
/dev/sdb1    /home/nazan.cengiz/bootcamp/    ext4  defaults 0 0
$ sudo mount -a; sudo reboot

$ su nazan.cengiz
$ cd /opt; sudo mkdir bootcamp ; cd bootcamp; sudo touch bootcamp.txt; sudo chown nazan.cengiz: bootcamp.txt; sudo echo "merhaba trendyol" >> bootcamp.txt
$ sudo echo "merhaba trendyol" >> bootcamp.txt

$ sudo chown nazan.cengiz: bootcamp/; sudo find / -iname "bootcamp.txt" -exec mv {} /home/nazan.cengiz/bootcamp/ \;

``` 

#show mounted and file

