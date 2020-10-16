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
* Encoding is the process of transforming data so that it may be transmitted without danger over a communication channel or stored without danger on a storage medium. For instance, computer hardware does not manipulate text, it merely manipulates bytes, so a text encoding is a description of how text should be transformed into bytes. Similarly, HTTP does not allow all characters to be transmitted safely, so it may be necessary to encode data using base64 (uses only letters, numbers and two safe characters).

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

#### DHCP(Dynamic Host Configuration Protocol)
* DHCP server dynamically assigns an IP address and other network configuration parameters to each device on a network so they can communicate with other IP networks.
* A DHCP server enables computers to request IP addresses and networking parameters automatically from the Internet service provider (ISP).

#### (IETF)Internet Engineering Task Force
* The Internet Engineering Task Force is an open standards organization, which develops and promotes voluntary Internet standards, in particular the standards that comprise the Internet protocol suite. It has no formal membership roster or membership requirements.

#### (RFC) Request for Comments
* Request for Comments, in information and communications technology, is a type of text document from the technology community. An RFC document may come from many bodies including from the Internet Engineering Task Force, the Internet Research Task Force, the Internet Architecture Board, or from independent authors.

#### Ephemeral Ports
* Port used by client in in client server architecture. These are the port on which client listen back from server.
* These port are being choose randomly from from a predefined range depending upon the OS.
* https://www.whizlabs.com/blog/ephemeral-ports/
* https://www.ncftp.com/ncftpd/doc/misc/ephemeral_ports.html 

#### Socket
* A socket is one endpoint of a two-way communication link between two programs running on the network. A socket is bound to a port number so that the TCP layer can identify the application that data is destined to be sent to.
* An endpoint is a combination of an IP address and a port number.
* Every TCP connection can be uniquely identified by its two endpoints.
* https://docs.oracle.com/javase/tutorial/networking/sockets/definition.html#:~:text=Definition%3A,address%20and%20a%20port%20number.  