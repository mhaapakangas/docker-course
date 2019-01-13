## Why and when to use Kubernetes

Docker allows packaging and distribution of containerized applications. If an application consists of multiple containers communicating with each other, a tool for orchestrating the containers becomes necessary. It should take care of starting containers, connecting them with each other and scaling them. Docker provides Docker Swarm for this purpose, and another popular tool is Kubernetes, which was originally developed by Google. 

Because Docker Swarm is integrated into the Docker ecosystem, Docker Compose and Docker CLI can be used to define containers. Kubernetes on the other hand has its own container definition language, which means that Docker Compose files need to be rewritten. As a result, Docker Swarm orchestration platform is easier to adopt. 

Docker Swarm is limited to Docker functionalities, which makes it simpler to install than Kubernetes. Kubernetes however is not tied to any particular tool but can be extended via plugins. Using storage as an example, Docker Swarm only supports Docker Volumes while Kubernetes can also use other technologies, such as AWS or Google Cloud storage solutions.

Kubernetes also offers built-in logging and monitoring, whereas Docker Swarm requires third-party tools. Monitoring the system resources allows Kubernetes to adapt the server loads by autoscaling the applications up or down. On the other hand, Docker Swarm only supports manual scaling of applications natively.

In conclusion, Docker Swarm may be a good candidate for a development environment because it's lightweight and easy to set up. In a production environment on the other hand, Kubernetes is a better choice thanks to its flexibility and built-in logging, monitoring and autoscaling functionalities.

#### Sources
* https://www.sumologic.com/blog/devops/kubernetes-vs-docker/
* https://hackernoon.com/kubernetes-vs-docker-swarm-a-comprehensive-comparison-73058543771e
* https://kubernetes.io/docs/concepts/storage/volumes/
