<h5>Directory</h5> 

<b>[Tech Portfolio Home](https://github.com/Jays1115/Jalen-Smith.git)</b>
<b>[AWS Projects](https://github.com/Jays1115/AWS-Projects.git)</b>

# Auto Scaling

<h2>Description</h2>
Scenario: A gaming company is hosting gaming parties and allows users to host their own servers in their cafe, using Amazon EC2 instances. They face issues with automatic server replacement when a crash occurs, enforcing user limits on server provisioning, and need a system to automatically start and shut down servers at specified times for events.
<br><br>
Solution: Set up an Auto Scaling group with defined resource limits. Configure the group to react to scheduled time-based events.

<h2>Program walk-through:</h2>

<p align="center">
Navigated to the EC2 instance page to view the game server: <br/>
<img src="images/Screenshot 2024-09-23 at 1.39.48 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.40.19 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Copied the public IPv4 address and pasted it into a new browser tab to access the server's homepage: <br/>
<img src="images/Screenshot 2024-09-23 at 1.42.19 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.43.15 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Created an Amazon Machine Image (AMI) of the game server, which allows for easy duplication of the server's configuration. This AMI can be used to quickly launch new instances with identical settings and software, ensuring consistent performance and reliability across deployments: <br/>
<img src="images/Screenshot 2024-09-23 at 1.45.51 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.47.04 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.47.11 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.51.12 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Navigated to "Launch Templates" via the left side bar: <br/>
<img src="images/Screenshot 2024-09-23 at 1.52.00 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
I created a launch template using the newly created AMI of the game server, selecting the t2.nano instance type for its cost-efficiency and sufficient resource provision for basic tasks. A new key pair was generated for secure access, and the template was added to the existing webserver security group to ensure it adheres to our predefined security protocols. This setup streamlines the deployment process and enhances security management across our server environment in preparation for configuring auto scaling: <br/>
<img src="images/Screenshot 2024-09-23 at 1.54.13 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.55.15 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.55.59 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.56.34 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.57.23 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.58.09 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 1.58.30 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Navigated to the "Auto Scaling Groups" page via the left side bar: <br/>
<img src="images/Screenshot 2024-09-23 at 2.06.14 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
I created an Auto Scaling group using the launch template we recently developed. I selected the appropriate Virtual Private Cloud (VPC) and its corresponding subnets to ensure the group operates within our secure network environment. Health checks were set to run every 240 seconds, allowing for timely detection and response to any operational issues. The group size was initially set to 2, with a minimum scale of 2 to ensure consistent availability and a maximum scale of 4 to effectively handle increased loads without overprovisioning resources. Additionally, I enabled a target tracking scaling policy to automatically adjust the capacity to maintain stable, predictable performance and cost efficiency. This policy helps maintain the balance between sufficient capacity to handle workload demands and efficient use of resources: <br/>
<img src="images/Screenshot 2024-09-23 at 2.09.00 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.09.09 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.10.06 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.10.26 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.10.47 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.12.12 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.13.14 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.14.40 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
I accessed the Auto Scaling group and navigated to the activity tab to review the historical activity of the group: <br/>
<img src="images/Screenshot 2024-09-23 at 2.17.37 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.17.56 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
Moved to the automatic scaling tab and scrolled down to create a scheduled action: <br/>
<img src="images/Screenshot 2024-09-23 at 2.20.25 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.20.36 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
I implemented an auto-scaling policy to dynamically increase resources to between 3 and 4 instances every Thursday at 8 PM. This ensures that the gaming company has sufficient capacity to handle anticipated increases in demand or workload during peak times, optimizing both performance and resource utilization: <br/>
<img src="images/Screenshot 2024-09-23 at 2.27.29 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.27.40 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<p align="center">
I established an auto-scaling policy to scale down to zero resources every day at 1 AM. This strategy is designed to minimize costs by reducing resource usage during off-peak hours when demand is typically low, ensuring efficient management of our cloud infrastructure: <br/>
<img src="images/Screenshot 2024-09-23 at 2.31.37 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="images/Screenshot 2024-09-23 at 2.33.22 PM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

