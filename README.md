# Create Inspect and Delete DNS A Records and CNAME
<p align="center">
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/301bea07-f6b9-4d70-86c2-e8149ccf1317"/>
</p>

<h1>Create Inspect and Delete DNS A Records and CNAME</h1>
In this tutorial, going off On-premises Active Directory Deployed in the Cloud (Azure) [https://github.com/Jacobvillagomez1/Configuring-On-premises-Active-Directory-within-Azure-VMs] we will Create Inspect and Delete DNS A Records and CNAME in DC-1 VM . <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Active Directory Domain Services
- Server Manager
- DNS Manager
- Command Prompt (Admin)


<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>High-Level Steps</h2>

- Log into Cilent-1 and DC-1 VM from [https://github.com/Jacobvillagomez1/Configuring-On-premises-Active-Directory-within-Azure-VMs]
- Go to DC-1 VM/ DNS Manager/ Forward Lookup Zones / Create A Record
- Open Cilent-1 VM ping A Record from DC-1
- Flush DNS and Display DNS on Cilent-1
- Open DC-1 VM and change the name of the A Record
- Open Cilent-1 VM Ping the new name of A Record
- Go back to DC-1 VM and create a CNAME
- Open Cilent-1 VM and Ping CNAME
- Go back to DC-1 VM and see Root Hints File


<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/ab091d4c-4b4b-4034-9488-9f27b0d25530"/>
</p>
<p>
First we need to log back into Cilent-1 and DC-1 from [https://github.com/Jacobvillagomez1/Configuring-On-premises-Active-Directory-within-Azure-VMs] using Remote Desktop Connection. Copy the Public IP and log into the VM indivudally.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/bec682f8-0a86-44ff-bfdb-a083311cb3ee"/>
</p>
<p>
Next open Cilent-1 VM and search for Command Prompt in the search bar.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/d1a70743-8702-48d7-9a00-b46170cc8f56"/>
</p>
<p>
Once CMD loads you will see you are under jane_admin.
</p>
<br />


<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/2dd0e5ea-5405-432b-be96-7efd8a6efeae"/>
</p>
<p>
Then Open DC-1 VM and click Tools on the top right side of Server Manager. Then select DNS.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/9de400d1-86fe-406e-99c0-0b2d98e49862"/>
</p>
<p>
Next click the DC-1 File.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/255b41c0-10d4-4b3a-9c39-5b580aec51ce"/>
</p>
<p>
Then click Forward Lookup Zones.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/38e34221-4a9b-431f-95f1-d61ab2d9f8a8"/>
</p>
<p>
Next double click mydomain.com folder
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/76996c4c-101c-4a68-bb45-5abc4de56b87"/>
</p>
<p>
We are now going to create a New Host A Record. To do this right click anywhere on the screen and click New Host (A or AAAA)...
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/db33009c-73c2-46b3-a7e1-55fbfce70897"/>
</p>
<p>
Now in the Name section we can type mainframe and for IP Address we can type the same IP as dc-1 IP which is 10.0.0.4. Once those are both typed in click add host.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/e75975e3-8c5e-40fd-a8e6-355318e4e679"/>
</p>
<p>
Once you added the host click ok.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/c99db801-f0d9-4bd8-bbd7-d39e4a15a9e6"/>
</p>
<p>
Then click done to finish the process.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/7de23ad6-8b92-47d6-a96e-b0961f671f8d"/>
</p>
<p>
Next go back to Cilent-1 VM and ping the A Record we created. Type ping mainframe in the command line 4 packets will be sent and received from DC-1 to Cilent-1.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/1e42a3c0-a861-4fde-b3eb-baa40498dc7b"/>
</p>
<p>
We can also lookup the IP Address by typing nslookup mainframe in the command line.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/4ae1faa6-23ea-4787-b41c-e24c351f0090"/>
</p>
<p>
Next type ipconfig /displaydns in the command line this will display all the websites search on this VM.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/2be367dd-e966-4379-80cf-83c9f7277479"/>
</p>
<p>
Then we can clear the DNS cache by typing ipconfig /flushdns in the command line.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/f955be08-2001-4dfa-b1af-2b6cc15e26c0"/>
</p>
<p>
The command line wont let use run this command, close CMD. Then when you re open Command Prompt right click and run as administrator.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/b7914a8c-dab9-4d5c-aefc-a069d9729bc9"/>
</p>
<p>
Click yes to allow Windows Command Processor to run.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/44b88858-44e3-4cbb-8e69-c02e7986c340"/>
</p>
<p>
Go back to DC-1 VM and double click mainframe and this time change the IP Address to 8.8.8.8 and click ok on the bottom left.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/9ece137c-ab90-4392-9a1a-577027e18636"/>
</p>
<p>
Now we can see that mainframe IP Address changed to 8.8.8.8
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/ddeb8e21-60b1-4464-aa2f-2fa8d215eef9"/>
</p>
<p>
Go back to Cilent-1 VM and type ping mainframe and it will still ping the IP Address even though we changed it.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/37282a6a-ff40-4d9c-a56d-7c10220d0ab0"/>
</p>
<p>
We can type ipconfig /displaydns to see what we pinged.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/5a7b8921-4169-4e36-a9f3-bddd550b4187"/>
</p>
<p>
Next type ipconfig /flushdns in the commandline to flush the DNS Resolver Cache.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/c4192677-e145-42bb-8b56-ab89fa87cae8"/>
</p>
<p>
Now type ping search in the command line you wil see the ping request could not find host search. Which means its not created yet.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/d445c469-4595-4ed6-bcb8-90fdeeb88d07"/>
</p>
<p>
Go back to DC-1 VM and right click anywhere, then click New Alias (CNAME).
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/a2e0b23a-8955-4d73-9183-9aa957b1d874"/>
</p>
<p>
Now in the Alias name section type search, and under fully qualified domain name type www.google.com then you can press ok.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/44ae25e4-689e-4459-9ff1-7ba452c6217b"/>
</p>
<p>
Now we can see that search was created.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/f1535394-f00b-4ca6-96e9-d7b48e8df671"/>
</p>
<p>
Go back to Cilent-1 VM and type ping search in the command line. 4 packets will be send and received from www.google.com
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/4e8cdac0-f884-4dbc-940c-bec590ef4b6c"/>
</p>
<p>
Next type ipconfig /displaydns and we will see the ping that we just did.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/cfb1ac69-53fd-4a34-8923-1332e3fb7a94"/>
</p>
<p>
Now type ipconfig /flushdns this will flush the DNS cache again.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/f0179b68-b242-44ea-ac46-7193774ccd12"/>
</p>
<p>
Go back to DC-1 VM and right click DC and go to properties.
</p>
<br />

<p>
<img src="https://github.com/Jacobvillagomez1/Create-Inspect-and-Delete-DNS-A-Records-and-CNAME/assets/143027686/f0179b68-b242-44ea-ac46-7193774ccd12"/>
</p>
<p>
Click on the Root Hints tab and you will see all the Root Hints in DC-1
</p>
<br />
