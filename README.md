# AWS EC2 + EBS Persistent Storage Lab (Lab 03)

> Note: Commands and configuration verified during live AWS lab session using EC2 + EBS.

## Overview
This hands-on AWS lab demonstrates launching an EC2 instance, attaching and mounting an EBS volume, and configuring persistent storage on Linux.

## Objectives
- Launch EC2 instance in AWS
- Create and attach EBS volume
- Format and mount EBS volume
- Configure persistent mounting using fstab
- Verify persistent storage after reboot

## Architecture
EC2 (Linux) with attached EBS volume mounted to /data and persisted via fstab.

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
