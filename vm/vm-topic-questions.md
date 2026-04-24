# Azure Virtual Machines - Practice Questions for AZ-900

## Section 1: Basic Concepts (15 Questions)

**Q1.** What is a Virtual Machine in Azure?

**Q2.** What are the three main benefits of using VMs in the cloud instead of buying physical servers?

**Q3.** You need to create a VM in Azure. What is the first thing you must have before creating any resources?

**Q4.** What is a Resource Group and why is it important?

**Q5.** You created a VM but forgot which Resource Group you put it in. Can a single VM belong to multiple Resource Groups?

**Q6.** What does "Region" mean when creating a VM?

**Q7.** Your company has customers in India, USA, and Germany. Where should you deploy VMs to give the best performance to all users?

**Q8.** What is the difference between stopping a VM and deleting a VM in terms of cost?

**Q9.** What is an "Image" in the context of Azure VMs?

**Q10.** You need to run a Windows application. Which Image should you choose: Ubuntu 20.04 or Windows Server 2022?

**Q11.** What determines the computing power (CPU and RAM) of a VM?

**Q12.** What is the difference between an OS Disk and a Data Disk?

**Q13.** What is a Public IP address and when would you need one for your VM?

**Q14.** What is the purpose of Auto-shutdown feature?

**Q15.** Can you change the size of a VM after it has been created?

---

## Section 2: VM Sizes and Series (10 Questions)

**Q16.** What is the B-series VM size best used for?

**Q17.** Your application needs to perform heavy calculations quickly. Which VM series should you choose: B-series, D-series, E-series, or F-series?

**Q18.** You are setting up a SQL Server database that needs lots of memory. Which VM series is most appropriate?

**Q19.** What does "D2s_v3" mean in a VM size name?

**Q20.** You have a test website with very low traffic. Which is more cost-effective: B1s or E16s_v3?

**Q21.** A VM with 64 CPUs and 432 GB RAM would typically be used for what type of workload?

**Q22.** What is the main difference between Standard HDD, Standard SSD, and Premium SSD disks?

**Q23.** Your VM needs to process machine learning models. What special type of VM should you consider?

**Q24.** You need a VM for development and testing, not production. Should you choose a high-performance or budget-friendly size?

**Q25.** Can you attach multiple data disks to a single VM?

---

## Section 3: Networking (12 Questions)

**Q26.** What is a Virtual Network (VNet)?

**Q27.** What is a Subnet and how is it different from a VNet?

**Q28.** You have 3 VMs in the same VNet. Can they communicate with each other privately?

**Q29.** What is a Network Security Group (NSG)?

**Q30.** You want to allow web traffic to your VM. Which port should you open: 22, 80, 443, or 3389?

**Q31.** What is the difference between port 80 and port 443?

**Q32.** You need to remotely access a Windows VM from your home computer. Which port should be open?

**Q33.** You need to remotely access a Linux VM using SSH. Which port should be open?

**Q34.** Is it a good security practice to open all ports on a VM? Why or why not?

**Q35.** What is a Load Balancer used for?

**Q36.** You have a database VM that should only be accessed by your web application VMs, not from the internet. Should it have a Public IP?

**Q37.** What is the benefit of having multiple VMs behind a Load Balancer?

---

## Section 4: Availability and Reliability (10 Questions)

**Q38.** What is an Availability Zone?

**Q39.** What is the difference between an Availability Zone and an Availability Set?

**Q40.** Your application is critical and cannot afford any downtime. Should you use a single VM or multiple VMs across Availability Zones?

**Q41.** What happens if you deploy a VM with "No redundancy" option and the physical server fails?

**Q42.** You have a VM in East US Availability Zone 1. The zone goes down. If you had deployed across 3 zones, what would happen?

**Q43.** What is the purpose of VM backups?

**Q44.** How often should you backup a production database VM: never, monthly, weekly, or daily?

**Q45.** What is the difference between a backup and a snapshot?

**Q46.** Can you restore a VM from a backup if it gets corrupted?

**Q47.** What is Boot Diagnostics used for?

---

## Section 5: Security (12 Questions)

**Q48.** What are the two main ways to authenticate to a VM: username/password or SSH key?

**Q49.** Which is more secure for Linux VMs: password or SSH key?

**Q50.** You created a VM with username "admin" and a simple password "12345". Is this secure?

**Q51.** What does "encryption at rest" mean?

**Q52.** What does "encryption in transit" mean?

**Q53.** Should production VMs be accessible from any IP address on the internet?

**Q54.** What is the principle of "least privilege" in security?

**Q55.** You have a VM that only needs to be accessed from your office. How should you configure the NSG?

**Q56.** What is Multi-Factor Authentication (MFA)?

**Q57.** Is it safe to store passwords in plain text in your application code?

**Q58.** What should you do if you accidentally expose your VM's admin password publicly?

**Q59.** Why should you regularly update and patch your VMs?

