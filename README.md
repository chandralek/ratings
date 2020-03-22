# Ratings Service.

Ratings service is developed on PHP. PHP will not run on itself and it requires a web server.

Apache HTTPD server is more famous and this app is already provided by developer in HTTPD conifguration rather than NGINX. So we choose the same to install and configure the web server with PHP.

1. Install Apache HTTPD Web Server.

```
# yum install httpd -y 
# yum install  http://rpms.remirepo.net/enterprise/remi-release-7.rpm -y 
# yum -y install yum-utils
# yum-config-manager --enable remi-php73
# yum -y install php php-opcache php73-php-pdo composer
```

