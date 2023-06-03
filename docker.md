```
$ docker run <image> -> creates a new container every time
$ docker start <container_id/name> 
$ docker stop <container_id/name>

$ docker run --detach --name web nginx:latest
$ docker run -it --link web:web --name web_test busybox:latest /bin/sh    (-it)
$ docker create <image> -> only creates container, does not start it

$ docker rename webid webid-old

$ docker logs web
$ docker exec <docker_ip/name> <command> -> executes a command

$ docker ps -a
$ docker images

$ docker inspect --format "{{.State.Running}}" wp

$ docker rm web
$ docker rmi web

$ docker search postgres

$ docker pull busybox:latest
$ docker save -o myfile.tar busybox:latest
$ docker load –i myfile.tar

$ docker build -t dia_ch3/dockerfile:latest ch3_dockerfile

$ docker run -d --volume /var/lib/cassandra/data --name cass-shared alpine echo Data Container
$ docker run -d --volumes-from cass-shared --name cass1 cassandra:2.2
$ docker run –it --rm --link cass1:cass cassandra:2.2 cqlsh cass
$ docker volume create rosemary
$ docker volume ls

$ docker run -d -P --name ch6_wordpress \
--memory 512m \
--cpu-shares 512 \
--user nobody \
--cap-drop net_raw \
--link ch6_mariadb \
wordpress:4.1

$ docker -it --rm --device /dev/video0:/dev/video0 ubuntu:latest ls -al /dev

$ docker run --name hw_container ubuntu:latest touch /HelloWorld
$ docker commit hw_container hw_image
$ docker rm -vf hw_container
$ docker run --rm hw_image ls -l /HelloWorld
$ docker diff <container>
$ docker history <image>
```
