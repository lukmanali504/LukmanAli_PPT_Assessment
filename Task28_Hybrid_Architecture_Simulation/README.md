# Advandced Task 4: Hybrid Architecture Simulation (Bastion Host)

## Objective
To simulate a secure on-premise to cloud network architecture using a Bastion Host (Jump Server) to access isolated private resources.

## Architecture Overview
* **VPC**: Custom `Task4-VPC` (10.0.0.0/16)
* **Public Subnet**: Hosts the Bastion Server (Accessible via Internet).
* **Private Subnet**: Hosts the Internal VM (No Internet Access, secure).
* **Security**: The Internal VM only accepts SSH connections from the Bastion Host's security group.

## Implementation Steps
1.  **Network Design**: Created a VPC with distinct Public and Private subnets.
2.  **Bastion Deployment**: Launched an EC2 instance (`Bastion-Host`) in the Public Subnet with a Public IP.
3.  **Private Server Deployment**: Launched an EC2 instance (`Private-VM`) in the Private Subnet with **no** Public IP.
4.  **Access Control**: Configured Security Groups to allow SSH traffic strictly from the Bastion to the Private VM.
5.  **Secure Access**: 
    - Logged into the Bastion Host using the private key.
    - "Jumped" to the Private VM using the local network IP.
6.  **Verification**: Confirmed successful login to the private IP address (10.0.x.x) from the Bastion terminal.

## Proof of Completion
* **Bastion_Jump_Success.png**: Terminal screenshot showing the SSH jump from Public to Private IP.
* **VPC_Architecture.png**: AWS Resource Map showing the network topology.
