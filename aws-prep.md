### AWS global infrastructure
* AWS Region
  * Different geo-political and governance rule
* Availability Zone:
  * Different Data center which are far enough to avoid any disaster but close enough to give high networking performance.
* Edge location:
  * These are CDN network for static content and storage for low latency. They are not compute services. E.g cloudfront
  * These are being deployed in most of the major cities of the world for low latency.

#### HA
* Recover from fail
* E.g auto-scaling group

#### FT
* System has multiple redundancies
* You store session outside of web server so that if any server fail the system continue to operate without any interruption
* Eg having a loadbalancer so that if any server fail the system continue to operate without any interruption
* You need to have system in active mode.

#### DR
* Protecting system critical data so that you can use that to recreate a new working system in the event of disaster

#### RPO(Recovery point objective): 
* Time between last recoverable copy of data and disaster occurred. It simply how much data lost you can bear with in case of disaster.


#### RTO(Recovery time objective):
* Time between disaster occurred and the system restored back. 
* You can use a HOT ec2 instance or read replica for lowering RTO.


#### Data persistence
* Ephemeral storage
  * Also known instance store volume.
  * Data that is local generally local to resource and is lost when the resource is powered down
  * They are fastest type of storage as the volume is directly attached to the host. 
  * If you restart and ec2 instance with instance store volume then that ec2 instance may start on another host. So previously attached volume is lost completely.
  
* Transient
  * e.g SQS
  
* Persistent
  * e.g EBS, EFS
  
#### OSI(Open System interconnect)
* APSTNDP




#### Cloud formation
* Cloud formation template component:
  * Parameter
  * Mapping
  * Resources

#### AWS Support Tiers
* Basic
* Developer
  * If you are experimenting or testing aws
* Business
  * If you have a production workload
* Enterprise
  * If you have mission critical workload
  
#### Permission policy vs Permission boundary
* Permission boundary limit access where as Permission policy can limit access or grant access?
* The final result is combination of both.

#### VPC
* Default resources created upon creation of VPC
  * Route table
  * NACL
  * Security Group
* Security group do not span VPC
* We need to have at least two subnet for ELB provisioning.


#### Ec2 Price model
* On demand Instances
* Reserved Instances
  * Standard Reserved Instance(Offer upto 75% off on demand when paying all upfront)
  * Convertible Reserved Instance(Offer upto 54% off on demand when paying all upfront)
  * Schedule Reserved Instance
* Spot Instances
  * Offer very good saving. But as soon as the price goes above bid price the instance get terminated. 
* Dedicated host
  * Licencing, Regulatory requirement, Single tenancy

#### STS
* Give user temporary access to aws resources.
#### Hypervisor
* Other Hypervisor not used in AWS are microsoft Hyper-V and VMware V-Sphere
* A Hypervisor or VMM(virtual machine monitor) is a computer software, firmware or hardware that create and run virtual machine. The computer on which a hypervisor run one or more virtual machine is called host and each virtual machine are called guest machine.
* EC2 currently run on XEN hypervisor
* XEN hypervisor can have guest OS running ad PV(Paravirtualization) or HVM(Hardware virtual machine)
  *  HVM are fully virtualized guest. The VMs on top of Hypervisors are not aware that they are sharing procession time with other VMs.
  * PV is lighter form of virtualization and it used to be quicker. PV is isolated by layer.
  * Amazon recommend to use HVM over PV. Window instance can only be HVM where as Linux can be both HVM and PV. 
  
#### Flow Logs
* Provide visibility about network traffic into a system.
* It does not provide the actual traffic i.e request. It provide metadata of traffic.
* Things which are not logged as a part of flow logs are:
  * DHCP traffic
  * AWS DNS
  * Meta data
  * Licence activation request 

