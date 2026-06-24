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
- OpenSSL: Cryptographic toolkit used to generate self-signed certificates and enable HTTPS encryption for secured web communications.
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

Starting MySQL.

<img width="631" height="279" alt="image" src="https://github.com/user-attachments/assets/92553d7e-b2cd-4eca-b826-f540f0d97ab1" />

Creating a new database DVWA.

<img width="299" height="58" alt="image" src="https://github.com/user-attachments/assets/1518edc1-e755-4e46-918d-2712262cb3d8" />

Creating new user identified by their password and received an error because the password did not satisfy the policy requirement. I proceeded to update the policy, then successfully resubmitted the query.

<img width="667" height="463" alt="image" src="https://github.com/user-attachments/assets/59cbed71-b950-46af-baf7-66c96edc9f0c" />

Granting access to the user, flushed privileges, then exited MySQL.

<img width="1009" height="230" alt="image" src="https://github.com/user-attachments/assets/dec5717e-9082-4bd9-a68a-9d802bff84cb" />

Initializing DVWA.

<img width="1007" height="637" alt="image" src="https://github.com/user-attachments/assets/09d024d4-257a-4b86-825d-e99a413e76f7" />

<img width="1008" height="206" alt="image" src="https://github.com/user-attachments/assets/7873d650-ada0-4d44-870b-b8fe596f3ae5" />

Changing DVWA's listening port to 8080 as Apache listens to port 80 by default.

Part 1

<img width="441" height="65" alt="image" src="https://github.com/user-attachments/assets/8df7f587-0799-4d7a-b5b1-fe5d3efff1ee" />

Part 2

<img width="748" height="329" alt="image" src="https://github.com/user-attachments/assets/5798ea8f-c932-45d6-8cfd-1872c440adba" />

Updating the default virtual host to 8080.

Part 1

<img width="623" height="24" alt="image" src="https://github.com/user-attachments/assets/07ee5d7a-5df4-4962-a487-127449517093" />

Part 2

<img width="1002" height="615" alt="image" src="https://github.com/user-attachments/assets/21250772-886b-4e88-ac02-67037420a690" />

Restarting Apache to register the changes.

<img width="1003" height="57" alt="image" src="https://github.com/user-attachments/assets/99069813-f93c-4633-847b-644663d6897a" />

Creating a table in my database called test_users containing usernames and passwords.

<img width="350" height="134" alt="image" src="https://github.com/user-attachments/assets/b970189c-a68c-43c1-ac91-298e6a86e2e3" />

Adding users to the table above.

<img width="477" height="197" alt="image" src="https://github.com/user-attachments/assets/72ec45fd-494d-4a9b-ae16-b4ddb9f6006e" />

Installing Docker.

<img width="966" height="330" alt="image" src="https://github.com/user-attachments/assets/33e40574-6cff-40fc-a53f-64d52af69e13" />

Starting, enabling and confirming the Docker version.

<img width="1001" height="332" alt="image" src="https://github.com/user-attachments/assets/907ec8c0-3c8f-4764-9ec0-185b72b62637" />

Generating Self Signed Certificates (priv.crt, priv.csr, priv.key)

<img width="1008" height="695" alt="image" src="https://github.com/user-attachments/assets/ddbb934f-1a9f-4828-8028-cb9bf97d950b" />

<img width="1004" height="596" alt="image" src="https://github.com/user-attachments/assets/6a15ce5b-f2e7-4470-a5cf-73fb692007b5" />

Importing SSL certificate priv.crt below to SafeLine WAF.

<img width="1003" height="581" alt="image" src="https://github.com/user-attachments/assets/45e46dfc-2db3-4d2c-ac0a-7ca7b94f35de" />

Successfully logged into SafeLine WAF.

<img width="1066" height="882" alt="image" src="https://github.com/user-attachments/assets/a4f118e0-4ee6-45bd-a820-ac6ae4fbd1af" />

Adding priv.crt and priv.key SSL Certificate previously generated above.

<img width="1066" height="722" alt="image" src="https://github.com/user-attachments/assets/c2204b44-30d7-4a25-a904-81cb962b7fab" />

<img width="876" height="158" alt="image" src="https://github.com/user-attachments/assets/f3265dcf-88d6-4f61-9f92-096503ab2bb6" />

Adding application and deleting port 80 because it is not encrypted, then selecting the previously added certificate above as well as the upstream.

<img width="1066" height="720" alt="image" src="https://github.com/user-attachments/assets/f5113a43-8710-4dd9-bb1a-e9c5e0ce1965" />

Application added successfully and it will be forcing all traffic to access the website only on port 443.

<img width="1070" height="520" alt="image" src="https://github.com/user-attachments/assets/a3c39c0e-546e-4d02-a571-b3b47ed9aa35" />


































