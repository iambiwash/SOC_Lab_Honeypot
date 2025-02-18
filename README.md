Home SOC Lab in Azure: Cybersecurity Project

Overview

This project is designed to help cybersecurity enthusiasts set up a basic home SOC (Security Operations Center) lab using Microsoft Azure. The lab involves creating a honeypot—a deliberately vulnerable virtual machine (VM)—that attracts attackers. By monitoring attack attempts in real-time, participants can learn about log analysis, threat detection, and security monitoring, making it an excellent hands-on project for a cybersecurity resume.

Purpose

The goal of this lab is to:

Deploy a honeypot VM on Azure that is open to public internet attacks.

Collect and analyze attack logs using a centralized logging system.

Connect logs to Microsoft Sentinel (SIEM) for interactive analysis.

Visualize attack origins on a map using IP geolocation data.

This setup mimics real-world security operations and helps users understand how security teams detect and respond to threats.

Project Scope

1. Setting Up Azure Environment

Create a free Azure subscription (or use pay-as-you-go).

Set up a resource group to organize cloud resources.

Deploy a Windows-based Virtual Machine (VM) to act as a honeypot.

2. Configuring Network Security

Create a virtual network to connect the VM.

Disable all firewalls to make the honeypot attractive to attackers.

Modify the network security group (NSG) to allow all inbound traffic.

3. Log Management & Forwarding

Use Windows Event Viewer to check failed login attempts.

Configure Log Analytics Workspace as a central log repository.

Integrate Azure Monitor Agent to forward logs to Microsoft Sentinel.

4. Analyzing Attacks with SIEM

Use Kusto Query Language (KQL) to filter logs and identify failed login attempts.

Create a watchlist of attacker IP addresses and map them to geographic locations.

Visualize attack patterns using an interactive dashboard in Sentinel.

Tools & Technologies Used

Cloud Provider: Microsoft Azure (Free Subscription)

Operating System: Windows 10/Server (for VM)

SIEM Solution: Microsoft Sentinel

Logging Service: Azure Log Analytics Workspace

Query Language: Kusto Query Language (KQL)

Visualization: Attack heatmap using Sentinel Workbooks

Benefits of This Lab

✅ Hands-on Cybersecurity Experience – Understand attacker behavior and logging techniques.✅ Practical SIEM Training – Gain real-world experience in log analysis using Sentinel.✅ Resume-Worthy Project – Showcase your skills in cloud security and threat intelligence.✅ No Cost Setup – Uses a free-tier Azure subscription, making it accessible to all.

Next Steps



Let's build a cybersecurity lab and start analyzing real-world attacks today!

