## install microk8s
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