---

## Section 6: Cost Management (10 Questions)

**Q60.** What are the main factors that determine the cost of running a VM?

**Q61.** You have a development VM that you only use during work hours (9 AM - 6 PM). How can you save costs?

**Q62.** Does a stopped (deallocated) VM still incur charges?

**Q63.** What is the difference between "Stop" and "Stop (deallocate)" for a VM?

**Q64.** What are Reserved Instances and how do they save money?

**Q65.** You are running a B1s VM 24/7 but it's only using 10% CPU. What should you do?

**Q66.** What costs more per month: a VM running 24/7 or a VM running only 8 hours per day?

**Q67.** Do you pay for disk storage even when the VM is stopped?

**Q68.** What is the benefit of using auto-shutdown for test VMs?

**Q69.** Is it cheaper to run one large VM or multiple smaller VMs for the same total resources?

---

## Section 7: Real-World Scenarios (15 Questions)

**Q70.** You need to host a small company website. What type of VM configuration would you choose?

**Q71.** A financial company needs to store EU customer data. Can they store it in a US region?

**Q72.** Your web application suddenly gets 10x more traffic. What Azure feature can automatically add more VMs?

**Q73.** You need to run a batch processing job that takes 2 hours every night. Should the VM run 24/7?

**Q74.** A VM is running slow. What metrics should you check first?

**Q75.** Your company has a compliance requirement to keep all logs for 7 years. What should you configure?

**Q76.** You accidentally deleted a critical VM. Can you recover it?

**Q77.** Your database VM crashed and won't start. What Azure feature helps you see what went wrong?

**Q78.** You need to test a new application version without affecting production. What should you do?

**Q79.** A trading application needs the fastest possible response time. Which disk type should you use?

**Q80.** You have 50 VMs for different projects. How should you organize them?

**Q81.** Your VM is getting attacked from multiple IP addresses. What should you configure to block them?

**Q82.** You need to connect 10 different VMs so they can communicate privately. What do you create?

**Q83.** Your application needs to be available even if an entire Azure region goes down. What should you implement?

**Q84.** A developer needs temporary access to a production VM for debugging. What security practice should you follow?

---

## Section 8: Comparison Questions (8 Questions)

**Q85.** What's the difference between a VM and a physical computer?

**Q86.** When would you use a B-series VM vs an F-series VM?

**Q87.** What's the difference between horizontal scaling (more VMs) and vertical scaling (bigger VM)?

**Q88.** When should you use a Public IP vs keeping a VM private?

**Q89.** What's the difference between a Resource Group and a Subscription?

**Q90.** When would you choose Standard SSD over Premium SSD?

**Q91.** What's the difference between stopping a VM and using auto-shutdown?

**Q92.** When should you use Availability Zones vs Availability Sets?

---

## Section 9: True/False Questions (10 Questions)

**Q93.** True or False: You can change the region of a VM after it's created.

**Q94.** True or False: A VM can belong to multiple Resource Groups at the same time.

**Q95.** True or False: You only pay for a VM when it's running.

**Q96.** True or False: All VMs must have a Public IP address.

**Q97.** True or False: You can attach both Windows and Linux data disks to the same VM.

**Q98.** True or False: Availability Zones protect against entire region failures.

**Q99.** True or False: SSH is used to connect to Windows VMs.

**Q100.** True or False: You should open all ports on a VM for maximum flexibility.

**Q101.** True or False: Premium SSD is faster but more expensive than Standard HDD.

**Q102.** True or False: You can resize a VM to a smaller size to save costs.

---

## Section 10: Scenario-Based Questions (8 Questions)

**Q103.** Scenario: You created a web server VM but users cannot access your website. The VM is running fine. What could be the problem? (List 3 possible reasons)

**Q104.** Scenario: Your monthly Azure bill is $5,000 but you expected $1,000. What are 3 things you should check?

**Q105.** Scenario: You need to deploy an application that must comply with Indian data residency laws. What should you consider when creating VMs?

**Q106.** Scenario: Your company runs an e-commerce website. During festival sales, traffic increases 5x. How should you architect your VMs?

**Q107.** Scenario: A developer accidentally deleted all data on a production VM. What could have prevented this disaster?

**Q108.** Scenario: You have 3 VMs: Web server (needs internet access), Database (private), Admin VM (access from office only). How should you configure Public IPs and NSGs for each?

**Q109.** Scenario: Your application needs to process credit card payments. What security measures should you implement on your VMs?

**Q110.** Scenario: You're setting up VMs for a global company with offices in USA, Europe, and Asia. How should you design the infrastructure?

---

## Total: 110 Questions

**Scoring Guide:**
- 90-110 correct: Excellent - Ready for AZ-900
- 70-89 correct: Good - Review weak areas
- 50-69 correct: Fair - More study needed
- Below 50: Need significant review

**Good luck with your AZ-900 preparation! 🎯**
