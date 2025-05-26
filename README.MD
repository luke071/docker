docker search rockylinux
docker pull rockylinux:9.3
docker search almalinux
docker pull almalinux
docker images
docker create --tty --interactive --name almalinux-lab almalinux
docker create --tty --interactive --name rockylinux-lab rockylinux:9.3
docker start rockylinux-lab
docker start almalinux-lab 
docker exec -it almalinux-lab /bin/bash
exit
docker exec -it rockylinux-lab /bin/bash
exit