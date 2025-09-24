
# AWS EC2 and Git Setup Documentation

This document outlines the steps for launching an Amazon Linux 2023 EC2 instance, connecting to it via SSH, and configuring Git.

-----

## 1\. AWS EC2 Instance Launch and Connection

### 1.1. EC2 Instance Configuration

The following parameters were used to launch the EC2 instance:

| Parameter | Value |
| :--- | :--- |
| **Server/AMI** | Amazon Linux 2023 |
| **Instance Type** | t3.micro |
| **Key Pair Name** | `key.pem` |
| **Security Group (SG)** | SSH traffic on port **22** from **0.0.0.0/0** (anywhere) |

### 1.2. SSH Connection Command

The command used to connect to the instance (replace the example IP with your actual public DNS/IP):

```bash
ssh -i "key.pem" ec2-user@ec2-3-80-195-140.compute-1.amazonaws.com
```

-----

## 2\. Git Installation and Verification

Once connected to the EC2 instance, the following commands were executed to update the system and install Git:

### 2.1. System Update and Git Installation

| Command | Purpose |
| :--- | :--- |
| `sudo yum update` | Updates the package lists and installed packages on the Amazon Linux 2023 system. |
| `sudo yum install git -y` | Installs the Git version control system. The `-y` flag confirms all prompts automatically. |

### 2.2. Git Version Verification

| Command | Purpose |
| :--- | :--- |
| `git --version` | Confirms that Git is installed and displays the installed version number. |

-----

## 3\. Global Git Configuration

After installation, the following global configuration settings were applied to associate a user name and email with future Git commits from this instance.

### 3.1. Setting User Name and Email

| Command | Purpose |
| :--- | :--- |
| `git config --global user.name "prajwal ahirrao"` | Sets the **user name** to be recorded in all subsequent commits. |
| `git config --global user.email "ahirraoprajwal@gmail.com"` | Sets the **user email** to be recorded in all subsequent commits. |

### 3.2. Verification of Configuration

| Command | Purpose |
| :--- | :--- |
| `git config --list` | Displays all configuration settings, including the newly set global `user.name` and `user.email`. |