#### Miscellaneous  
* Dedicated Host vs Dedicated instance vs shared host.
* 5000 User per account.
* SCP do not impact in master account in anyway.
* Geolocation routing policy is used when you want to route traffic based on the location of your users.
* Geo proximity routing policy is for scenarios where you want to route traffic based on the location of your resources and, optionally, shift traffic from resources on one location to resources in another.
* you can only use the same SSL certificate from ACM in more than one AWS Region if you are attaching it to your CloudFront distribution only, and not to your Application Load Balancer
* An IAM policy can be applied only to IAM users, groups, or roles, and `it can never restrict the root identity of the AWS account`.
* AWS Organizations lets you use service control policies (SCPs) to allow or deny access to particular AWS services for individual AWS accounts, or for groups of accounts within an organizational unit (OU). The specified actions from an attached SCP affect all IAM users, groups, and roles for an account, `including the root account identity`.
* AWS Schema Conversion Tool to convert the source schema and code to match that of the target database.
* AWS Database Migration Service to migrate data from the source database to the target database
* For EC2 instances, always use a Type A Record without an Alias. For ELB, Cloudfront and S3, always use a Type A Record with an Alias and finally, for RDS, always use the CNAME Record with no Alias.
* ELB will improve the availability
* IDS is mostly concerned about detection of unauthorized access and IPS is basically similar to IDS, but provides a prevention mechanism for your network.
* Egress-only Internet gateway is primarily used to handle IPv6 traffic.
#### VPN Connection
* Component
  * Customer gateway
  * Tunnel endpoint
  * Virtual private gateway(VPC router is aware of this. VPC router using route table direct traffic to VPGW)
    * VPGW can be attach to a single VPC but can be termination point for may VPN connection 
* VPN connection occur between Customer gateway and VPGW

#### Direct connect
* Component
  * Private VIF(Virtual private interface) or Public VIF
  * Port
  * Public VIF is for public zone services
  * Direct connect gateway
  * Virtual private gateway
  * With the Direct connect gateway now you can connect in multiple regions. Earlier it was not possible. 
  * Data is not encrypted over Direct connect 
  
#### Transit gateway
* Allow you to connect in hub and spock form for multiple VPC and VPN connection from on premise data center
* VPC Attachments  

#### Cloud Front
* Origin, Viewer
* Regional Cache
* Origin Access Identity

#### Storage Gateway
* Type
  * File Gateway
  * Volume Gateway
    * cached volumes
    * stored volumes 
  * Tape Gateway
#### Roue 53
* When you register a domain name then records are placed into global DNS system.
  * Store name server information
  * Registrant contact, administrative contact and technical contact
* Hosted zone link name server and domain name.
* You have option of private and public hosted zone.
* Record set are value that DNS uses to operate.
* Record set contains record type, routing policy, standard or alis, target health. TTL
##### Routing policy
* Simple
* Failover
* Geo Location
* Latency
* Weighted
* Multi value

#### Hosted Zone
* Public hosted zone
  * Public hosted zone contain records that specify how you want to route traffic on the internet.
  
* Private hosted zone
  * Private hosted zones contain records that specify how you want to route traffic in an Amazon VPC.

`enableDnsHostnames` - Indicates whether the instances launched in the VPC get public DNS hostnames. If this attribute is true, instances in the VPC get public DNS hostnames, but only if the enableDnsSupport attribute is also set to true.

`enableDnsSupport` - Indicates whether the DNS resolution is supported for the VPC. If this attribute is false, the Amazon-provided DNS server in the VPC that resolves public DNS hostnames to IP addresses is not enabled. If this attribute is true, queries to the Amazon provided DNS server at the 169.254.169.253 IP address, or the reserved IP address at the base of the VPC IPv4 network range plus two ( *.*.*.2 ) will succeed.

#### AWS System manager
* AWS Systems Manager Run Command is primarily used to remotely manage the configuration of your managed instances.
* AWS Systems Manager State Manager is just a configuration management service that automates the process of keeping your Amazon EC2 and hybrid infrastructure in a state that you define.
   

#### AWS Secrets Manager secrets 
* helps you protect access to your applications, services, and IT resources
* enables you to easily rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle
* dedicated secrets store with lifecycle management
#### AWS Systems Manager Parameter Store parameters
* Single store for configuration and secrets
* Does not have life cycle and rotation feature

#### Systems Manager Session Manager
*  Used to simplify the process of complying with corporate policies that require controlled access to instances, strict security practices, and fully auditable logs with instance access details.

#### AWS Systems Manager State Manager
* Secure and scalable configuration management service that automates the process of keeping your Amazon EC2 and hybrid infrastructure in a state that you define.
* Bootstrap instances with specific software at start-up
* Download and update agents on a defined schedule, including SSM Agent
* Configure network settings
* Join instances to a Windows domain (Windows instances only)
* Patch instances with software updates throughout their lifecycle
* Run scripts on Linux and Windows managed instances throughout their lifecycle


