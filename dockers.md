Docker service start
Docker build <path of docker file> -t <name of image>
docker run -p 80:80 image-name

#### ECS cluster type
* Fargate
  * Serverless. You do not need to manage ec2 instance of it. AWS does it for you.
  * Not avialable in all region
* EC2
  
#### Terminology of ECS
* Image
* Repository
* Task Definition
  * Parameter for building and running container like which image to use, CPU, memory etc
* Service
  * Maintain the number of container specified in task definition
  * Its like watch dog. If your container dies for some reason the service will create a new container.
* Cluster
  * Integrate different pieces of puzzle. Image, Repository, Task definition, service etc


