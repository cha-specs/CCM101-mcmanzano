# Mission 8: Cloud Security Engineer – Reflection

Completing Mission 8 helped me understand how important security is when managing cloud servers. Before doing this activity, I knew that servers needed protection, but I did not fully understand how easily an exposed service could become an entry point for attackers. Through this mission, I learned how to deploy an Nginx web application, test it using curl, and configure UFW to control incoming network traffic.

A host-based firewall protects a server by filtering network connections directly on the machine. Even if the physical network perimeter is breached, the firewall can still block unauthorized incoming connections based on its rules. This provides another layer of defense and helps protect services that should not be accessible to everyone.

Managing open network ports is also important because every exposed service can increase the server's attack surface. For example, allowing only SSH for administration and port 8080 for the web application reduces unnecessary exposure. Applying the default deny policy makes the server more secure because incoming traffic is blocked unless it is specifically permitted.

In a real enterprise environment, leaving MySQL port 3306 open to the public internet is dangerous. Attackers could attempt brute-force logins, exploit software vulnerabilities, or access sensitive database information if other security measures fail. Database access should normally be restricted to trusted application servers or private networks, with strong authentication and additional security controls.

This mission changed my perspective because I realized that even a newly deployed server can be vulnerable if its security settings are ignored. Configuring a firewall is not just about running commands; it also requires checking rules, testing access, and understanding their effects. I also learned that Docker-published ports may need additional firewall controls, so a successful local test does not always prove that external access is properly restricted.

Having eight missions in my GitHub portfolio makes me feel that I am gradually building practical cloud computing skills. My repository also serves as evidence of my learning and progress. Overall, this activity taught me to prioritize security, document my work, and apply safer configurations whenever I deploy applications in the cloud.
