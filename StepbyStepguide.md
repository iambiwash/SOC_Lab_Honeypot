layout: default
title: Home SOC Lab in Azure

🛡️ Step-by-Step Guide: Home SOC Lab in Azure

📌 Introduction

This guide provides a step-by-step walkthrough to set up a Home Security Operations Center (SOC) Lab using Microsoft Azure. By the end of this guide, you will have a honeypot virtual machine (VM) that attracts attackers, forwards logs to a central repository, and analyzes attack patterns using Microsoft Sentinel.

🔹 Prerequisites

✔️ A free Azure account (or pay-as-you-go if needed)✔️ Basic understanding of virtual machines & networking✔️ A Windows or Mac computer with an internet connection

## 📺 Video Walkthrough
<iframe width="560" height="315" src="https://www.youtube.com/embed/g5JL2RIbThM" frameborder="0" allowfullscreen></iframe>


🚀 Step 1: Create an Azure Account

1️⃣ Go to Azure Free Account.2️⃣ Click Start Free and sign up using a personal email.3️⃣ Enter your credit card for verification (no charges for free-tier usage).4️⃣ Once verified, log in to the Azure Portal at portal.azure.com.

🏗️ Step 2: Set Up the Honeypot Virtual Machine

2.1 Create a Resource Group

1️⃣ In the Azure Portal, search for Resource Groups.2️⃣ Click Create, enter a name (e.g., RG-SOC-Lab), and select a region (e.g., East US).3️⃣ Click Review + Create, then Create.

2.2 Create a Virtual Network

1️⃣ Search for Virtual Networks in the Azure Portal.2️⃣ Click Create, enter a name (e.g., VNet-SOC-Lab), and assign it to your resource group.3️⃣ Click Review + Create, then Create.

2.3 Deploy a Virtual Machine (VM)

1️⃣ Search for Virtual Machines and click Create.2️⃣ Select your resource group.3️⃣ Enter a name (e.g., CorpNet-East1).4️⃣ Select Windows 10 as the operating system.5️⃣ Choose a Standard DS1 v2 instance (free-tier eligible).6️⃣ Set the username (labuser) and password (CyberLab123!).7️⃣ Click Review + Create, then Create.

2.4 Configure Network Security Group (NSG)

1️⃣ Go to Networking under the VM settings.2️⃣ Remove any existing inbound security rules.3️⃣ Click Add inbound rule and set:

Source: Any

Protocol: Any

Port Range: *

Action: Allow4️⃣ Click Save.

📡 Step 3: Configure Log Collection

3.1 Install Azure Monitoring Agent

1️⃣ Search for Extensions + Applications under the VM.2️⃣ Click Add Extension, select Azure Monitor Agent.3️⃣ Click Install.

3.2 Set Up Log Analytics Workspace

1️⃣ Search for Log Analytics Workspace.2️⃣ Click Create, enter a name (e.g., LAW-SOC-Lab), and assign it to your resource group.3️⃣ Choose East US.4️⃣ Click Review + Create, then Create.

3.3 Link VM to Log Analytics Workspace

1️⃣ Go to the Log Analytics Workspace you just created.2️⃣ Select Agents Management.3️⃣ Copy the Workspace ID and Primary Key.4️⃣ Go back to your VM, select Diagnostics Settings, and add the Workspace ID & Key.

🔍 Step 4: Set Up Microsoft Sentinel for Analysis

4.1 Enable Sentinel

1️⃣ Search for Microsoft Sentinel in Azure.2️⃣ Click Create and assign it to your log analytics workspace.

4.2 Connect Logs to Sentinel

1️⃣ Open Sentinel, click Data Connectors.2️⃣ Search for Security Events and enable it.3️⃣ Click Connect and enable Windows Security Events collection.

4.3 Query Attack Logs

1️⃣ Open Sentinel, go to Logs.2️⃣ Run the query:

SecurityEvent
| where EventID == 4625 // Failed login attempts
| project TimeGenerated, Account, IPAddress

3️⃣ Review failed login attempts.

🗺️ Step 5: Map Attacks in Sentinel

5.1 Upload IP Geolocation Watchlist

1️⃣ Download the GeoIP List (provided in the resources).2️⃣ Go to Sentinel > Watchlists.3️⃣ Click Create Watchlist, upload the GeoIP file.

5.2 Visualize Attacks on a Map

1️⃣ Open Workbooks in Sentinel.2️⃣ Click New Workbook > Edit.3️⃣ Copy & Paste the JSON attack map template.4️⃣ Click Save, and view real-time attack locations on a global map.

🎯 Conclusion

This Home SOC Lab provides hands-on experience in cloud security monitoring. You will:

🔍 Detect & analyze cyber threats in real-time.

⚡ Use SIEM (Microsoft Sentinel) to visualize attack sources.

🚀 Improve cybersecurity skills through practical learning.

✅ Next Steps

✅ Leave the honeypot running for 24 hours to collect data.

✅ Experiment with KQL queries for deeper analysis.

✅ Explore Microsoft Sentinel alerts for automated threat detection.

🚀 Take your cybersecurity skills to the next level with this project! 🔥
