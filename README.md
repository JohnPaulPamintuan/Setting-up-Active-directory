<h1>Setting up Active Directory on Windows Server </h1> 

<h2>Project Description:</h2>
In this project, we will download and install VMWare workstation pro, Windows Server ISO 2022 and Install Active Directory tool on Window Server 2022 using Virtual Machine and creating a local domain name.  <br/>

<h2>Link Used:</h2>

- [<b>VMware Workstation Pro download</b>](https://knowledge.broadcom.com/external/article?articleNumber=368667)

- [<b>Windows Server 2022 ISO download</b>](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022)


<h1>Step-by-Step Implementation Guide for Setting Up Windows Server 2022 with Active Directory</h1>

<h2><ins>1. Downloading VMware Workstation Pro and Preparing the Windows Server 2022 ISO</ins></h2>

- To initiate the setup, first, download VMware Workstation Pro. Navigate to the VMware website, select "Personal use," and ensure you choose the version compatible with your operating system (Windows). Opt for the latest version available. While VMware is installing, go ahead and download the Windows Server 2022 ISO from the official Microsoft website or another reliable source and save it to your local machine. 

  <img src="https://i.imgur.com/sQNv98X.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <img src="https://imgur.com/mKHNXaz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  
<h2><ins>2. Creating a new virtual machine and Installing Windows Server 2022 on the virtual machine</ins></h2>

- Once you have completed the installation of VMware Workstation Pro (version 17 for personal use), open the application and select the option to create a new virtual machine. Select the “Typical” configuration for ease. During the virtual machine setup, choose Windows Server 2022 as the operating system you wish to install. Proceed through the steps, assigning appropriate resources such as memory and CPU based on your physical machine capabilities.

   <img src="https://imgur.com/egiEHTX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://imgur.com/zwgmYSe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  
<h2><ins>3. Configuring the virtual machine settings and Installing the Active Directory tool on the virtual machine</ins></h2>

- After creating your virtual machine, you will see its specifications listed. Right-click on the virtual machine directory and select "Settings." Here, navigate to the CD/DVD (SATA) option to attach the Windows Server 2022 ISO. Click on "Browse," locate the ISO file you previously downloaded, and select it. Next, power on the virtual machine. When prompted, press any key quickly to boot from the ISO, which will load the Windows Server installation setup.
- In the installation setup, choose "Desktop Experience" and select "Custom: Install Microsoft Server operating system (advanced)." Follow the prompts to continue with the installation, setting a memorable password for the administrator account. After the installation is complete, log in using your administrator credentials.
- Now, let's install the Active Directory tools on your server. The Server Manager will automatically pop up upon login. From the Server Manager interface, navigate to "Manage," then select "Add Roles and Features." Under the Server Roles section, find and choose "Active Directory Domain Services." If there are other tools or foundational services you might need, select those as well. Proceed through the installation prompts until completion.
  
   <img src="https://i.imgur.com/oQC4Kom.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://i.imgur.com/W6PVPXT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://i.imgur.com/E11MNJk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://i.imgur.com/PfhX4nv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://i.imgur.com/KMZDgTs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://i.imgur.com/iGuKjqU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://i.imgur.com/PfhX4nv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://i.imgur.com/PwOkLSb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <img src="https://i.imgur.com/meNVvyj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

   

<h2><ins>4. Conclusion and recap</ins></h2>

- Upon successful installation of Active Directory Domain Services, you will see an option labeled "Promote this server to a domain controller." This step is crucial as we are setting up a domain controller. In the "Deployment Configuration," select “Add a new forest” and input your desired domain name, remembering to append “.local” for best practices in domain naming. For the "Domain controller Options," select the most recent version of the server.
- Set a password for your domain, and continue to click "Next" until the installation process prompts a reboot. The server will restart to finalize the Active Directory installation.
- After rebooting, log back in using your domain admin credentials and verify that your Active Directory has been set up correctly. You can find the Active Directory tools typically under Windows Administrative Tools.
- Now you have successfully set up a Windows Server 2022 virtual machine with Active Directory services, equipped for managing domains and user authentication!
 
- Example filter to capture this sequence:

<img src="https://i.imgur.com/9qz7fvz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/0N7lmsQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/xGby7vI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/RJfamJK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ZiZnE1T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/tf9OrUS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
