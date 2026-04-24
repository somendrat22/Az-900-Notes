# Azure Virtual Machines - Answer Sheet for AZ-900

## Section 1: Basic Concepts - Answers

**A1.** A Virtual Machine (VM) is a computer inside a computer - a virtualized computing environment that runs on physical hardware in Azure's data centers. It provides CPU, memory, storage, and networking just like a physical computer.

**A2.** Three main benefits:
1. No physical hardware needed - rent instead of buy
2. Quick setup - get a computer running in minutes
3. Pay only for what you use - like paying electricity bills

**A3.** A Subscription - this is your billing account with Azure that will be charged for all resources you create.

**A4.** A Resource Group is a container/folder that holds related Azure resources together. It's important because:
- Easy to manage resources together
- Easy to delete all resources at once
- Easy to see costs per project
- Easy to apply permissions to a group of resources

**A5.** No, a VM can only belong to ONE Resource Group at a time. Each resource must be in exactly one Resource Group.

**A6.** Region is the physical location (data center) where your VM will run. Examples: East US (Virginia), Central India (Pune), West Europe (Netherlands).

**A7.** Deploy VMs in multiple regions:
- Central India region for Indian customers
- East US region for American customers  
- West Europe region for German customers
This gives the best performance by reducing latency.

**A8.** 
- **Stopping (deallocated)**: You don't pay for compute (CPU/RAM) but still pay for disk storage
- **Deleting**: You stop paying for everything (compute + storage), but the VM is gone forever

**A9.** An Image is the operating system and pre-installed software template used to create a VM. Like choosing a furnished vs unfurnished apartment. Examples: Windows Server 2022, Ubuntu 20.04, Red Hat Linux.

**A10.** Windows Server 2022 - because Ubuntu is a Linux operating system and won't run Windows applications.

**A11.** The VM Size determines computing power. The size specifies how many CPUs, how much RAM, and storage the VM will have. Examples: B1s (1 CPU, 1 GB RAM), D2s_v3 (2 CPUs, 8 GB RAM).

**A12.** 
- **OS Disk**: The main hard drive where the operating system is installed (required)
- **Data Disk**: Additional storage you can attach for storing files, databases, etc. (optional)

**A13.** A Public IP is an address accessible from the internet. You need one when:
- You want to access the VM from home/internet
- You're hosting a website that users need to visit
- You need remote desktop/SSH access from outside Azure

**A14.** Auto-shutdown automatically turns off a VM at a scheduled time to save costs. Useful for dev/test VMs that don't need to run 24/7.

**A15.** Yes, you can resize a VM after creation (make it bigger or smaller) but the VM needs to be stopped first.

---

## Section 2: VM Sizes and Series - Answers

**A16.** B-series (Burstable) is best for:
- Low-traffic websites
- Development and testing
- Small applications
- Workloads that don't need consistent high CPU
- Budget-friendly scenarios

**A17.** F-series (Compute-optimized) - designed for CPU-intensive workloads requiring fast processors.

**A18.** E-series (Memory-optimized) - provides high memory-to-CPU ratio, perfect for databases that need lots of RAM.

**A19.** Breaking down "D2s_v3":
- **D** = D-series (general purpose)
- **2** = 2 vCPUs
- **s** = Supports Premium SSD storage
- **v3** = Version 3 (generation)

**A20.** B1s is more cost-effective. E16s_v3 has 16 CPUs and 128 GB RAM - massive overkill for a test website, and very expensive.

**A21.** Database workloads or memory-intensive applications (like SQL Server, SAP HANA, in-memory analytics).

**A22.** 
- **Standard HDD**: Slowest, cheapest (like a regular cupboard)
- **Standard SSD**: Faster, moderate cost (like an organized closet)
- **Premium SSD**: Fastest, most expensive (like a high-tech storage system)

**A23.** GPU VMs (like NC-series or NV-series) - they have Graphics Processing Units designed for AI/ML, deep learning, and data science workloads.

**A24.** Budget-friendly size (B-series) - no need to pay for high performance when testing.

**A25.** Yes, you can attach multiple data disks to a single VM (the number depends on the VM size).

---

## Section 3: Networking - Answers

**A26.** A Virtual Network (VNet) is a private network in Azure where your resources can communicate securely. Like a gated community for your VMs.

**A27.** 
- **VNet**: The entire private network (like the whole gated community)
- **Subnet**: A section within the VNet (like different blocks within the community - Block A for web servers, Block B for databases)

