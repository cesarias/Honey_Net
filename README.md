<p align="center">
<img src="https://i.imgur.com/tMxbbpd.png" height="70%" width="70%" alt="Sentinel logo"/>
</p>

<h1> Azure Clould Detection Lab </h1>
This Lab demonstrates setting up Analytic Rules to detect Security events in Sentinel..<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Microsoft Sentinel
- Microsoft Defender for Cloud
- Remote Desktop
- KQL


<h2>Operating Systems Used </h2>

- MAC OS / Windows 10(VM)</b> 


<h2> Lab Description </h2>

<p>
<img src="https://i.imgur.com/yc5LmJT.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Confgure and delpoyed Azure Resources.  
</p>
<br />

<p>
<img src="https://i.imgur.com/QlLpQOV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 To seucure our VM we set our incoming RDP traffic (port 3389) to only our IP address. 
</p>
<br />

<p>
<img src="https://i.imgur.com/YFZdAeO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 To further secure our VM and reduce our attack surface we enable the just-in-time feature which makes it accessible only through time-based restrictions.
 Also implementing the principle of least privilege. Which only gives user the rights to do their specific job at task. 
</p>

<p>
<img src="https://i.imgur.com/GJWAHNB.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Next we set our data connectors and create a data collection rule to collect data from our Windows VM.</p>

<p>
<img src="https://i.imgur.com/XePKkyN.png" width="80%" alt="Disk Sanitization Steps"/>

<p>
 Microsoft Overview showing we have zero incidents at the moment.
</p>

<p>
<img src="https://i.imgur.com/6HO36eV.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 In our Windows VM we go to event viewer to see our Security events.
</p>

<p>
<img src="https://i.imgur.com/VUtEvCo.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Back in Azure we go to Microsoft Sentinel Logs and run a quick KQL query verifying the security events in our Windows VM.
</p>

<p>
<img src="https://i.imgur.com/fgsxeE3.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 We run a different KQL query where we parse specific information from our logs. We will use this data to create a new scheduled Analytics Rule. 
</p>

<p>
<img src="https://i.imgur.com/MXkUknY.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 We create our rule query from our Sentinel Log we ran earlier and also set the set entities so Sentinel can give us the specific data we want for our       research into any incidents inciting our alert to trigger. The entities will help us paint picture better as to what exactly is going on. 
</p>

<p>
<img src="https://i.imgur.com/IWrc2oe.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Here we have our recently created rule active.
</p>                                         
                                                                                    
 <p>
<img src="https://i.imgur.com/MdBtJky.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 We create a scheduled task in our Windows VM to set off an alert in Sentinel.
</p>                                                                                   
                                                                                
 <p>
<img src="https://i.imgur.com/0IXKJSc.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 We can see that our scheduled task in our Windows VM alerted Sentinel and triggered an incident in our Overview. 
</p> 

<p>
<img src="https://i.imgur.com/0IXKJSc.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 We can see that our scheduled task in our Windows VM alerted Sentinel and triggered an incident in our Overview. 
</p>                 
 
 <p>
<img src="https://i.imgur.com/vFrY0HF.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Investigating our alert in Sentinel. 
</p>                                                                                   
                                                                                    
<p>
<img src="https://i.imgur.com/ji4rBps.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Here ticket was assigned, status was made active and after research we close out the incident in Sentinel as a False Positive.
 
 
 Thank you for viewing. 
</p>
<br />
