# Introduction to Docker
Search and download image. 
```bash
docker search rockylinux  
docker pull rockylinux:9.3  
docker search almalinux  
docker pull almalinux  
``` 
Viewing images.  
```bash
docker images
```
Creating containers with the ability to use the shell.  
```bash
docker create --tty --interactive --name almalinux-lab almalinux  
docker create --tty --interactive --name rockylinux-lab rockylinux:9.3  
```
Launching containers. 
```bash 
docker start rockylinux-lab  
docker start almalinux-lab  
```
How to check the IP addresses of containers in the default bridge network?
```bash
docker network inspect bridge
```

almalinux-lab - 172.17.0.2/16  
rockylinux-lab  - 172.17.0.3/16  
Container shell entry and checking the network connection between containers.  
```bash
docker exec -it rockylinux-lab /bin/bash  
apt-get install iputils-ping -y  
ping 172.17.0.2  
```
![alt text](./assets/network1.png)  

# NGINX
Search and download image nginx. Run a web server.
```bash
docker search nginx
docker pull nginx:1.27.5
docker run -it --rm -d -p 8080:80 --name hello-nginx nginx  
```
Open browser and type http://localhost:8080/ .

![alt text](./assets/network2.png)  

# PostgreSQL
After searching and downloading the image, run PostgreSQL.
```bash
docker run --name hello-postgres --env POSTGRES_PASSWORD=admin --volume postgres-volume:/var/lib/postgresql/data --publish 5432:5432 --detach postgres
```
docker ps -a  
![alt text](./assets/postgre1.png)   
Configuring the connection to the container in pgAdmin.  
![alt text](./assets/postgre2.png)  
Connected to PostgreSQL database inside Docker Container  
![alt text](./assets/postgre3.png)   

Stopping and starting a previously created container

```bash
docker stop hello-postgres
docker start hello-postgres
```