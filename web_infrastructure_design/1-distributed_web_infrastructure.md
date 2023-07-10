<https://imgur.com/B9vUdY4>


Description:
This is a distributed web infrastructure aimed at reducing traffic to the primary server by distributing some of the load to a replica server, with the assistance of a load balancer responsible for balancing the workload between the two servers (primary and replica).

Specifics About This Infrastructure:

Load Balancer Distribution Algorithm: The load balancer implemented in this infrastructure utilizes the Round Robin distribution algorithm. This algorithm operates by evenly distributing incoming requests across the available servers, based on their weights. It ensures that each server receives an equal share of the workload, promoting fairness and balancing the processing time.

Load Balancer Setup: The load balancer, implemented using HAProxy, enables an Active-Passive setup rather than an Active-Active setup. In an Active-Active setup, the load balancer distributes workloads across all nodes to prevent any single node from becoming overloaded. This setup improves throughput and response times. In contrast, an Active-Passive setup designates certain nodes as active, capable of receiving workloads, while others remain passive or on standby. The passive nodes can become active only if the preceding active node becomes inactive.

Primary-Replica (Master-Slave) Database Cluster: The infrastructure utilizes a Primary-Replica database setup. In this configuration, one server functions as the Primary server, while the other server acts as a Replica of the Primary server. The Primary server handles both read and write operations, while the Replica server is limited to read operations only. Synchronization of data occurs whenever the Primary server executes a write operation, ensuring consistency between the two servers.

Role Difference Between Primary and Replica Nodes: The Primary node is responsible for handling write operations for the application, such as adding or modifying data. On the other hand, the Replica node is primarily focused on processing read operations. By offloading read traffic to the Replica node, the Primary node's workload is reduced, optimizing its performance and ensuring efficient resource utilization.

Issues With This Infrastructure:

Single Points of Failure (SPOF): The infrastructure suffers from multiple SPOFs. For example, if the Primary MySQL database server goes down, the entire site will be unable to make changes, including adding or removing users. Additionally, the server hosting the load balancer and the application server connected to the primary database server also pose as potential SPOFs.

Security Concerns: The infrastructure lacks necessary security measures. Data transmitted over the network is not encrypted using an SSL certificate, leaving it vulnerable to interception by hackers. Moreover, the absence of a firewall on any of the servers restricts the ability to block unauthorized IP addresses, potentially compromising the network's security.

Lack of Monitoring: The infrastructure lacks a monitoring system to keep track of the status and performance of each server. Without monitoring, it becomes difficult to identify issues, troubleshoot problems, and ensure optimal system operation.

To address these issues, it is recommended to introduce redundancy measures to eliminate single points of failure. Implementing SSL certificates and firewalls will enhance network security, and deploying a robust monitoring system will allow proactive monitoring and management of the infrastructure.