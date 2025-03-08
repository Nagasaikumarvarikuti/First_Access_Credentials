# Azure Logic App: First_Access_Credential  

## 🎯 **Purpose**  
- 🚀 Triggered by an incident in Microsoft Sentinel.  
- 🌐 Retrieves related IP addresses from the incident.  
- 🏠 Checks if the IP is private or public.  
- 🔍 If public, performs a VirusTotal lookup to check reputation.  
- 🛡️ Categorizes IP addresses as **Malicious** or **Clean** based on the reputation.  
- 🧑‍💻 **Validates sign-in activity** using Azure Monitor logs to check the authentication type and trust type.  
- 🔎 **Retrieves user audit logs** to confirm operations related to credential changes.  
- 📝 Logs the results in Microsoft Sentinel as a comment.  

---

## 📝 **Description**  
The **First_Access_Credential** Logic App is designed to monitor and analyze suspicious sign-ins and credential activities detected by Microsoft Sentinel. It retrieves related IP addresses and checks their reputation using VirusTotal. It then analyzes sign-in activity using Azure Monitor logs and retrieves audit logs to confirm operations related to credential changes. Based on the results, it logs comments in Microsoft Sentinel and sends an email notification if any malicious activity is detected.  

---

## 🔄 **Workflow Overview**  
1. **⚡ Trigger** – Triggered by an incident created in Microsoft Sentinel.  
2. **📡 Get IPs** – Retrieves IP addresses from the incident.  
3. **🔎 Check IP Type** – Identifies whether the IP is private or public.  
4. **🛡️ Reputation Check** – Uses VirusTotal to check the reputation of public IPs.  
5. **📑 Sign-In Logs** – Uses Azure Monitor to analyze sign-in activity from the retrieved IPs.  
6. **🔍 Audit Logs** – Retrieves audit logs to validate credential changes or unusual operations.  
7. **📝 Log Result** – Logs the result in the incident as a comment.  
8. **📧 Email Notification** – Sends an email notification if a malicious IP is detected.  

---

## 🔌 **Connectors Used**  
- 🛡️ **Microsoft Sentinel** – To retrieve and update incidents.  
- 🦠 **VirusTotal** – For IP reputation checks.  
- 📊 **Azure Monitor** – For sign-in activity and log analysis.  
- 📧 **Office365** – For sending email notifications.  

---

## ✅ **Best Practices**  
- 🔑 Ensure that the VirusTotal API key is secure.  
- 📊 Monitor the app for failures using Azure Monitor.  
- 🔒 Use Managed Identity instead of hardcoded credentials for better security.  
- 🛡️ Ensure permissions for Microsoft Sentinel and VirusTotal are correctly assigned.  

---

✅ **Feel free to open an issue or submit a pull request if you encounter any problems!** 😎  

## 🚀 **Deploy to Azure**  
[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fnagasaikumarvarikuti.github.io%2FFirst_Access_Credentials%2Fazuredeploy.json)

