<h1>Active Directory Lab</h1>

<h2>Description</h2>
In this lab, I created a Active Directory environment using VirtualBox. I configured a Windows 2019 Server with active directory, network configurations, and setup users. The goal of this lab is to replicate a how a business would setup a network and be able to centrally manage users from a domain controller. 
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Active Directory</b>
- <b>Oracle VirtualBox</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> 
- <b>Windows Server 2019</b>

<h2>Program walk-through:</h2>

<p align="center">
Created a VM with Windows Server 2019 installed <br/>
<img src="https://i.imgur.com/g6i2kHf.png" height="80%" width="80%" alt="AD Lab Steps"/>
<br />

<br />
Added two NICs on the server virtual machine. One is for connection to the ISP and one is going to be used within the internal network. Assigned a static IP to the internal NIC which will be a default gateway for the network. <br/>
<img src="https://i.imgur.com/IuTkhQU.png" height="80%" width="80%" alt="AD Lab Steps"/>
<br />

<br />
Installed active directory, remote access server, and NAT server. This will allow clients to be within private network but still give access to the internet with our domain controller. Created a admin user and logged in using that account.<br/>
<img src="https://i.imgur.com/5QdTJ64.png" height="80%" width="80%" alt="AD Lab Steps"/>
<br />

<br />
Install DHCP server on domain controller for our internal clients to be able to receive an IP address. Created and set the range for the scope on our DHCP server to be 172.16.0.100-200, these will be the IP ranges that will be assigned to clients that connect to the domain.<br/>
<img src="https://i.imgur.com/9w2ZCm1.png" height="80%" width="80%" alt="AD Lab Steps"/>
<br />

<br />
Used a PowerShell script to create multiple users. Using a text file containing 1000 randomized names, we create users with usernames and passwords and predetermined settings. Here are the results from the script. <br/>
<img src="https://i.imgur.com/7ON4jbY.png" height="80%" width="80%" alt="AD Lab Steps"/>
<img src="https://i.imgur.com/U2XoxAz.png" height="80%" width="80%" alt="AD Lab Steps"/>
<br />

<br />
Using a virtual machine, I created a client and connected it to our windows server domain. The DHCP server assigned it an IP address of 172.16.0.100 since that is the first address in our scope. Now using that client, any user on the domain can use their credentials to sign in on that client.   <br/>
<img src="https://i.imgur.com/UnDEO1j.png" height="80%" width="80%" alt="AD Lab Steps"/>
<br />

<br />
Here is the new client shown within our domain controller after it has connected. <br/>
<img src="https://i.imgur.com/zTgWWmJ.png" height="80%" width="80%" alt="AD Lab Steps"/>
<br />
</p>
