
# Home Kubernetes Configuration
    The configuration I'm using updated as I start to understand how the Kubernetes eco-system works.
    
[Installing the Cluster](https://github.com/keithlee-co-uk/home-kubernetes-configuration/blob/master/docs/Installing-the-Cluster.md)   
[Install (microk8s) Kubernetes](https://github.com/keithlee-co-uk/home-kubernetes-configuration/blob/master/docs/Install-Kubernetes.md)  

## Objetives
To have running a:  
- Resilient Dashboard  
- Resilient DNS  
- Resilient Monitoring  

### Resilient - meaning a power outage on one or two nodes the service remains up.  
This will mean we want a Service or maybe to load balance the end-points - not sure yet.  

---
[Ref](https://ubuntu.com/tutorials/install-a-local-kubernetes-with-microk8s#3-enable-addons)  
### Dashboard Install
`microk8s enable dns dashboard`  


### Metallb install
Following the [MetalLb Installation instructions](https://metallb.universe.tf/installation/)  
Intended Network:  
Network:   192.168.0.192  
IP range:  192.168.0.193 - 192.168.0.222  
Broadcast: 192.168.0.223  

![Logo](https://github.com/keithlee-co-uk/home-kubernetes-configuration/blob/master/images/Kubernetes-Logo.wine.png)


## License
Distributed under the MIT License. See [LICENSE.txt](https://github.com/keithlee-co-uk/home-kubernetes-configuration/blob/master/LICENSE.txt) for more information.

<p align="right">(<a href="#top">back to top</a>)</p>