**A28.** Yes, VMs in the same VNet can communicate with each other privately using their private IP addresses.

**A29.** Network Security Group (NSG) is a firewall that controls inbound and outbound traffic to VMs. It contains security rules that allow or deny traffic based on source, destination, port, and protocol.

**A30.** Port 80 (HTTP) or 443 (HTTPS) for web traffic. Both are commonly used for websites.

**A31.** 
- **Port 80**: HTTP - unencrypted web traffic
- **Port 443**: HTTPS - encrypted/secure web traffic (recommended for production)

**A32.** Port 3389 (RDP - Remote Desktop Protocol) for Windows VMs.

**A33.** Port 22 (SSH - Secure Shell) for Linux VMs.

**A34.** No, it's a terrible security practice. Only open the ports you actually need. Opening all ports is like leaving all doors and windows of your house unlocked - inviting security breaches.

**A35.** A Load Balancer distributes incoming traffic across multiple VMs. Benefits:
- If one VM fails, traffic goes to healthy VMs
- Distributes load evenly
- Improves performance and availability

**A36.** No, the database VM should NOT have a Public IP. It should only be accessible via private network from your web VMs, not from the internet.

**A37.** Benefits of Load Balancer with multiple VMs:
- High availability - if one VM crashes, others handle traffic
- Better performance - traffic distributed across VMs
- Easy scaling - add more VMs when needed
- No single point of failure

---

## Section 4: Availability and Reliability - Answers

**A38.** An Availability Zone is a physically separate data center within an Azure region. Each zone has independent power, cooling, and networking. Like having backup apartments in different buildings in the same city.

**A39.** 
- **Availability Zone**: Separate physical data centers in the same region (different buildings in the same city)
- **Availability Set**: VMs distributed across different racks/servers in the same data center (different floors in the same building)
Availability Zones provide better protection.

**A40.** Multiple VMs across Availability Zones - this ensures if one zone fails, your application keeps running on VMs in other zones.

**A41.** Your VM goes down and your application stops working until Azure moves it to another server (which could take time).

**A42.** The VMs in Zone 2 and Zone 3 would automatically take over, and your application would continue running with minimal disruption.

**A43.** VM backups create copies of your VM at specific points in time. If something goes wrong (data corruption, accidental deletion, ransomware), you can restore to a previous working state.

**A44.** Daily backups for production database VMs - database data is critical and changes frequently, so daily backups are essential.

**A45.** 
- **Backup**: Complete copy of VM stored in Azure Backup vault, can be retained for months/years
- **Snapshot**: Point-in-time copy of a disk, typically used for short-term recovery
Backups are more comprehensive and better for long-term retention.

**A46.** Yes, you can restore a VM from any backup point you have available.

**A47.** Boot Diagnostics captures screenshots and logs when a VM starts. If a VM won't boot or has startup problems, you can see what went wrong (like a security camera recording).

---

## Section 5: Security - Answers

**A48.** Two main authentication methods:
1. Username and Password
2. SSH Key (for Linux) or Certificate-based authentication

**A49.** SSH Key is more secure than password because:
- Longer and more complex (harder to crack)
- Not vulnerable to brute-force attacks
- Can't be accidentally exposed as easily

**A50.** No, this is extremely insecure:
- "admin" is a common username (easy to guess)
- "12345" is a weak password (can be cracked in seconds)
- Should use strong password with uppercase, lowercase, numbers, special characters

**A51.** Encryption at rest means data stored on disks is encrypted. If someone physically steals the hard drive, they can't read the data without the encryption key.

**A52.** Encryption in transit means data is encrypted while moving over the network (like using HTTPS). Prevents eavesdropping on network traffic.

**A53.** No, production VMs should NOT be accessible from any IP. Use NSG rules to restrict access to:
- Specific office IP addresses
- VPN connections
- Bastion hosts
- Only necessary ports

**A54.** Least privilege means giving users/services only the minimum permissions they need to do their job. Don't give admin access to everyone - only to those who need it.

**A55.** Configure NSG to:
- Allow traffic only from your office's public IP address
- Deny all other IP addresses
- Only open necessary ports (like RDP 3389 or SSH 22)

**A56.** Multi-Factor Authentication (MFA) requires two or more verification methods:
- Something you know (password)
- Something you have (phone with code)
- Something you are (fingerprint)
Adds extra security layer.

