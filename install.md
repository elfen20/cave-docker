# installation steps for the cave docker containers
install docker, prerequisites and containers to test cave packages.

linux commands can be used on windows subsystem for linux v2 (wsl2)
(atm only preview win10)
## Linux
### install from official repo
at the moment on wsl only ubuntu is supported.
docker is called docker-ce (community edition)el
https://docs.docker.com/engine/install/ubuntu/
 
    sudo usermod -aG docker $USER    

### run
choose a file in the linux folder, e.g. xxx.yml

    docker-compose -f xxx.yml up
you can stop with CTRL-C

if you want do detach use option -d

    docker-compose -d -f xxx.yml up
### stop
This will remove all changes in the containers.
Shutdown the image with

    docker-compose -f xxx.yml down

## Windows
Todo

## useful commands
### wsl
#### ssh
start ssh with:

    sudo service start ssh
connect to localhost.
#### files    
windows files in wsl can be found in

    /mnt/{driveletter}
wsl files in windows can be found in

    \\wsl$
or use the following command in wsl bash:

    explorer.exe .

### docker
list Containers

    docker ps [-a] [-q]
run container

    docker run my_image [-it bash]

kill all running containers with docker 

    docker kill $(docker ps -q)
delete all stopped containers with docker 

    docker rm $(docker ps -a -q)
delete all images with docker 

    docker rmi $(docker images -q)
