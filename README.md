# Network-Traffic-Analysis

## Detecting FTP Security Risks with Wireshark

### Introduction

File Transfer Protocol (FTP) is an outdated but still widely used method for transferring files over a network. However, it poses severe security risks due to its lack of encryption. This project demonstrates how an attacker can capture FTP traffic using Wireshark, analyze security vulnerabilities, and exploit them using Metasploit. The goal is to highlight the risks of unencrypted FTP communication and recommend secure alternatives.

### Scenario

Jane, a security analyst, identifies a critical security flaw within her company’s internal network. The company relies on FTP for file transfers, unaware that it transmits credentials in plaintext. To raise awareness, Jane simulates an attack using Wireshark to capture and analyze FTP traffic, demonstrating how attackers can exploit insecure protocols in a corporate environment.

### Objective

This project aims to:

📄 Simulate an attack on an FTP connection by capturing and analyzing network traffic with Wireshark.

📄 Demonstrate the security risks of unencrypted FTP communication, such as credential exposure.

📄 Provide recommendations for secure alternatives like SFTP or FTPS to enhance network security.

### Environment Setup

To conduct this experiment, the following setup is used:

Kali Linux VM: Running Wireshark and Metasploit.

Metasploitable 2 VM: A vulnerable target machine with an active FTP service.

Virtual Network Configuration: Both machines are configured within the same virtual network for seamless communication.

## Step 1: Verify Communication Between Machines
### Test Connectivity: On Kali Linux, ping the Metasploitable 2 machine:

![VirtualBox_kali-linux-2024 3-virtualbox-amd64_06_02_2025_22_02_15](https://github.com/user-attachments/assets/13ac9e27-283b-46d1-a558-19dfda8f1110)

### Launch Metasploit Framework: Open the Metasploit console on Kali Linux

![VirtualBox_kali-linux-2024 3-virtualbox-amd64_06_02_2025_19_11_41](https://github.com/user-attachments/assets/6f3a2d3c-c378-4fbb-9708-f4bf75973a85)

### Identify active ports on Metasploitable 2

![VirtualBox_kali-linux-2024 3-virtualbox-amd64_06_02_2025_21_02_25](https://github.com/user-attachments/assets/88cea01c-2aee-4de1-9a65-c8f568a4a7f2)


## Step 2:Capture FTP Traffic with Wireshark 

### Open Wireshark on Kali Linux 

![VirtualBox_kali-linux-2024 3-virtualbox-amd64_06_02_2025_21_09_20](https://github.com/user-attachments/assets/98ff0bdf-d2ed-48a1-83c0-fbf5d13f069d)

### Select the Network Interface (eth0 or wlan0)

![VirtualBox_kali-linux-2024 3-virtualbox-amd64_06_02_2025_21_09_36](https://github.com/user-attachments/assets/456858a6-4338-4444-a666-c1fabcb79a1a)

### Apply filter to isolate FTP packets 

![VirtualBox_kali-linux-2024 3-virtualbox-amd64_06_02_2025_21_10_30](https://github.com/user-attachments/assets/8afe2cda-bb10-40b4-9520-0c00dd29d73a)


## Step 3: Analyse FTP Traffic in Wireshark

### Identify FTP Packets containing USER and PASS fields.

![VirtualBox_kali-linux-2024 3-virtualbox-amd64_06_02_2025_21_35_06](https://github.com/user-attachments/assets/1050c454-ab3d-4dfb-b1b6-5c70369ab9f3)

### Observe Credentials being transmitted in plaintext. 

#### Username: RbbuiE

#### Password: zMHG

#### 🚨 🚨 Credentials can be intercepted by attackers, leading to unauthorized access.

## Step 4: Exploiting FTP Backdoor with Metasploit

### Use a Known exploit for a FTP vulnerability

![VirtualBox_kali-linux-2024 3-virtualbox-amd64_06_02_2025_21_32_08](https://github.com/user-attachments/assets/40406fd4-5efb-4ac2-9312-9e06d61f4ed1)

If this process is successful, the attacker gains full access to the system.

## Potential Harm and Security Recommendations

### Risks of Unsecured FTP

#### ⚠︎ Credential Theft: Attackers can capture login credentials.

#### ⚠︎ Data Manipulation: Unencrypted file transfers allow unauthorized modifications.

#### ⚠︎ System Compromise: Exploiting FTP vulnerabilities can lead to complete system takeover.

### Recommended Security Measures

#### ✔ Disable Plaintext FTP: Use FTPS (FTP Secure) or SFTP (SSH File Transfer Protocol).

#### ✔ Implement Strong Authentication: Enforce key-based authentication and multi-factor authentication (MFA).

#### ✔ Regular Updates & Patching: Keep FTP services updated to mitigate vulnerabilities.

## Conclusion

This project demonstrates the real-world risks of using unencrypted FTP. By capturing login credentials through Wireshark and exploiting FTP vulnerabilities using Metasploit, this project exposes how attackers can compromise insecure systems. Organizations must adopt secure file transfer alternatives and enforce strong security controls to protect sensitive data.

## References

### Wireshark Official Documentation

### Metasploit Framework

### Secure FTP Best Practices


## Author 

### Lateefah Olagoke

#### (Cybersecurity Afocionado) 


