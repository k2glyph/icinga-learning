# Icinga-Learning
Setup ubuntu server and install icinga on LAMP stack.
## Steps to install LAMP Stack:
### Install Apache2
`sudo apt-get update`
`sudo apt-get install apache2`
`sudo ufw app list`
`sudo ufw app info "Apache Full"`
<http://your_server_IP_address>
### Install Mysql
`sudo apt-get install mysql-server`
`mysql_secure_installation`
### Install Php
`sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql`
`sudo systemctl restart apache2`
### Install Icinga2
`sudo apt-get install icinga2 icinga2-ido-mysql`
`sudo icinga2 feature enable ido-mysql command`
`sudo systemctl restart icinga2`
`sudo systemctl status icinga2`
### Install Icingaweb2
`sudo apt-get install icingaweb2`
`sudo systemctl restart apache2`
### Get Token from icinga-cli
`sudo icingacli setup token create`
### Browse
<https://icinga-master.example.com/icingaweb2>
## Sample Host to be added in /etc/icinga2/conf.d/hosts.conf
```
object Host "SonarQube" {
  import "generic-host"
  address= "sonarqube.com"
  vars.http_vhosts["http"]= {
   http_uri = "/"
  }
  vars.notification["mail"]= {
   groups =["icingaadmins"]
  }
}
```
`sudo systemctl restart icinga2`
