#### ECS 
* ECS is container management service. Start, stop and update your containers
  * Scalable- add or remove container instances without any downtime
  * Secure: Security is defined by roles created in IAM. Provide granual permission to adminstration to ecs resources.
  * Reliable
  * Fast
#### Cluster launch type
* server less- Farget
 * When using the Fargate launch type with tasks within your cluster, Amazon ECS manages your cluster resources
 * Run in aws managed infrastructure. 
 * No EC2 instance are required. No need of provisioning of server.
 * No need to apply security patches 
 * Scalable: Scaling in and out does not require adding or removing VM. Just need to modify the culture of run number of task.
 * Any task running uses ephemeral storage. Once the task is terminated the storage used to by task is also deleted
 * Isolation boundary: There is no such thing like sharing memory, network, cpu with any other running task.
 * Not available in all region
 * Variable short running task
 * Costlier
 
* EC2
 * When using the EC2 launch type, then your clusters are a group of container instances you manage.
 * An Amazon ECS container instance is an Amazon EC2 instance that is running the Amazon ECS container agent.
 * useCase: Predictable and long running task
 * Cheaper

#### ECS Cluster
* Logical grouping of container instances
* You can use Amazon ECS to schedule the placement of containers across your cluster based on your resource needs, isolation policies, and availability requirements. 
* Amazon ECS eliminates the need for you to operate your own cluster management and configuration management systems or worry about scaling your management infrastructure.

#### ECS Cluster component
* Image
* Repository
* Task definitions: Used to run docker images. Contains Parameters for docker container, docker images to use, CPU, memory
* Services : maintain the number of instances specified in task definition.

* ECS Cluster integrate all the different pieces of puzzle. These pieces of puzzle are docker image, repo, task definition, service.
 
#### General Point
* Memory and cpu can be defined at container level. But in most of cases if it defined at task level.
* Tag are basically version of images. Default:LATEST indicate this was the last modified version of this image.  


#### Task definition
* Task definition name
* Task role: Role used by task definition to interact with other services. 
* Task execution IAM role: This is used by task to pull container images and publish container logs into cloudwatch on your behalf.
* N/W Mode: 
  * AWSVPC : Provide n/w interface, an ip address to every task the task definition will be running. 
  
#### Services
* Act as a watchdog for your task. maintain the number of instances specified in task definition.
* When used with ELB it spread load across all the tasks
* ECS Service scheduler
  * Replica
    - Maintain the number of desired task all time
    - Used by farget launch type
  * Daemon
    - Used by EC2 launch type
    - One task per container instance
    - It as task fail it will wait until a new a new instance meeting the cluster requirement is added to the cluster before launching the task on this new container instance.
#### Task scheduling
* Fixed interval(GUI)
* CRON expression(More complex)

#### Network mode
* Awsvpc: Every container get an ENI. So there is no bottle-nack of host port to container port mapping. Each container can have its own security group because each container get its own ENI.
* Bridge: This come from docker background. In Bridge ECS utilise docker build in virtual network which run inside each container instance.
* None: Disable all networking. No connectivity with external n/w as well as other container.
* Host: It is somewhat similar to Bridge but here it bypass the docker build in virtual network and directly map container port to the host port. This improve performance.
* The host and awsvpc network modes offer the highest networking performance for containers because they use the Amazon EC2 network stack instead of the virtualized network stack provided by the bridge mode.

#### How it all work
* EC2, Docker agent and ecs agent


