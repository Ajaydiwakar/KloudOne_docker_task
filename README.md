# KloudOne_docker_task 

Article link  - :   https://www.linkedin.com/pulse/creating-docker-private-registry-pushpull-image-further-diwakar

Hey Guys , so here we are going to first create a docker private registry ( Secure) and than we will generate a image of a container and will be pushing the same to this private registry .

Now once the above task is done , next we will be pulling the same image and launch a container from it .

Next gonna install httpd and net-tools inside the container

And Finally will be adding a html page inside the path /var/www/html

Let's Begin

First create a directory in you root

#mkdir certs

browse to /etc/docker and you will find a dir names certs.d . Incase if its not present than create it using mkdir

copied the contents of the directory cert/ present in root to /etc/docker/certs.d . It will ask for confirmation . Given yes and proceeded

Restarted the docker service

After creating the tag to the container as

#docker image tag kloudone:v1 repo.docker.local:5000/kloudone:v1

Now if you try to push this image to our local repo it will fail showing No such hosts. Reason behind this is it didnt able to resolve the ip 10.0.2.15 which is our host ip . So need to add this under /etc/hosts

Here The first image kloudone is basically a container image launched of centos .

Now we are going to create a tag for this container image using command shown in screenshot and finally the image is pushed to the private repository

Now removing the image repo.docker.local:5000/kloudone:v1 from our docker images and pulling the same image from the private repo we created.

Now once image is pulled successfully in docker images .

Next we are going to launch a container using the same image and install net-tools and httpd

Start the httpd services using the command

# systemctl start httpd

browse to the path /var/www/html and add a page named index.html with content as " Welcome To KloudOne"

Now check the ip of this container using the command # docker inspect container_name

Go to browser and type 172.17.0.3/index.html

Syntax will be ContainerIp/page_name

Here you will see the page showing as " Welcome to KloudOne" 

