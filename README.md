# Automation-using-ansible
The project involves deploying a simple PHP script on webservers running *Nginx* and deploying a *HAProxy* load balancer using **Ansible**

---
## Nginx
Nginx is a popular open-source web server which can also be used as a reverse proxy,load balancer and HTTP cache.The project involves deploying nginx on three webservers.The project also requires the installation of PHP-FPM ver-7.4 as nginx doesn't have a built-in support for processing PHP files.The webservice is deployed on webservers devices devA,devB and devC as defined in the hosts file.The nginx documentation for configuration can be accessed [here](https://nginx.org/en/docs/beginners_guide.html).

## HAProxy
HAProxy stands for High Availability Proxy which is a popular open-source TCP/HTTP load balancer whose main aim is to distribute the workflow across multiple servers and improve the reliability of the environment.The load balancer is deployed on devhaproxy device as specified in the hosts file.The configuration parameters of the HAProxy can be accessed [here](http://www.haproxy.org/download/2.2/doc/configuration.txt). 

## Bastion Host
Bastion host,also called as a jump server,is a server used to manage access to a private network from an external network.

---
* The project requires a properly configured SSH config file to be used by the Ansible controller.A SSH connection is established to the private network of devices through the Bastion host.

* The service is accessed through the load balancer which then communicates with the backed servers using roundrobin load-balancing algorithm for delivering the service. 

---
To run the playbook use the command:`ansible-playbook -i hosts site.yaml`
