## Example setup using Docker Swarm

I deployed the frontend - backend example in Docker Swarm hosted on Google Cloud. The swarm is composed of three Virtual Machines, one manager and two workers. The application is accessible at `http://35.228.173.193/`. 

The manager node was initialized and drained to avoid running containers on it:
```
docker swarm init --advertise-addr MANAGER_INTERNAL_IP
docker node update --availability drain manager
```
The worker nodes were added to the swarm: 
```
docker swarm join --token TOKEN MANAGER_INTERNAL_IP:2377
```

Docker images are stored in a registry running on the manager node.
```
docker run -d -p 5000:5000 --name registry registry:2
```

To allow access to the registry, `/etc/docker/daemon.json` was created on each machine.
```
{
  "insecure-registries" : ["MANAGER_INTERNAL_IP:5000"]
}
```

Dockerfiles for frontend, backend and nginx, the docker-compose file and the nginx.conf were copied to the manager node.
Docker images for frontend, backend and nginx were built and uploaded to the registry:
```
docker-compose build
docker-compose push
```

The application was deployed:
```
docker stack deploy --compose-file docker-compose.yml myApp
```
