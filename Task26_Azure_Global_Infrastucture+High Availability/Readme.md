# Advanced Task 2: Azure Global Infrastructure + High Availability

## Objective
To deploy a highly available Virtual Machine infrastructure using Availability Sets, Availability Zones, Load Balancers, and Azure Monitor.

## Steps Taken
1. **Resource Group:** Created `HA-Task2-RG` in the East US region to contain all resources.
2. **Network Setup:** Deployed a Virtual Network (`HA-VNet`) with a default subnet to host the infrastructure.
3. **Availability Set:** Launched 2 Virtual Machines (`VM-Set-1`, `VM-Set-2`) in an Availability Set to protect against hardware failures within a single data center.
4. **Availability Zones:** Launched 2 additional Virtual Machines (`VM-Zone-1`, `VM-Zone-2`) in separate Availability Zones (Zone 1 & Zone 2) to protect against entire data center failures.
5. **Load Balancing:**
   - Deployed a **Standard Public Load Balancer** (`My-LB`).
   - Configured a **Zone-Redundant Frontend IP**.
   - Added all 4 VMs to the **Backend Pool**.
   - Configured a **Health Probe** (TCP:80) and **Load Balancing Rule** to distribute traffic.
6. **Monitoring:**
   - Configured **Boot Diagnostics** on the VMs using a custom Storage Account (`Lukmanstorage2026`).
   - Set up an **Azure Monitor Alert** (`High-CPU-Alert`) to trigger an email notification if CPU usage exceeds the threshold.

## Resources Configured
* **Compute:** 4 Ubuntu Virtual Machines (2 in Availability Set, 2 in Availability Zones).
* **Networking:** Standard Load Balancer, Virtual Network, Public IP.
* **Storage:** Locally-redundant storage (LRS) account for diagnostics.
* **Monitoring:** Action Group (Email) and Alert Rules.

## Proofs
* **VMs.png**: Screenshot of the 4 Virtual Machines running in the Resource Group.
* **My-LB.png**: Screenshot of the Load Balancer Overview showing the Frontend IP.
* **BackendPool.png**: Screenshot showing the 4 VMs successfully added to the Load Balancer.
* **Email-alert.png**: Screenshot showing the Azure Monitor Alert rule configuration.
* **StorageAccount.png**: Screenshot of the Storage account used for diagnostic logs.
* **Test_Public_IP.png**: Screenshot proving the Public IP address configuration and reachability test.
