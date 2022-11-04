# Home-Kubernetes-Configuration
    The configuration I'm using updated as I start to understand how the Kubernetes eco-system works.
    
[[__TOC__]]

<!-- GETTING STARTED -->
## Getting Started

## Installed 3 PIs with Raspberry PI OS Lite (64 bit) 
k8s will only run on 64 bit OSs

Configured DNS on my router - when adding a new node to the cluster the process checks the DNS lookuyp matches the hostname.

`sudo apt install vim unattended-upgrades snapd`  
because vim-tiny does odd things when you use the arrow keys  
and I do not remember to update the OS often enough  

### added the path for snap
by adding the following to the bottom of each `~/.bashrc` file  
`export PATH=$PATH:/snap/bin`


--

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
### Configure the memory Control Group
- I believe that this is required by microk8s, possibly any kubernetes install
Cgroups allow you to allocate resources — such as CPU time, system memory, network bandwidth, or combinations of these resources
`sudo vim /boot/cmdline.txt`  
`cgroup_enable=memory cgroup_memory=1`  

### install microk8s
`sudo snap install microk8s --classic`  

add user to the microk8s group
```
sudo usermod -a -G microk8s keith
sudo chown -f -R keith ~/.kube
newgrp microk8s
```

on PI-1
`add-node`
pasting the result to PI-2

on PI-1
`add-node`
pasting the result to PI-3

I got error messages along the line of  
`Connection failed. The hostname (pi4-kube-n) of the joining node does not resolve to the IP`  
I found dropping the wlan0 interface so that only the eth0 interfce could be seen helped

`sudo ifconfig wlan0 down`

### And now for something useful?


## License
Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>



