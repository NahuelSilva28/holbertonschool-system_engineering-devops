<https://imgur.com/bVzXdVu>

Description:
This web infrastructure is an upgraded version of the previous infrastructure. It eliminates all single points of failure by separating the major components (web server, application server, and database servers) onto individual GNU/Linux servers. Each server is protected by a firewall, ensuring network security. SSL protection is not terminated at the load balancer, providing end-to-end encryption. Additionally, the servers are monitored to track their status and performance.

Specifics About This Infrastructure:

Firewall Implementation: A firewall is placed between each server, providing protection against unwanted and unauthorized access attempts. This enhances the overall security of the infrastructure.

Issues With This Infrastructure:

High Maintenance Costs: The upgraded infrastructure incurs higher maintenance costs. The separation of components onto individual servers requires the procurement of additional hardware and increases the electricity consumption, leading to increased expenses for server purchase and electricity bills.

To address the high maintenance costs, it is recommended to evaluate the cost-benefit ratio and assess the scalability requirements of the web infrastructure. Alternative solutions, such as cloud-based infrastructure or resource optimization strategies, could be explored to optimize costs while maintaining the desired level of performance and security.
