# Getting Started with Docker

## Validate the Setup
```
sudo docker version
sudo docker run hello-world
```

## Launching Your First Container
```
sudo docker system events

sudo docker container run centos ps (from another SSH session)
```

## List Containers
Where,
* -l: last run container
* -n xx: last xx number of containers
* -a: all containers (even if they are in ‘stopped’ state
```
sudo docker ps -l
sudo docker ps -n 2
sudo docker ps -a
```
## Images