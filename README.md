# Cloud-Based-Load-Balancer-Implementation-using-Microsoft-Azure-and-Docker
This project focuses on implementing a **software-defined networking (SDN)-based HTTP request load balancer** using **Microsoft Azure Virtual Machines (VMs) and Docker containers**. The objective is to efficiently manage and distribute incoming HTTP traffic across multiple web servers while demonstrating the advantages of containerization in network management. 

**Project Overview**
The setup consists of three **Ubuntu-based virtual machines (VMs) on Microsoft Azure**:
- **Two VMs (VM52 and VM53) function as web servers**, hosting containerized Nginx instances.
- **One VM (VM54) acts as the load balancer**, distributing HTTP requests among the web servers.

The project explores different **load balancing techniques**, ensuring fair and efficient request allocation based on predefined strategies.

**Implementation Steps**
1. **Setting Up the Environment:**
   - Docker was installed on all three VMs to enable containerized deployment.
   - Custom Docker images were created for web servers based on Nginx, ensuring standardized configurations.
   - Each web server was configured with a Python-based backend to process requests and return unique responses.

2. **Web Server Deployment:**
   - A **custom Docker image** was built using a `Dockerfile` that installed Nginx and defined the necessary configurations.
   - The image was deployed on **VM52 and VM53**, running containers that served HTTP responses.
   - The servers were tested by accessing them through their IP addresses, ensuring they responded correctly.

3. **Load Balancer Deployment:**
   - A separate **Docker container was set up on VM54** to function as a load balancer.
   - Multiple load balancing algorithms were implemented using Python, each handling incoming requests differently.
   - The load balancer forwarded requests to **VM52 and VM53**, ensuring optimized traffic distribution.

4. **Load Balancing Strategies Implemented:**
   - **Round Robin:** Requests were distributed sequentially among the available servers, ensuring equal load distribution.
   - **Weighted Round Robin:** Requests were assigned based on pre-defined server weights, allowing high-capacity servers to handle more traffic.
   - **Workload-Sensitive Load Balancing:** The system monitored real-time server load and directed requests to the least busy server, optimizing performance.
   - **Random Selection Load Balancing:** Requests were forwarded to servers at random, ensuring a non-deterministic distribution pattern.

5. **Testing and Validation:**
   - The load balancer was tested by sending HTTP requests and analyzing request distribution.
   - The performance of each algorithm was observed using server logs, ensuring expected behavior.
   - Requests were accessed via a web browser using the load balancer’s IP address and port to verify successful load balancing.

 **Results and Findings**
The project successfully implemented all four **load balancing techniques**, demonstrating their functionality in a cloud-based environment. The **Round Robin algorithm** evenly distributed requests across servers, ensuring fairness. The **Weighted Round Robin approach** provided controlled distribution based on server capacity. The **Workload-Sensitive method** dynamically adjusted request allocation to optimize resource usage, while the **Random Selection method** demonstrated unpredictability in request handling. The implementation highlighted the efficiency of **containerized load balancing solutions** in cloud computing environments, showcasing **the benefits of virtualization, scalability, and dynamic traffic management**.

This project serves as a practical exploration of **SDN concepts, containerized deployments, and real-world load balancing mechanisms**, emphasizing their importance in modern cloud infrastructure.
