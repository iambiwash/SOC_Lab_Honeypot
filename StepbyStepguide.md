# 🛠️ Step-by-Step Guide: Home SOC Lab Setup  

## 📌 Overview  
This guide provides **detailed instructions** for setting up the Home SOC Lab, explaining **key configurations** and their significance.  

---

## 1️⃣ **Azure Subscription Setup**
🔹 **Sign Up for an Azure Free Account** → [Azure Free Tier](https://azure.microsoft.com/en-us/free/)  
🔹 A credit card is required for identity verification, but **you won’t be charged for free-tier usage**.  

---

## 2️⃣ **Create the Virtual Machine (VM)**
1. **Log in to the Azure Portal** → [portal.azure.com](https://portal.azure.com/)  
2. Navigate to **Virtual Machines** → Click **Create** → **Virtual Machine**.  
3. **Select OS:** Choose **Windows Server 2019** for the honeypot.  
4. **Set Username & Password** → This will be used for **Remote Desktop (RDP)**.  
5. **Enable Public IP** → Required for external attack attempts.  
6. **Network Configuration:**
   - Ensure **Allow RDP (Port 3389)** is enabled.
   - **Disable Firewall** inside the VM after deployment.

📸 **Screenshot Example:**  
![VM Setup](assets/images/vm_setup.png)

---

## 3️⃣ **Network Security Group (NSG) Configuration**
The **NSG (Network Security Group)** controls incoming and outgoing traffic.  
**Goal:** Allow attackers to attempt unauthorized access.

### **Steps to Open All Ports:**
1. In Azure Portal → Go to **Virtual Machines** → Select your VM.
2. Click **Networking** → **Add Inbound Rule**.
3. **Rule Configuration:**
   - **Source:** Any  
   - **Destination:** Virtual Machine  
   - **Protocol:** Any  
   - **Action:** Allow  
4. **Save Changes.**  

🚨 **Warning:** This makes your VM highly vulnerable! Do **not** use this setup in production.

---

## 4️⃣ **Monitoring Attack Attempts**
Once the **honeypot VM** is online, attackers will attempt to gain access.

### **How to View Logs:**
1. **Open Event Viewer** inside the VM.
2. Navigate to **Windows Logs → Security**.
3. Look for **Event ID 4625 (Failed Login Attempts)**.

📸 **Event Viewer Example:**  
![Event Viewer](assets/images/event_viewer.png)

---

## 5️⃣ **Forward Logs to Microsoft Sentinel (SIEM)**
🔹 **Step 1:** Create a **Log Analytics Workspace**  
🔹 **Step 2:** Connect **Windows Security Logs** to Sentinel  
🔹 **Step 3:** Configure Kusto Query Language (KQL) for analysis  

📌 **Example KQL Query for Failed Logins:**
```kql
SecurityEvent
| where EventID == 4625
| project TimeGenerated, Account, IPAddress, FailureReason
| order by TimeGenerated desc
📸 Sentinel Dashboard Example:

6️⃣ Mapping Attacker Locations
Extract IP addresses from Sentinel logs.
Use MaxMind GeoIP Database to get locations.
Generate a world map showing attacker sources.
📸 Geographic Attack Map Example:

🎯 Final Thoughts
By completing this project, you have:
✅ Set up a honeypot to attract cyber attacks.
✅ Configured log collection and SIEM integration.
✅ Analyzed failed login attempts using KQL.
✅ Mapped attacker locations to understand real-world threats.

🔗 Additional Resources
📖 Microsoft Sentinel Documentation → Read Here
📖 Kusto Query Language (KQL) Guide → Learn More

📞 Contact & Support
📧 Email: your.email@example.com
🐦 Twitter: @yourhandle
🔗 LinkedIn: Your Profile

🔒 Disclaimer: This project is for educational purposes only.

yaml
Copy
Edit

---

### ✅ **Summary of Files:**
1. **`README.md`** → **Project overview**, **video walkthrough**, and scope.  
2. **`SETUP_GUIDE.md`** → **Detailed step-by-step instructions** with explanations.  

Both files are structured for **clarity and ease of navigation**, ensuring a professional and engaging experience for users. 🚀  

Let me know if you need any further modifications! 🎯
