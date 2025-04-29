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
- Create a Linux Virtual Machine.
- Install Wireshark. 
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
6. Click on the Windows virtual Machine, and find the Public IP Address. Go to Remote Desktop and enter in the IP address from the windows vm. (if you're on Mac, you need to download it from the app store). Enter in the username and password you put in for the virtual network when you created it. Log into the virtual network.
</p>
<p>

  ![image](https://github.com/user-attachments/assets/976515af-1834-4888-9cf9-cce5a5694e0f) ![image](https://github.com/user-attachments/assets/2c4bad6e-3e59-4349-93b5-20f9716ee524) ![image](https://github.com/user-attachments/assets/4fd5e486-6357-4f65-bc37-e7f9d507c887)



</p>
<br />




</p>
<br />

<p>
7. Within the Windows vm, install wireshark (https://www.wireshark.org). Click download , then choose the "Windows x64 Installer". When its finished downloading, click "Open File" at the top right of the screen. Select yes and ok to all of the options. *IMPORTANT* Be sure to enable the check box for Npcap. When finished, Open Wireshark so we can observe traffic between the VM's.
</p>
<p>

  ![image](https://github.com/user-attachments/assets/5ace5a66-9c8a-4e8e-8dfa-cc62f1f904f2) ![image](https://github.com/user-attachments/assets/001f5713-c767-412b-bd6e-89f9ca2d278a) ![image](https://github.com/user-attachments/assets/a4d9bd3e-4203-44d3-9dcb-c6ebc2eefe43)



</p>
<br />




</p>
<br />

<p>
8. After opening wireshark, you should see the screen below. Click on "Ethernet" to highlight it, then click on the shark fin at the top left corner to observe the Ethernet traffic. You should see a screen that looks like the second picture below. There should be constant movement on the screen. Those are all the packets that are going to and from the virtual machine. 
</p>
<p>

![image](https://github.com/user-attachments/assets/f6c77d36-d1e6-4ff1-9aad-9fde9948b98c) ![image](https://github.com/user-attachments/assets/26e1681c-386d-448b-84f4-1c0dc9c02bbc)





</p>
<br />




</p>
<br />

<p>
9. In the search bar at the top of the screen, type in "IMCP". Then, go back to azure on your personal desktop and get the Private IP address for the Ubuntu Server and attempt to ping it using powershell. To get to powershell, Click the start button on the VM and type in "Powershell". 
</p>
<p>

 ![image](https://github.com/user-attachments/assets/eb4c9ba2-2d3e-4571-bc57-01a677f6bea5) ![image](https://github.com/user-attachments/assets/9cda524e-ee72-49c6-8235-d76d9ff7b305) ![image](https://github.com/user-attachments/assets/12de8e62-1999-49d9-94a4-a7aa2a34ca00)






</p>
<br />



</p>
<br />

<p>
10. From within powershell, type in "ping (Ubuntu Private IP address). You should see this happen in Powershell. In Wireshark, you should be able to see the IMCP traffic. In wireshark, Click the green fin in the top left corner , then click "continue without saving" to clear the traffic on screen. 
</p>
<p>

![Screenshot 2025-04-29 091027](https://github.com/user-attachments/assets/c088a36e-70bd-4d98-ac07-154a25f02290) ![image](https://github.com/user-attachments/assets/6a5b499b-bdb2-42dd-b2e0-2071ccf6189a) ![image](https://github.com/user-attachments/assets/fd99aadc-f24c-4733-8e89-954367ab34d4) ![image](https://github.com/user-attachments/assets/1c71733c-5a01-473a-b221-0ce6655d71e9)










</p>
<br />



</p>
<br />

<p>
11. In the search bar, type in "ssh" to observe the ssh traffic. In Powershell, type in "ssh labuser@(privateIPadress), and press enter. You should see the traffic in Wireshark. Powershell is going to ask you if you want to continue connecting; type yes. When it asks for the password, type in the password for the Ubuntu Server you made. It will appear invisible on-screen, so be sure you're spelling it correctly. if everything is done right, you should be connected to the Ubuntu Server. When you're finished observing the traffic, 
 Go into Powershell and type "exit". In wireshark, clear the traffic on screen.
</p>
<p>

 ![image](https://github.com/user-attachments/assets/6b03416b-2f69-43b1-9bda-03d69e128fae) ![image](https://github.com/user-attachments/assets/d7a8c198-e8c4-4da6-9efa-4c1aaa41ced1) ![image](https://github.com/user-attachments/assets/36b9fb76-1782-4283-ac66-4e41a4d3f763) ![image](https://github.com/user-attachments/assets/1dc5779c-a8a4-4951-93d9-46bf33544d76)










</p>
<br />




</p>
<br />

<p>
12. In Wireshark, filter the traffic to either "dhcp" or "udp.port==67||udp.port==68". Then, go into the notes in the VM, and type "ipconfig /release" then "ipconfig /renew" below it, as shown in the second picture. Save that under Programdata in the Windows c: drive as "dhcp.bat"   
</p>
<p>

![image](https://github.com/user-attachments/assets/6890b2c5-d157-4e87-bdde-9f4293743a47) ![image](https://github.com/user-attachments/assets/3a54e4d4-2ef4-4ce1-bde5-89cc8c2dd4fb) ![image](https://github.com/user-attachments/assets/52758ee6-7b8f-44ef-9c22-d4a998f93f33)








</p>
<br />




</p>
<br />




</p>
<br />

<p>
13. In Powershell, type "cd c:\programdata". You should see the screen below. After that, Type in ".\dhcp.bat". When you do that, your connection to the virtual machine should stop and restart automatically. When it comes back up, you should see the traffic in Wireshark as shown below. When you're finished observing the traffic, clear it from Wireshark.
</p>
<p>

![image](https://github.com/user-attachments/assets/6b9bf0e8-8fe3-452c-b3d3-0094a46a639e) ![image](https://github.com/user-attachments/assets/df503e12-435b-4ae3-b78e-9c1b16c8e37b) ![image](https://github.com/user-attachments/assets/4694b578-bfd4-448b-bf3a-ff2b48704cc8)


 





</p>
<br />




</p>
<br />




</p>
<br />

<p>
14. Type "dns" into the search bar to filter for dns traffic. You should see the screen below. Clear that traffic, and go into Powershell. Type in "nslookup disney.com" (we use disney as an example). When you do that, you should see this screen in Powershell, and you should see the traffic in Wireshark as shown below. When youre finished observing the dns traffic, you can go ahead and close out the virtual machine, and delete everything you made in azure.   
</p>
<p>

![image](https://github.com/user-attachments/assets/48c2dd4e-6998-462e-92ac-6439f0c61620) ![Screenshot 2025-04-29 105430](https://github.com/user-attachments/assets/f3af8f4b-e5ae-489a-a86b-ac11ed8a9714) ![Screenshot 2025-04-29 105449](https://github.com/user-attachments/assets/b0060892-a538-4990-a501-03b498c1cacc)

