# Lab 2 – Configuring Examples of Security Control Types

_Domain: General Security Concepts_  
Date: 24/09/2025

---

## 🎯 Objective
- **Purpose of the lab:**  
	In this lab, you will learn about several types of security controls, including preventive, detective, directive, and corrective.

	As a security team member of Structureality Inc, you are working to improve your organization's security stance. This lab focuses on configuring, using or testing the security controls to ensure you understand the nature of the various types of controls. These exercises will facilitate your recommendations on the remediations to resolve security weaknesses. First, you will work with a preventive control, then a detective control. Next, you will work with a directive control and finally, a corrective control.
- **Security+ concepts:**
    - Security controls:
    - Preventative Controls
    - Detective controls
    - 

---

## 🛠️ Tools Used
- CompTIA VM Lab environment
- Windows PowerShell
- Microsoft Policy Analyzer
- Security Baseline Templates

---

## 📋 Steps
1.1 Configure and test preventative controls
A preventive control attempts to stop an unwanted activity from taking place. In this exercise, you will first perform an undesirable activity. Next, you will implement a preventive control to block that activity. And finally, you will attempt the unwanted activity again to test the preventive control.

 1.Open **Windows PowerShell as Administrator**.
- ![[Pasted image 20250905191919.png]]
 
2.Copy required files from D: to C:\LABFILES:
- copy D:\* C:\LABFILES
- This command copies _PolicyAnalyzer.zip_ and _Windows 10 Version 1809 and Windows  Server 2019 Security Baseline.zip_ from the read-only removable media virtual optical disc (i.e., D:) to C:\LABFILES.
3.Navigate to the directory and confirm contents:
- Enter cd c:\LABFILES to change into the directory.
- Enter ls to view the contents of the directory.
 ![[Pasted image 20250905184659.png]]4.Extract both zip files:
- Enter the following commands to extract the contents of the zip files into their own sub-directories:
- Expand-Archive -Path PolicyAnalyzer.zip
- Expand-Archive -Path "Windows 10 Version 1809 and Windows Server 2019 Security Baseline.zip"
5.Launch Policy Analyzer:
- C:\LABFILES\PolicyAnalyzer\PolicyAnalyzer_40\PolicyAnalyzer.exe
![[Pasted image 20250905185138.png]]
6.In **Policy Analyzer**, load the baseline policy rules from:
- On the _Pick the folder containing the Policy Analyzer Policy Rules files_ window, in left pane select **Local Disk (C:)**, in the right pane double-click **LABFILES**, double-click **Windows 10 Version 1809 and Windows Server 2019 Security Baseline**, double-click **Documentation**, then select **Select Folder**.
- The Policy Analyzer window should now show several policy rule sets.

![[Pasted image 20250905185523.png]]
![[Pasted image 20250905185610.png]]
7.Run **View/Compare** to review baseline values.

![[Pasted image 20250905185836.png]]
- Perform a View/Compare of MSFT-Win10-v1809-RS5-WS2019-FINAL using Policy Analyzer by marking the **MSFT-Win10-v1809-RS5-WS2019-FINAL** checkbox, then selecting **View / Compare**.

- The _Policy Viewer_ window will be displayed, showing the various policy settings contained in the MSFT-Win10-v1809-RS5-WS2019-FINAL policy rule set.

- This feature, View/Compare, shows the settings currently in the baseline security template file.
![[Pasted image 20250905190411.png]]
- in the screenshot below you can see the policy setting item of MinimumPasswordLength, has a baseline value of 14 on the security template. on the second window below it there is a description of the policy security settings, explaining the policy related to Minimum Password Length.
![[Pasted image 20250905191113.png]]
8.Run **Compare to Effective State** to identify configuration gaps between baseline and current system.
- Perform a **Compare to Effective State** of MSFT-Win10-v1809-RS5-WS2019-FINAL using Policy Analyzer by marking the **MSFT-Win10-v1809-RS5-WS2019-FINAL** checkbox, then selecting **Compare to Effective State**.

- This feature, _Compare to Effective State_, performs a gap analysis between the baseline security template file and the current in-use values of the local operating system.
![[Pasted image 20250905191919.png]]
- The _Policy Viewer_ window will be displayed, showing a comparison between the various policy settings contained in the MSFT-Win10-v1809-RS5-WS2019-FINAL policy rule set and the current operating system (labeled as "Effective state").
- Differences highlighted in **yellow** show mismatches between the baseline file and the current effective state of the live operating system environment of PC10.
- Since you are using a security template from a third party, it is essential to understand that while the template's settings may be based on general security best practices and recommendations, they are not tuned specifically to your organization's risk profile or business goals. You will need to tailor and scope security configuration templates to your organization's specific needs and requirements.
---

## ✅ Results
- Successfully launched Policy Analyzer.
- Performed **View/Compare** of baseline security template.
- Performed **Compare to Effective State**, identifying configuration differences.
- There are many items highlighted in yellow meaning these are where there are differences between the baseline file and the current effective state of the live operating system environment of PC10.

---

## 🧠 Key Takeaways
- You can verify if your systems are compliant by using the windows Policy Analyzer to do a gap analysis,
- The policy Analyzer allows you to identify security vulnerabilities within your current operating systems by comparing the effective state(current systems) to the required policy baseline.
- You have to know what to look for and you have to know the data to collect and analyze to do your gap analysis.
- In this lab we are analyzing our system configuration
- More than one policy baseline can be used to perform a gap analysis.


---

## 🔗 References
- CompTIA CertMaster Labs for Security+ (SY0-701)/Report Lab link