**A57.** No, extremely dangerous! Passwords should:
- Be stored in Azure Key Vault
- Use environment variables
- Never be committed to source code
- Be encrypted

**A58.** Immediately:
1. Change the password
2. Rotate any API keys or secrets
3. Check audit logs for unauthorized access
4. Review NSG rules
5. Consider rebuilding the VM if compromised

**A59.** Regular updates and patches:
- Fix security vulnerabilities
- Prevent exploitation by hackers
- Improve stability and performance
- Ensure compliance with security standards

---

## Section 6: Cost Management - Answers

**A60.** Main cost factors:
1. **VM Size**: Bigger VM = higher cost
2. **Running time**: Only pay when running (per hour/minute)
3. **Disk storage**: Costs even when VM is stopped
4. **Data transfer**: Moving data in/out of Azure
5. **Region**: Different regions have different prices

**A61.** Use Auto-shutdown to automatically stop the VM at 6 PM and auto-start at 9 AM. This saves ~62% cost (9 hours vs 24 hours).

**A62.** A stopped (deallocated) VM:
- Does NOT charge for compute (CPU/RAM)
- DOES charge for disk storage
- DOES charge for reserved Public IP (if any)

**A63.** 
- **Stop**: VM is stopped but resources are still reserved (still paying)
- **Stop (deallocate)**: VM is stopped and resources are released (not paying for compute)
Always use "Stop (deallocate)" to save money.

**A64.** Reserved Instances are a commitment to use a VM for 1 or 3 years. You pay upfront or monthly and get 30-40% discount compared to pay-as-you-go pricing. Best for production VMs that run 24/7.

**A65.** You should downsize to a smaller VM (like A1 or even smaller B-series). You're paying for resources you're not using - this is over-provisioning.

**A66.** VM running 24/7 costs more. 
- 24/7 = 720 hours/month
- 8 hours/day = 240 hours/month
You save approximately 67% by running only 8 hours daily.

**A67.** Yes, disk storage costs continue even when VM is stopped. Only deleting the disk stops the storage charges.

**A68.** Auto-shutdown for test VMs:
- Prevents forgetting to stop VMs
- Saves 50-70% on costs
- Ensures VMs don't run overnight/weekends unnecessarily

**A69.** Generally the same cost for the same total resources, but multiple smaller VMs provide:
- Better availability (if one fails, others continue)
- Better load distribution
- More flexibility
However, one large VM is simpler to manage.

---

## Section 7: Real-World Scenarios - Answers

**A70.** Small company website configuration:
- **Size**: B2s or D2s_v3 (2 CPUs, 4-8 GB RAM)
- **Image**: Ubuntu 20.04 or Windows Server 2022
- **Region**: Closest to your customers
- **Disk**: Standard SSD (128 GB)
- **Public IP**: Yes
- **Ports**: 80 (HTTP), 443 (HTTPS), 22/3389 (management)
- **Auto-shutdown**: If not 24/7 business

**A71.** No, EU data protection regulations (GDPR) require EU customer data to be stored in EU regions. They must use regions like West Europe or North Europe.

**A72.** Auto-scaling (Virtual Machine Scale Sets) - automatically adds more VMs when traffic increases and removes them when traffic decreases.

**A73.** No, use auto-shutdown. Configure the VM to:
- Auto-start at the scheduled time (e.g., 10 PM)
- Run the batch job (2 hours)
- Auto-shutdown after completion (12 AM)
Saves ~90% cost compared to running 24/7.

**A74.** Check these metrics first:
- **CPU usage**: Is it at 100%?
- **Memory usage**: Is RAM full?
- **Disk IOPS**: Is disk being bottleneck?
- **Network**: Is bandwidth saturated?

