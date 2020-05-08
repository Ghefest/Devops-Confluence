# DevOps Exam

## Description:

Create 3 VMs using single Vagrantfile. Use hostnames (/etc/hosts).
VM1 _proxy_ (OS Cenos7):
Install and configure ngnix reverse proxy server with SSL/TLS termination.
VM2 _app_ (OS Ubuntu 18.04):
[Download distro](http://yoko.ukrtux.com:8899/atlassian-confluence-7.1.0-x64.bin) and install and configure Atlassian Confluence (trial).
Use downloaded distro instead of direct download to save the time and network traffic.
VM3 _db_ (OS Ubuntu 18.04):
Install and configure docker host and MySQL server powered on it.
Configure Internet access to your mini-project using ssh reverse-proxy via yoko.ukrtux.com host.
