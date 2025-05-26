## Search and download image  
docker search rockylinux  
docker pull rockylinux:9.3  
docker search almalinux  
docker pull almalinux  
## Viewing images  
docker images  
## Creating containers with the ability to use the shell  
docker create --tty --interactive --name almalinux-lab almalinux  
docker create --tty --interactive --name rockylinux-lab rockylinux:9.3  
## Launching containers  
docker start rockylinux-lab  
docker start almalinux-lab  
## Container shell entry and exit  
docker exec -it almalinux-lab /bin/bash  
exit  
docker exec -it rockylinux-lab /bin/bash  
exit  