**A75.** Configure:
- Long-term backup retention (7 years)
- Immutable storage (logs can't be modified)
- Separate storage account for archives
- Compliance policies on Resource Group

**A76.** Maybe - depends on timing:
- If recently deleted, might be in soft-delete (recoverable for 14 days)
- If you have backups, restore from backup
- If completely deleted with no backup, it's gone forever
This is why backups are critical!

**A77.** Boot Diagnostics - it shows:
- Screenshot of the VM screen
- Serial console logs
- Error messages during startup
Helps diagnose why VM won't boot.

**A78.** Create a separate VM in a Dev/Test Resource Group:
- Clone the production VM or create new one
- Test the new application version
- Keep it completely isolated from production network
- Only deploy to production after successful testing

**A79.** Premium SSD or Ultra Disk - trading applications need:
- Lowest latency (milliseconds matter)
- Highest IOPS (input/output operations per second)
- Consistent performance

**A80.** Organize using Resource Groups by:
- **Project**: "Project-A-RG", "Project-B-RG"
- **Environment**: "Production-RG", "Development-RG", "Testing-RG"
- **Department**: "Finance-RG", "HR-RG", "Sales-RG"
Makes management, billing, and access control easier.

**A81.** Configure NSG rules to:
- Deny traffic from attacking IP addresses
- Use Azure DDoS Protection
- Enable Azure Firewall
- Consider using Azure Security Center for threat detection

**A82.** Create a Virtual Network (VNet) and put all 10 VMs in it. They can then communicate using private IP addresses securely.

**A83.** Implement multi-region deployment:
- Deploy VMs in multiple regions (e.g., East US and West Europe)
- Use Azure Traffic Manager to route traffic
- Replicate data across regions
- Configure automatic failover

**A84.** Use Just-In-Time (JIT) access:
- Grant temporary access only when needed
- Access expires after set time (e.g., 3 hours)
- Requires approval
- All access is logged
Never give permanent production access for debugging.

---

## Section 8: Comparison Questions - Answers

**A85.** Differences:
- **VM**: Virtual, runs on shared hardware, can be created in minutes, pay-as-you-go, easy to scale
- **Physical**: Real hardware, takes days/weeks to procure, upfront cost, harder to scale, you own and maintain it

**A86.** 
- **B-series**: For workloads with low average CPU usage (dev/test, small websites, low-traffic apps) - budget-friendly
- **F-series**: For CPU-intensive workloads (gaming servers, batch processing, analytics) - high performance
Use B for cost savings, F for performance.

**A87.** 
- **Horizontal scaling**: Add more VMs (scale out) - better for availability, can handle more users
- **Vertical scaling**: Make VM bigger (scale up) - simpler but has limits, single point of failure
Horizontal is generally better for production.

**A88.** 
- **Public IP**: When VM needs to be accessed from internet (web servers, remote access, public APIs)
- **Private only**: When VM should only be accessed internally (databases, internal APIs, backend services)
Security best practice: minimize Public IPs.

**A89.** 
- **Subscription**: Billing account, top-level container, can have multiple Resource Groups
- **Resource Group**: Container for resources within a subscription, used for organizing related resources
Hierarchy: Subscription → Resource Groups → Resources

**A90.** Choose Standard SSD when:
- Budget is limited
- Performance requirements are moderate
- For dev/test environments
- For infrequently accessed data
Choose Premium SSD for production, databases, high-performance needs.

**A91.** 
- **Manual stop**: You manually stop the VM when needed
- **Auto-shutdown**: VM automatically stops at scheduled time (e.g., 7 PM daily)
Auto-shutdown prevents forgetting to stop VMs.

**A92.** 
- **Availability Zones**: For highest availability, protects against data center failures, use for critical production apps
- **Availability Sets**: For basic availability, protects against rack/server failures, lower cost than zones
Use Zones for mission-critical, Sets for standard production.

---

## Section 9: True/False - Answers

**A93.** **False** - You cannot change the region of a VM after creation. You must create a new VM in the desired region and migrate data.

**A94.** **False** - A VM can only belong to ONE Resource Group at a time.

**A95.** **Partially True** - You only pay for compute when running, but you still pay for disk storage even when stopped (deallocated).

**A96.** **False** - VMs do not need a Public IP. Many VMs (like databases) should only have private IPs for security.

**A97.** **False** - Data disks don't have an OS, they're just storage. The VM's OS (Windows or Linux) determines what it can use.

**A98.** **False** - Availability Zones protect against data center failures within a region, NOT entire region failures. For region failure protection, you need multi-region deployment.

**A99.** **False** - SSH is for Linux VMs. Windows VMs use RDP (Remote Desktop Protocol) on port 3389.

**A100.** **False** - Opening all ports is a major security risk. Only open the ports you actually need.

**A101.** **True** - Premium SSD offers better performance (faster IOPS, lower latency) but costs more than Standard HDD.

**A102.** **True** - You can resize a VM to a smaller size to reduce costs, but the VM must be stopped first.

---

## Section 10: Scenario-Based - Answers

**A103.** Three possible reasons users can't access the website:
1. **Port not open**: Ports 80/443 not opened in NSG
2. **No Public IP**: VM doesn't have a public IP address
3. **Web server not running**: The web server software (Apache, IIS, Nginx) isn't started on the VM
4. **Firewall on VM**: OS-level firewall blocking traffic
5. **DNS issue**: Domain name not pointing to VM's IP

**A104.** Three things to check for unexpected high bill:
1. **VMs running 24/7**: Check if dev/test VMs are left running unnecessarily
2. **Oversized VMs**: Check if VMs are larger than needed (e.g., using E16 when B2 would suffice)
3. **Premium storage**: Check if using Premium SSD when Standard would work
4. **Data transfer**: Check outbound data transfer costs
5. **Orphaned resources**: Check for disks, IPs not attached to any VM

**A105.** Considerations for Indian data residency:
- **Region**: Must use Central India or South India regions
- **Compliance**: Ensure data doesn't leave India
- **Backup**: Backup storage must also be in India region
- **Replication**: If using replication, keep it within India
- **Documentation**: Maintain compliance documentation

**A106.** E-commerce architecture for variable traffic:
- **Auto-scaling**: Use VM Scale Sets to automatically add VMs during high traffic
- **Load Balancer**: Distribute traffic across multiple VMs
- **Multiple VMs**: Start with 3-5 VMs, scale to 15-20 during sales
- **Availability Zones**: Deploy across zones for high availability
- **Caching**: Use Azure Cache to reduce database load
- **Monitoring**: Set up alerts for high traffic

**A107.** Disaster prevention measures:
1. **Regular backups**: Daily automated backups with 30-day retention
2. **Role-based access**: Don't give developers delete permissions on production
3. **Resource locks**: Apply "CanNotDelete" lock on critical VMs
4. **Separate environments**: Keep dev and production completely separate
5. **Audit logs**: Enable logging to track all actions

**A108.** Configuration for 3 VMs:
- **Web Server**: 
  - Public IP: Yes (users need to access)
  - NSG: Allow 80, 443 from anywhere; Allow 22/3389 from office IP only
- **Database**: 
  - Public IP: No (private only)
  - NSG: Allow 1433/3306 only from web server subnet; Deny all internet
- **Admin VM**: 
  - Public IP: Yes (for remote access)
  - NSG: Allow 22/3389 only from office IP address; Deny all other IPs

**A109.** Security measures for payment processing:
1. **Encryption**: Enable disk encryption and use HTTPS/TLS
2. **PCI DSS Compliance**: Follow payment card industry standards
3. **Network isolation**: Keep payment VMs in separate subnet
4. **No Public IP**: Payment processing should be internal only
5. **Strong authentication**: Use MFA for all admin access
6. **Audit logging**: Log all transactions and access
7. **Regular patching**: Keep VMs updated
8. **Penetration testing**: Regular security testing
9. **Key Vault**: Store encryption keys in Azure Key Vault
10. **DDoS protection**: Enable Azure DDoS protection

**A110.** Global company infrastructure design:
- **Multi-region deployment**:
  - USA: East US or West US region
  - Europe: West Europe or North Europe region
  - Asia: Southeast Asia or East Asia region
- **Traffic Manager**: Route users to nearest region
- **Data replication**: Replicate critical data across regions
- **Local compliance**: Ensure each region meets local regulations
- **Load balancers**: In each region for high availability
- **Backup strategy**: Region-specific backups
- **Cost optimization**: Use Reserved Instances for 24/7 VMs
- **Monitoring**: Centralized monitoring across all regions

---

## Scoring Guide

**90-110 correct (82-100%)**: Excellent! You have a strong understanding of Azure VMs. You're ready for the AZ-900 exam.

**70-89 correct (64-81%)**: Good! You understand most concepts. Review the questions you missed and focus on those areas.

**50-69 correct (45-63%)**: Fair. You have basic understanding but need more study. Review the main document and retake the quiz.

**Below 50 (less than 45%)**: Need significant review. Go through the main VM explanation document thoroughly and practice more.

---

## Key Topics to Master for AZ-900

1. ✅ VM basics and benefits
2. ✅ VM sizes and series (B, D, E, F)
3. ✅ Networking (VNet, Subnet, NSG, Public IP)
4. ✅ Availability (Zones, Sets, Backups)
5. ✅ Security (Authentication, Encryption, NSG rules)
6. ✅ Cost management (Auto-shutdown, Reserved Instances)
7. ✅ Real-world scenarios and best practices

**Good luck with your AZ-900 exam! 🎯📚**
