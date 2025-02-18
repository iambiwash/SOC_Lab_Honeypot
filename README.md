# 🛡️ Creating a Basic Home SOC Lab in the Cloud 🖥️☁️

![Cybersecurity Lab](assets/images/cybersecurity_lab.png)  

## 🚀 Introduction

In this tutorial, we will set up a **Basic Home SOC Lab** on a cloud platform using a **free Azure subscription**. This project is ideal for cybersecurity enthusiasts and professionals looking to gain hands-on experience with attack monitoring. 

Through this lab, we will:
- Deploy a **honeypot** (intentionally vulnerable virtual machine).
- **Monitor attack attempts** in real-time.
- **Analyze logs** using Microsoft Sentinel and Kusto Query Language (KQL).
- **Visualize cyber threats** using a geographic attack map.

✅ **Perfect for cybersecurity portfolios and SOC analyst training!**  

---

## 📌 Key Components

| **Component**        | **Description** |
|----------------------|----------------|
| 🌐 **Azure Subscription** | Free cloud platform for deployment |
| 🖥️ **Virtual Machine (VM)** | Windows-based system as a honeypot |
| 🔒 **Network Security Group** | Allows open inbound traffic for attack monitoring |
| 📊 **Log Forwarding** | Sends attack logs for analysis |
| 🛡️ **SIEM (Microsoft Sentinel)** | Connects logs for real-time monitoring |
| 🗺️ **Attack Mapping** | Displays attack origins on a world map |

---

## ⚙️ Step-by-Step Setup Guide

### 1️⃣ **Sign Up for an Azure Subscription**
📌 Go to [Azure Free Tier](https://azure.microsoft.com/en-us/free/) and create an account.  
A credit card is required for verification, but **you won’t be charged for free-tier usage.**  

---

### 2️⃣ **Deploy a Virtual Machine (VM)**  
- Create a **Resource Group** to organize all lab components.
- Set up a **Virtual Network** to allow connectivity.
- Deploy a **Windows-based VM** with a **public IP**.

**💡 Pro Tip:** Name your VM something **generic** to prevent attackers from realizing it’s a honeypot.

#### 📌 Virtual Machine Architecture
```plaintext
+---------------------------------------+
|          Azure Cloud                  |
| +-----------------------------------+ |
| |  Virtual Machine (Windows OS)     | |
| |  - Public IP Assigned             | |
| |  - RDP Enabled                    | |
| +-----------------------------------+ |
|    ⬇ Network Security Group (NSG) ⬇    |
| +-----------------------------------+ |
| |  Inbound Rules:                   | |
| |  - Allow all traffic (0.0.0.0/0)  | |
| +-----------------------------------+ |
+---------------------------------------+
📸 Screenshot Example:

3️⃣ Configure Network Security Group (NSG)
Open all inbound ports to attract potential attacks.
Disable Windows Firewall to allow unrestricted access.
🚨 Warning: This is for educational purposes only. Do not use this setup in a production environment.

📸 Example NSG Rule:

plaintext
Copy
Edit
Allow All Traffic | Inbound | Any | Any | Any | Any | Allow
4️⃣ Enable Log Collection & Monitoring
Access Windows Event Viewer on the VM.
Monitor Event ID 4625 (Failed Login Attempts).
Manually generate logs by attempting to log in with incorrect passwords.
📸 Log Monitoring Screenshot:

5️⃣ Integrate with Microsoft Sentinel
Create a Log Analytics Workspace in Azure.
Connect Sentinel for real-time log analysis.
Use Kusto Query Language (KQL) to analyze failed login attempts.
📌 Example KQL Query for Failed Logins:

kql
Copy
Edit
SecurityEvent
| where EventID == 4625
| project TimeGenerated, Account, IPAddress, FailureReason
| order by TimeGenerated desc
📸 Sentinel Log Analysis Screenshot:

6️⃣ Attack Visualization with Geographic Mapping
Extract IP addresses of attackers from logs.
Use MaxMind GeoIP Database to locate attack sources.
Plot results on a world map.
📸 Geographic Attack Map Example:

📽️ Video Demonstration
🎥 Watch the full setup walkthrough here:

🏁 Final Thoughts
Congratulations! 🎉 You have successfully set up a Home SOC Lab in the cloud.
This lab provides real-world cybersecurity experience, helping you: ✅ Understand how cyber attacks happen.
✅ Gain hands-on experience with log analysis.
✅ Improve your SOC Analyst and Threat Hunting skills.

🔗 Next Steps:

Add Threat Intelligence Feeds to analyze attacker patterns.
Implement automated alerts for failed logins.
Explore advanced SIEM integrations (Splunk, ELK Stack).
📚 Additional Resources
📖 Microsoft Sentinel Documentation → Read Here
📖 Kusto Query Language (KQL) Guide → Learn More

🤝 Connect with Me
If you found this project useful, feel free to connect and share your feedback!

📧 Email: your.email@example.com
🐦 Twitter: @yourhandle
🔗 LinkedIn: Your Profile

🔒 Disclaimer: This project is for educational purposes only. Do not deploy vulnerable systems in production environments.

markdown
Copy
Edit

### 📌 Features in this `README.md`
✅ **Professional Structure** with clear sections.  
✅ **Visual Elements** (images, diagrams, video thumbnails).  
✅ **Tables for Component Breakdown**.  
✅ **Code Blocks for KQL Queries**.  
✅ **Security Warnings & Pro Tips**.  
✅ **Clickable Links & Video Demonstration Placeholder**.

---
### 🛠 Next Steps
- Upload your `assets/` folder with **images, videos, and diagrams**.
- Replace placeholders with **your real video links**.
- Adjust the **contact information** in the "Connect with Me" section.

Let me know if you need any modifications! 🚀