#### AWS Systems Manager Patch Manager
* Used to automate the process of patching managed instances with security-related updates
* 

#### AWS Server migration service
* AWS Server Migration Service automates the migration of your on-premises VMware vSphere, Microsoft Hyper-V/SCVMM, and Azure virtual machines to the AWS Cloud. 
* AWS SMS incrementally replicates your server VMs as cloud-hosted Amazon Machine Images (AMIs) ready for deployment on Amazon EC2.


#### Six approaches detailed below are common migration strategies employed
* Re-host
* Re-platform
* Repurchase
* Re-architect/Refactor
* Retire
* Retain

#### Amazon Cognito
* Amazon Cognito scales to millions of users and supports sign-in with social identity providers, such as Facebook, Google, and Amazon, and enterprise identity providers via SAML 2.0.

#### EMR cluster
* In multi node cluster there are three type of node master node, the core node, and task nodes
* In single-node cluster, all components run on the master node

#### 5 pillars Well-Architected Framework
* Operational Excellence
* Security
* Reliability : ability of a system to recover from infrastructure or service disruptions, dynamically acquire computing resources to meet demand, and mitigate disruptions such as misconfiguration or transient network issues.
* Performance Efficiency
* Cost Optimization

#### RTMP distribution
* Used for real-time streaming


#### AWS Inspector
* A security assessments service which only helps you in checking for unintended network accessibility of your EC2 instances and for vulnerabilities on those EC2 instances.

#### Route Origin Authorization (ROA)
* It contains the address range, the ASNs that are allowed to advertise the address range, and an expiration date.
* It is created via Regional Internet Registry (RIR) such as the American Registry for Internet Numbers (ARIN) or Réseaux IP Européens Network Coordination Centre (RIPE)

#### AWS WAF
* Web application firewall that helps protect your web applications or APIs against common web exploits that may affect availability, compromise security, or consume excessive resources.
* AWS WAF gives you control over how traffic reaches your applications by enabling you to create security rules that block common attack patterns, such as SQL injection or cross-site scripting, and rules that filter out specific traffic patterns you define.
* You can get started quickly using Managed Rules for AWS WAF, a pre-configured set of rules managed by AWS or AWS Marketplace Seller.
* The Managed Rules for WAF address issues like the OWASP Top 10 security risks.
* WS WAF includes a full-featured API that you can use to automate the creation, deployment, and maintenance of security rules.
* It can help you block common attack patterns to your VPC such as SQL injection or cross-site scripting.
* AWS WAF gives you control over which traffic to allow or block to your web applications by defining customizable web security rules. 
* You can use AWS WAF to create custom rules that block common attack patterns, such as SQL injection or cross-site scripting, and rules that are designed for your specific application. 
* New rules can be deployed within minutes, letting you respond quickly to changing traffic patterns.
#### AWS Firewall Manager
* Manage multiple AWS WAF Deployment.
* simplify your AWS WAF administration and maintenance tasks across multiple accounts and resources.
* used to manage your Firewall across multiple AWS accounts under your AWS Organizations.


#### Amazon GuardDuty
*  Amazon GuardDuty is primarily used as a threat detection service that continuously monitors for malicious or unauthorized behavior to help you protect your AWS accounts and workloads.
* It monitors for activity such as unusual API calls or potentially unauthorized deployments that indicate a possible account compromise.


#### Amazon Macie
* Amazon Macie is a security service that uses machine learning to automatically discover, classify, and protect sensitive data in AWS.
* Amazon Macie recognizes sensitive data such as personally identifiable information (PII) or intellectual property, and provides you with dashboards and alerts that give visibility into how this data is being accessed or moved.
* The fully managed service continuously monitors data access activity for anomalies, and generates detailed alerts when it detects risk of unauthorized access or inadvertent data leaks.


#### Intrusion Detection Systems (IDS)
* Intrusion Detection Systems (IDS) monitor networks and/or systems for malicious activity or policy violation, and report them to systems administrators or to a security information and event management (SIEM) system.
* Intrusion Prevention Systems (IPS) are positioned behind firewalls and provide an additional layer of security by scanning and analyzing suspicious content for potential threats. Placed in the direct communication path, an IPS will take automatic action on suspicious traffic within the network.









