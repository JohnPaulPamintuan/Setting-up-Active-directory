<h1>Setting up Active Directoy on Windows Server using Virtual Machine </h1> 

<h2>Project Description:</h2>
In this project, we will download and install VMWare workstation pro on Windows Server 2022 and Install Active Directory tool on Window Server 2022 <br/>

<h2>Link Used:</h2>

- [<b>VMware Workstation Pro download</b>](https://knowledge.broadcom.com/external/article?articleNumber=368667)

- [<b>Windows Server 2022 ISO download</b>](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022)


<h1>Step-by-Step Implementation Guide for Setting Up Windows Server 2022 with Active Directory</h1>

<h2><ins>1. Downloading VMware Workstation Pro and Preparing the Windows Server 2022 ISO</ins></h2>

-To initiate the setup, first, download VMware Workstation Pro. Navigate to the VMware website, select "Personal use," and ensure you choose the version compatible with your operating system (Windows). Opt for the latest version available. While VMware is installing, go ahead and download the Windows Server 2022 ISO from the official Microsoft website or another reliable source and save it to your local machine. 

  <img src="https://i.imgur.com/Q99f0YI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h2><ins>2. Creating a new virtual machine and Installing Windows Server 2022 on the virtual machine</ins></h2>

- Once you have completed the installation of VMware Workstation Pro (version 17 for personal use), open the application and select the option to create a new virtual machine. Select the “Typical” configuration for ease. During the virtual machine setup, choose Windows Server 2022 as the operating system you wish to install. Proceed through the steps, assigning appropriate resources such as memory and CPU based on your physical machine capabilities.

   <img src="https://i.imgur.com/n4wsxXD.png" height="120%" width="85%" alt="Disk Sanitization Steps"/>

- Example command to capture all TCP traffic and save it to a file:
   <img src="https://i.imgur.com/1dxjZDH.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>

- <b>Other examples of Tcpdump Packet Filtering:</b>

	- <ins><b>*host*</b></ins> will filter visible traffic to show anything involving the designated host.

       <img src="https://i.imgur.com/oJHHKxN.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>


  - <ins><b>*src and dest*</b></ins> are modifiers. We can use them to designate a source or destination host or port and <ins><b>*Utilizing Source With Port as a Filter.*</b></ins>

     <img src="https://i.imgur.com/RNkMYk3.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>
     <img src="https://i.imgur.com/Q4cBh2I.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>

   -  <ins><b>*proto*</b></ins> will filter for a specific protocol type. (ether, TCP, UDP, and ICMP as examples).
   -  <ins><b>*port*</b></ins> is bi-directional. It will show any traffic with the specified port as the source or destination.

       <img src="https://i.imgur.com/BnS36fc.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>
       <img src="https://i.imgur.com/thajDeo.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>
       <img src="https://i.imgur.com/7jrsoKr.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>
       
       

   - <ins><b>*less and greater*</b></ins> can be used to look for a packet or protocol option of a specific size.

     <img src="https://i.imgur.com/IKaTf8g.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>
     <img src="https://i.imgur.com/HYcVD9Y.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>
     
     

   - <ins><b>*and &&*</b></ins> can be used to concatenate two different filters together. for example, src host AND port.
   - <ins><b>*or*</b></ins> allows for a match on either of two conditions. It does not have to meet both. It can be tricky.
   - <ins><b>*not*</b></ins> is a modifier saying anything but x. For example, not UDP.

     <img src="https://i.imgur.com/JcgsKpC.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>
     <img src="https://i.imgur.com/m6fMmrg.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>
     <img src="https://i.imgur.com/WBrtF35.png" height="130%" width="80%" alt="Disk Sanitization Steps"/>

  
<h2><ins>3. Configuring the virtual machine settings and Installing the Active Directory tool on the virtual machine</ins></h2>

- After creating your virtual machine, you will see its specifications listed. Right-click on the virtual machine directory and select "Settings." Here, navigate to the CD/DVD (SATA) option to attach the Windows Server 2022 ISO. Click on "Browse," locate the ISO file you previously downloaded, and select it. Next, power on the virtual machine. When prompted, press any key quickly to boot from the ISO, which will load the Windows Server installation setup.
- In the installation setup, choose "Desktop Experience" and select "Custom: Install Microsoft Server operating system (advanced)." Follow the prompts to continue with the installation, setting a memorable password for the administrator account. After the installation is complete, log in using your administrator credentials.
- Now, let's install the Active Directory tools on your server. The Server Manager will automatically pop up upon login. From the Server Manager interface, navigate to "Manage," then select "Add Roles and Features." Under the Server Roles section, find and choose "Active Directory Domain Services." If there are other tools or foundational services you might need, select those as well. Proceed through the installation prompts until completion.
  
   <img src="https://i.imgur.com/D5P15oy.png" height="120%" width="85%" alt="Disk Sanitization Steps"/>
- To filter for TCP packets with the SYN flag set (indicating new connection attempts):
   <img src="https://i.imgur.com/ixoWbwR.png" height="120%" width="85%" alt="Disk Sanitization Steps"/>
- To see all packets with the FIN flag (indicating connection terminations):
   <img src="https://i.imgur.com/yfg94fA.png" height="120%" width="85%" alt="Disk Sanitization Steps"/>

<h2><ins>4. Conclusion and recap</ins></h2>

- Upon successful installation of Active Directory Domain Services, you will see an option labeled "Promote this server to a domain controller." This step is crucial as we are setting up a domain controller. In the "Deployment Configuration," select “Add a new forest” and input your desired domain name, remembering to append “.local” for best practices in domain naming. For the "Domain controller Options," select the most recent version of the server.
- Set a password for your domain, and continue to click "Next" until the installation process prompts a reboot. The server will restart to finalize the Active Directory installation.
- After rebooting, log back in using your domain admin credentials and verify that your Active Directory has been set up correctly. You can find the Active Directory tools typically under Windows Administrative Tools.
- Now you have successfully set up a Windows Server 2022 virtual machine with Active Directory services, equipped for managing domains and user authentication!
 
- Example filter to capture this sequence:

 <img src="https://i.imgur.com/jhwYuR9.png" height="120%" width="85%" alt="Disk Sanitization Steps"/>
