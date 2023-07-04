![My Remote Image](https://i.imgur.com/mKK4bf8.jpg)


Explanation of the infrastructure:

1.  **Server 1, Server 2, Server 3**: Three servers are added to provide redundancy and improve fault tolerance. They host the various components of the web infrastructure.
    
2.  **Firewalls**: Three firewalls are added to enhance security. Firewalls act as barriers between the servers and the external network, controlling and monitoring incoming and outgoing traffic. They help protect the servers from unauthorized access, intrusion attempts, and other network threats.
    
3.  **SSL Certificate**: An SSL certificate is installed on the servers to serve the website [www.foobar.com](http://www.foobar.com) over HTTPS. HTTPS encrypts the traffic between the users' browsers and the web servers, ensuring secure communication and protecting sensitive data from being intercepted or tampered with.
    
4.  **Monitoring Clients**: Three monitoring clients, such as data collectors for Sumo Logic or other monitoring services, are added to monitor the infrastructure. These monitoring clients collect data on server performance, resource utilization, availability, and other metrics. They provide insights into the health and performance of the infrastructure, allowing proactive troubleshooting and optimization.
    

Specifics about the infrastructure:

-   **Firewalls**: Firewalls are added to safeguard the infrastructure by enforcing security policies, controlling access to the servers, and preventing unauthorized network traffic.
    
-   **HTTPS**: Traffic is served over HTTPS to ensure secure communication between the users' browsers and the web servers. HTTPS encrypts the data transmission, protecting it from eavesdropping, tampering, and man-in-the-middle attacks.
    
-   **Monitoring**: Monitoring is used to track the performance, availability, and health of the servers and applications. It helps detect issues, identify bottlenecks, and ensure optimal performance. The monitoring tool collects data by periodically querying the servers, analyzing server logs, and capturing relevant metrics.
    
-   **Monitoring Web Server QPS**: To monitor the web server's queries per second (QPS), you can use the monitoring tool to capture and analyze relevant metrics such as the number of requests received per second or the server's response time. This data helps assess the web server's performance and identify any potential performance bottlenecks.
    

Issues with the infrastructure:

-   **Terminating SSL at the load balancer level**: Terminating SSL at the load balancer level means that the load balancer decrypts the HTTPS traffic and forwards it to the backend servers as unencrypted HTTP traffic. This can pose a security risk, as the traffic between the load balancer and backend servers is not encrypted. It's recommended to enable end-to-end encryption by terminating SSL at the backend servers themselves.
    
-   **Single MySQL server capable of accepting writes**: Having only one MySQL server capable of accepting write operations creates a single point of failure and can limit scalability. If the MySQL server fails, the website/application may become unavailable, and write operations cannot be performed. To address this, a database replication setup with a primary-replica (master-slave) cluster is recommended to provide redundancy, fault tolerance, and load distribution.
    
-   **Servers with the same components**: Having servers with the same components (database, web server, and application server) can lead to a lack of flexibility and scalability. It may limit the ability to independently scale different components based on their specific requirements. Introducing a more modular and scalable architecture, such as microservices or containerization, can help overcome this problem.
    

Remember, this design is a high-level overview, and there can be variations based on specific requirements and considerations.