FROM centos:latest

MAINTAINER diwakarajay44@gmail.com

RUN yum install httpd -y
RUN yum install net-tools -y
RUN yum install git -y
COPY /root/devopsal1/style.css  /var/www/html
COPY /root/devopsal1/last.jpg  /var/www/html
COPY /root/devopsal1/transparentlogin.html /var/www/html

EXPOSE 80

CMD echo Container created 
CMD ["Open in Browser your container_ip/login.html"]

