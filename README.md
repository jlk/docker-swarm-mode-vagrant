# docker-swarm-mode-vagrant

This project is to simplify the setup for [Docker Swarm Mode][1] with Vagrant.

It will automatically create a swarm cluster of Docker, and the first node will be the manager and others will be worker.

For ease of use, network connections to TCP port 8080 (such as http://localhost:8080) are forwarded to the master node. Swarm mode's mesh routing will forward this traffic to any container in the cluster with published service on port 8080.

# Branches
As I use this project in different locations, I'm creating separate branches with different configurations:

* master: Used in my [linux.com article on Swarm Mode service discovery](https://www.linux.com/blog/event/open-networking-summit/2017/3/how-service-discovery-works-containerized-applications-using-docker-swarm-mode)
* traefik\_proxy: Used in another linux.com article on how to discover services outside a Docker Swarm Mode cluster.

# Usage

For user in China, you can uncomment the following line in "provision-manager.sh", "provision-worker.sh" for using the [Aliyun Mirrors](http://mirrors.aliyun.com) to speed up the package installation/update.

    #USE_ALIYUN_MIRROR=1


This application is available in the form of a Docker image that you can run as a container by executing this command:
    
    vagrant up



# Play with it

Run the Swarm manager 

	vagrant ssh node-1


```
docker info
docker node ls
```

# References
[Swarm mode overview][1]

[1]: https://docs.docker.com/engine/swarm/
