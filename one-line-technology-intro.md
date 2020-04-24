#### Spring cloud Bus
* The Spring Cloud Bus provides feature to refresh configurations across multiple instances.
* This is achieved by connecting all micro-services to a single message broker. Whenever an instance is refreshed, this event is subscribed to all the microservices listening to this broker and they also get refreshed. The refresh to any single instance can be made by using the endpoint /bus/refresh
* [Java in use](https://www.javainuse.com/spring/cloud-stream-bus)

#### Apache Kafka
* open-source stream-processing software platform developed by LinkedIn.
* Apache Kafka is a high throughput distributed messaging system for handling real-time data feeds.
* Apache Kafka Topic, Apache Kafka Broker, Apache Kafka Topic

#### Apache Zookeeper
* Apache Zookeeper is a coordination service for distributed application that enables synchronization across a cluster
* It is used to keep the distributed system functioning together as a single unit, using its synchronization, serialization and coordination goals, selecting leader node.

#### Kubernetes
* Open-source container-orchestration system for automating deployment, scaling and management of containerized applications.

#### Parallelism
* simultaneous execution of processes on a `multiple cores per CPU or multiple CPUs` (on a single motherboard).
#### Concurrency
* Parallelism is achieved on a `single core/CPU` by using scheduling algorithms that divides the CPU’s time (time-slice). Processes are interleaved.

#### Encoding
* Transforms data into another format using a scheme that is publicly available so that it can easily be reversed.
* Encoding is for maintaining data usability and uses schemes that are publicly available.
* To hide meaning, To use less time(when performing calculations), To use less space (for storage or transfer of information)
* Example : UTF8, ASCII, Base64

#### Encryption
* Transforms data into another format in such a way that only specific individual(s) can reverse the transformation.
* Encryption is for maintaining data confidentiality and thus the ability to reverse the transformation (keys) are limited to certain people.
* aes, blowfish, rsa
#### Hashing
* Hashing serves the purpose of ensuring integrity, i.e. making it so that if something is changed you can know that it’s changed. Technically, hashing takes arbitrary input and produce a fixed-length string that has the following attributes:
  * The same input will always produce the same output.
  * It should not be possible to go from the output to the input.
  * Any modification of a given input should result in drastic change to the hash.
* Examples: sha-3, md5 (now obsolete), etc.