
To deploy a fault-tolerant web application across multiple Availability Zones using VPC, ALB, Auto Scaling, EC2, S3, and CloudWatch.

Implementation Steps
1. Networking Foundation (VPC)
Created a custom VPC with a CIDR block of 10.0.0.0/16.
Provisioned Public and Private subnets across two Availability Zones (AZs) for high availability.
Configured an Internet Gateway (IGW) for public access and a NAT Gateway to allow private instances to access the internet securely.
2. Compute and Automation (EC2 & ASG)
Launched two Ubuntu EC2 instances within the private subnets.
Utilized a User Data script to automate the installation and configuration of the Apache web server upon launch.
Configured an Auto Scaling Group (ASG) to maintain instance counts and ensure system resilience.
3. Traffic Management (ALB)
Deployed an Application Load Balancer (ALB) in the public subnets to distribute incoming traffic.
Configured Security Groups using the principle of least privilege, ensuring EC2 instances only accept traffic originating from the ALB.
4. Storage and Monitoring
Created an Amazon S3 bucket for centralized asset storage.
Configured a CloudWatch Alarm to monitor CPU Utilization, set to trigger an alert if usage exceeds a 70% threshold.
Resources Configured
VPC: 10.0.0.0/16
Instances: WebServer-1, WebServer-2
Load Balancer: My-Public-ALB (Application Tier)
Monitoring: CPU Utilization Threshold > 70%
Tools: VPC, EC2, ALB, Auto Scaling, S3, CloudWatch
Proofs of Completion
Architecture_Proof.png: Screenshot showing the live web application loaded via the Load Balancer DNS URL.
Resources.png: Screenshot showing the EC2 instances running in different Availability Zones.
