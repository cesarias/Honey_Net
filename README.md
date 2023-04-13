<p align="center">
<img src="https://i.imgur.com/tMxbbpd.png" height="70%" width="70%" alt="Sentinel logo"/>
</p>

<h1> Azure Clould Detection Lab </h1>
This Lab demonstrates a highly vulnerable environment leaving many attack surfaces open for 24 hours. With the incoming traffic from all around the world we can study the data in Sentinel(SIEM) and practice Incident Response. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Microsoft Sentinel (SIEM)
- Microsoft Defender for Cloud
- Remote Desktop
- KQL
- Blob Storage
- Powershell
- Visual Studio Code
- Log Analytic Workspace
- Resource Logs
- Activity Logs
- Azure Active Directory Logs
- Key Vault


<h2>Operating Systems Used </h2>

- MAC OS / Windows 10(VM)</b> 


<h2> Lab Description </h2>

<p>
<img src="https://i.imgur.com/yc5LmJT.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 We create our resources (VMs, Azure AD, Blob Storage, Activity Log, Key Storage) within Azure. With our Resources we ingest data into our Log Analytic Workspace that serves as our central repository. Since we will be on the public internet and our environment is highly succeptible, our resources will be constantly attacked by hackers/bots.  For that reason we will create a SIEM (Azure Sentinel). With Sentinel we will draw data out of our Log Analytic Workspace. With that data we can conduct logging, monitoring, configure alerts and plot locations of malicious attackers around the world. 
</p>
<br />
                                                                                        
 <p>
<img src="https://i.imgur.com/VoAfD8s.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Created custom inbound rule in our Windows VM. Purposely weakinging our NSG. Allowing multiple ports to remain open, to make it attractive to attackers  world wide.   
</p>
<br />                                                                                       

<p>
<img src="https://i.imgur.com/gycQtZH.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 We create anoter Windows VM(attacker) that will act as one of our attackers where it can create alerts and incidents in our SIEM (Azure Sentinel).  
</p>
<br />
                                                                                        
 <p>
<img src="https://i.imgur.com/qtFNqyx.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Enable logging for SQL Server to report successful and failed attempts into Windows Event Viewer . 
</p>                                                                                                    
                                                                                        
                                                                                        
<p>
<img src="https://i.imgur.com/l8FFRO7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Begin to create one of the new alerts in Microsoft Sentinel. Name it decide the tactics and Tactics/techniques to scan for. 
<br />

<p>
<img src="https://i.imgur.com/HrYaubu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> 
  This query in the scheduled rule will alert Sentinel for EventID 4625. where failed log-in attempts are 10 or more.                                                                                               
                                                                                                 
</p>

<p>
<img src="https://i.imgur.com/ZtKRaSv.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 This code from our Attacker VM will simulate a Brute Force Attack where it loops 11 failed log-in attempts with one successful log-in at the end .</p>

<p>
<img src="https://i.imgur.com/cwJFYQf.png" width="80%" alt="Disk Sanitization Steps"/>

<p>
 This code from our Attacker VM will attempt to access the password for our Key Vault Resource we created in our Windows VM .
</p>

<p>
<img src="https://i.imgur.com/xLv63t6.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Created four custom workbooks in Microsoft Sentinel to track and plot the locations of the attacks globally .
</p>

<p>
<img src="https://i.imgur.com/EubDCBR.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To form the attack maps in this lab along with our workbooks in Sentinel, two large files containing Geo Data(longitude/latitude/IP addresses) were loaded into a container within a storage account. Blob SAS URLs (Shared Access Signatures) were then created for both files. The SAS URLs are ingested by our Log Repository. Creating and linking our Microsoft Sentinel resource to the Log Anaylytics workspace gives the SIEM access to all the geo data. Giving Sentinel access to this data allows watchlists/queries/workbooks and other instances to be created in the SIEM. 

</p>

<p>
<img src="https://i.imgur.com/52gvYnL.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Our two watchlists within Microsoft Sentinel.  
</p>

<p>
<img src="https://i.imgur.com/mmk42W2.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Attack Map displays Network Security Groups  Malicious Flows 
</p>

<p>
<img src="https://i.imgur.com/1h1ha5h.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Attack Map displays Syslog authoriaztion failures. 
</p>

<p>
<img src="https://i.imgur.com/kPtXmME.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Attack Map displays Windows Authentication Failures.
</p>                                         
                                                                                    
 <p>
<img src="https://i.imgur.com/8ZPM8Mj.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Begin to inspect one of the Alerts/Incidents in Microsoft Sentinel.
</p>                                                                                   
                                                                                
 <p>
<img src="https://i.imgur.com/vcR9qwr.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Looking further into the Brute Force Attempt, looking at the related incidents to this alert.  
</p> 

<p>
<img src="https://i.imgur.com/h64y7gL.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Here ticket was assigned, status was made active and after research we close out the incident in Sentinel as a False Positive. 
</p>                 
 
 
      
 Thank you for viewing. 
</p>
<br />
