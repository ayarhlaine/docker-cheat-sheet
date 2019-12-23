## Docker Cheat Sheet
#### Check Docker Version 
`docker version`
#### Getting Help for `docker container run` command
`docker container run --help`
#### Show Running Docker Containers
`docker ps` or `docker container ls`
#### Show All Docker Containers
`docker ps -a`\
-a = all \
-f = filter \
-q,--quiet = only display numeric id \
-s = display size 

#### Show Docker Images
`docker images`
#### Remove Docker Image or Images
`docker rmi imageid` or `docker image rm imageid`
#### Pull Image to local machine
`docker pull imagename`\
Eg : `docker pull nginx`
#### Pull and Run Nginx Docker Container (Foreground)
`docker container run -it -p 8081:80 nginx` \
Note: \
-it = interactive \
-p = publish = publish container port to the host
#### Pull and Run Nginx Docker Container (Background)
`docker container run -d -p 8081:80 --name mynginx nginx` \
Note: \
-it = detach \
-p = publish = publish container port to the host \
--name = name to container
#### Docker Run Container with environment variables
`docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag` \
-e = env 
#### Docker Run with Bind Mount
`docker container run -d -p 8083:80 -v $(pwd):/usr/share/nginx/html --name mynginx nginx`
#### Docker Build with Dockerfile
`docker build -t ayarhlaine/nginx-website .` \
``.`` = current directory = location of Dockerfile
#### Run command in running container
`docker exec -it mynginx bash`
#### Remove All Images 
`docker rmi -f $(docker images -a -q)`
#### Remove All Containers
`docker rm -f $(docker ps -aq)`