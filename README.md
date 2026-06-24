# Building-Home-Lab-and-deploy-Safeline-WAF

## Objective
The SafeLine Web Application Firewall Deployment project aimed to build a fully functional security environment from the ground up, simulating how organizations protect web-facing infrastructure against modern threats. The primary focus was on deploying and configuring SafeLine WAF within a virtualized lab, where I provisioned Ubuntu and Kali Linux virtual machines in VirtualBox, stood up an Apache web server, and secured communications by generating and implementing self-signed certificates using OpenSSL. This hands-on experience was designed to deepen my understanding of web application security architecture, certificate management, and the operational processes involved in positioning a WAF to inspect, filter, and defend against malicious web traffic in a real-world enterprise environment.

### Skills Learned
- Deployed and configured SafeLine Web Application Firewall (WAF) in a virtualized environment, gaining hands-on experience with web traffic        inspection and threat filtering.
- Provisioned and managed Ubuntu and Kali Linux virtual machines using VirtualBox, developing proficiency in hypervisor configuration and virtual   network setup.
- Installed and configured an Apache web server, reinforcing understanding of web server architecture and service management in a Linux             environment.
- Generated and implemented self-signed certificates using OpenSSL, building practical knowledge of Public Key Infrastructure (PKI), encryption     protocols, and securing web communications over HTTPS.
- Demonstrated ability to integrate multiple security technologies within a single lab environment, simulating real-world enterprise network        segmentation and defense-in-depth strategies.
- Strengthened Linux command-line proficiency across both Ubuntu and Kali Linux distributions, executing system administration tasks essential to   SOC and security engineering roles.
- Developed troubleshooting and problem-solving skills by independently configuring and resolving technical challenges across networking,           security tooling, and system services from scratch.

### Tools Used
- SafeLine WAF: Web application firewall used to inspect and filter inbound web traffic, providing protection against common web-based attacks such as SQL injection and cross-site scripting (XSS).
- VirtualBox: Hypervisor platform used to provision and manage Ubuntu and Kali Linux virtual machines, simulating an isolated lab network environment.
- Ubuntu: Primary Linux distribution used to host the Apache web server and SafeLine WAF deployment.
- Kali Linux: Security-focused Linux distribution used for testing and validating WAF configurations against simulated attack traffic.
- Apache HTTP Server: Open-source web server installed and configured to serve as the protected web application behind the SafeLine WAF.
- OpenSSL — Cryptographic toolkit used to generate self-signed certificates and enable HTTPS encryption for secured web communications.
- Linux CLI (Bash): Primary interface used across both Ubuntu and Kali Linux for system configuration, service management, and deployment tasks.

### Steps
I have started by launching both Kali Linux and Ubuntu

<img width="712" height="329" alt="image" src="https://github.com/user-attachments/assets/decf2d8a-9bbf-43d5-a491-145ea77f01bd" />

I will run the ifconfig on both machines to ensure they are both on the same network for my project.
Kali

<img width="636" height="458" alt="image" src="https://github.com/user-attachments/assets/26f18edc-ae7d-4834-9ac4-ddfd1f45a7bd" />

Ubuntu

<img width="731" height="256" alt="image" src="https://github.com/user-attachments/assets/d47917cb-53df-4ba4-b600-915dfcc54f6a" />

Next I proceeded to install the SafeLine firewall. However, because of the missing curl command, I have installed the curl command.

<img width="810" height="607" alt="image" src="https://github.com/user-attachments/assets/2af58c40-a957-4ccb-87f0-828cd34e2b3e" />

I have deployed SafeLine, however, since the command was denied, I resolved it by elevating my privilege by running it as a root command.

<img width="1005" height="366" alt="image" src="https://github.com/user-attachments/assets/dee69fb1-564d-4ed2-ba57-1604bf6c8f9c" />

SafeLine installation completed successfully.

<img width="769" height="668" alt="image" src="https://github.com/user-attachments/assets/e440c586-57f9-40a5-8a3d-a750b0b291f6" />

Installed Net-Tools and OpenSSL.

<img width="522" height="294" alt="image" src="https://github.com/user-attachments/assets/140a0131-2465-40ab-a998-d9ec5506c73d" />

Installing Apache2, PHP, MySQL

<img width="965" height="201" alt="image" src="https://github.com/user-attachments/assets/cf06ecf1-b67f-4f53-b405-679177621d5e" />

Hardening MySQL by setting a root password, remove anonymous users and disable remote root login.

<img width="555" height="245" alt="image" src="https://github.com/user-attachments/assets/b8d622bb-be79-4b9b-a13d-cc5bc6293a10" />

<img width="555" height="245" alt="image" src="https://github.com/user-attachments/assets/dc66c476-f63c-4174-96c2-d8115845fa8d" />

Installing and configuring Damn Vulnerable Web App(DVWA). However, the git command was not installed and stalled the installation. I first installed the git command, then resumed the installation of DVWA.
Part 1

<img width="984" height="726" alt="image" src="https://github.com/user-attachments/assets/d9418061-e482-4064-8919-6d3d36bb430d" />

Part 2

<img width="672" height="171" alt="image" src="https://github.com/user-attachments/assets/6fb9b474-9e1a-40f4-a106-d5805a5d2f70" />

Setting file permissions.

<img width="553" height="58" alt="image" src="https://github.com/user-attachments/assets/e58844b3-1e11-4ca4-b7b6-80adc95a5050" />

Updated the Vulnerable Web Application (DVWA Database) config file before configuring the database.

<img width="654" height="94" alt="image" src="https://github.com/user-attachments/assets/584f01eb-e679-4428-a4f2-6067a9c9f535" />

Configured DVWA database.

<img width="1006" height="822" alt="image" src="https://github.com/user-attachments/assets/d842b61c-2119-4d79-8184-ab24b33a0429" />











