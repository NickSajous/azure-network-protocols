<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, DNS, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create a Windows 10 Virtual Machine.
- Observe IMCP traffic.
- Observe SSH traffic
- Observe DHCP traffic
- Observe DNS traffic

<h2>Actions and Observations</h2>

<p>.
1. Create a Resource Group. Name it "RG-Network-Activities". *IMPORTANT* Fot the "Region" drop down, always select the same region. Create the Resource Group.
</p>
<p>

  ![image](https://github.com/user-attachments/assets/104c2ae6-efd5-4808-8dbe-6e140f9bf26a)

</p>
<br />

<p>
2. Create a Virtual Machine (Windows). Under "Resource Group", select the resource group you made previously. Under the virtual machine name type "windows-vm". For the username, type "labuser". For the password, type "Cyberlab123!".  *IMPORTANT* Make sure you choose the right image for the virtual machine (Windows 10 Pro). 
<p>

  ![image](https://github.com/user-attachments/assets/2ce82f43-f414-41f0-8288-01507066ff12) ![image](https://github.com/user-attachments/assets/c69f4dbf-33c1-4e94-9212-a8e33a78784c)


</p>
<br />

<p>
3. Go to the "Networking" tab, click "Create New" and rename the virtual network to Lab2-Vnet. Create the Virtual Network.
</p>
<p>

  ![image](https://github.com/user-attachments/assets/5f6338fa-baa0-47dd-9567-2297d2eef1b2) ![image](https://github.com/user-attachments/assets/cc230921-e8ff-47b2-be94-708aba3d3775)


</p>
<br />




</p>
<br />

<p>
4.Create a second Virtual machine (Ubuntu). Under "Resource Group", select the resource group that you made (RG-Network-Activities). Select "Ubuntu Server" in the image drop down. Under the "Administrator account" section, change the option to password. For the username, type "labuser". For the password, type "Cyberlab123!".
</p>
<p>

  ![image](https://github.com/user-attachments/assets/3ce6931e-b2e3-4b17-8d7a-fde590c9805f) ![image](https://github.com/user-attachments/assets/5a39e879-96e7-419e-a701-61861755dd4a) ![image](https://github.com/user-attachments/assets/b8e2c7e9-bb3b-4931-9b53-eebbc7fe0193)



</p>
<br />




</p>
<br />

<p>
5.  Go to the "Networking" tab, and change the virtual network to the one you created previously (Lab2-Vnet). *IMPORTANT* Make sure that both of the virtual machines are in the same virtual network. It will not work otherwise. Create the virtual machine.
</p>
<p>

  ![image](https://github.com/user-attachments/assets/0f66d857-9e91-4399-aeee-c8cc29c066d8)

</p>
<br />




</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />




</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
