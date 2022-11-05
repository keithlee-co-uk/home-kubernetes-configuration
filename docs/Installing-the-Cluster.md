
# Installing the OS and configuring hardware settings ready for microk8s

## Installed 3 PIs with Raspberry PI OS Lite (64 bit) 
```diff
NOTE
- k8s will only run on 64 bit OSs
```

Configured DHCP on my router - to ensure I get consistant IPs for the cluster.

`sudo apt install vim unattended-upgrades snapd`  
because vim-tiny does odd things when you use the arrow keys  
and I do not remember to update the OS often enough  

### added the path for snap
by adding the following to the bottom of each `~/.bashrc` file  
`export PATH=$PATH:/snap/bin`


--  
[Ref](https://linuxhint.com/enable-disable-unattended-upgrades-ubuntu/)  
### Configuring unattended-upgrades
```
sudo dpkg-reconfigure -f noninteractive unattended-upgrades
sudo vim /etc/apt/apt.conf.d/50unattended-upgrades
```

`Unattended-Upgrade::Automatic-Reboot "true";`  

#### Staggering the updates so we never loose the whole cluster   
`Unattended-Upgrade::Automatic-Reboot-Time "01:00"; # on PI-1`  
`Unattended-Upgrade::Automatic-Reboot-Time "02:00"; # on PI-2`  
`Unattended-Upgrade::Automatic-Reboot-Time "03:00"; # on PI-3`  

--  
[Ref](https://microk8s.io/docs/install-raspberry-pi)  
### Configure the memory Control Group
- I believe that this is required by microk8s, possibly any kubernetes install
Cgroups allow you to allocate resources — such as CPU time, system memory, network bandwidth, or combinations of these resources
`sudo vim /boot/cmdline.txt`  
`cgroup_enable=memory cgroup_memory=1`  

### Additional Package
`sudo apt install linux-modules-extra-raspi`  
