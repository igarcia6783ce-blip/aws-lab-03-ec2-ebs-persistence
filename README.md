# AWS EC2 + EBS Persistent Storage Lab (Lab 03)

> Note: Commands and configuration verified during live AWS lab session using EC2 + EBS.
> 
## Overview
This project demonstrates how to configure persistent storage on an AWS EC2 instance using an EBS volume, including formatting, mounting, and ensuring data persists across reboots using fstab.



## Objectives
- Launch EC2 instance in AWS
- Create and attach EBS volume
- Format and mount EBS volume
- Configure persistent mounting using fstab
- Verify persistent storage after reboot

- ## Key Concepts Learned
- How EBS volumes provide persistent storage
- How to format and mount storage in Linux
- How fstab ensures automatic mounting after reboot
- Difference between temporary and persistent storage on EC2
- 
## Real-World Use Case
This setup can be used for storing application data, logs, or databases that must persist even if the EC2 instance is restarted.
- 

## Architecture
EC2 (Linux) with attached EBS volume mounted to /data and persisted via fstab

## Steps Performed

### 1. Launching EC2 Instance
- Amazon Linux instance deployed
- SSH access configured
- Key pair authentication used

### 2. Create and Attach EBS Volume
- New EBS volume created in same Availability Zone
- Volume attached to EC2 instance

### 3. Format and Mount Volume
Commands used:

```bash
lsblk
sudo mkfs -t xfs /dev/nvme1n1
sudo mkdir /data
sudo mount /dev/nvme1n1 /data
sudo blkid
sudo nano /etc/fstab
sudo mount -a
```
