<h1>Setting up Active Directoy on Windows Server using Virtual Machine </h1> 

<h2>Project Description:</h2>
In this project, we will download and install VMWare workstation pro on Windows Server 2022  on VM Install Active Directory tool on Window Server 2022 <br/>

<h2>Link Used:</h2>

- [<b>VMware Workstation Pro download</b>](https://knowledge.broadcom.com/external/article?articleNumber=368667)

- [<b>Windows Server 2022 ISO download</b>](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022)


<h1>Step-by-Step Implementation</h1>

<h2><ins>1. Setting Up the Environment</ins></h2>

- Install TCPdump on your machine (Linux-based or virtual machine).
- Ensure that you have administrative privileges to capture network traffic.

  <img src="https://i.imgur.com/Q99f0YI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h2><ins>2. Capturing TCP Traffic</ins></h2>

- Use TCPdump to capture only TCP traffic from a specified network interface (e.g., eth0). You can use filters to focus on traffic from a specific source or destination IP, or port.
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

  
<h2><ins>3. Basic Analysis with TCPdump</ins></h2>

- After capturing the traffic, use TCPdump to analyze specific packets directly from the terminal.
- View the contents of the <b>.pcap</b> file:
  
   <img src="https://i.imgur.com/D5P15oy.png" height="120%" width="85%" alt="Disk Sanitization Steps"/>
- To filter for TCP packets with the SYN flag set (indicating new connection attempts):
   <img src="https://i.imgur.com/ixoWbwR.png" height="120%" width="85%" alt="Disk Sanitization Steps"/>
- To see all packets with the FIN flag (indicating connection terminations):
   <img src="https://i.imgur.com/yfg94fA.png" height="120%" width="85%" alt="Disk Sanitization Steps"/>

<h2><ins>4. Inspecting TCP Three-Way Handshake</ins></h2>

- Identify the TCP three-way handshake in the captured data by filtering for packets with the SYN, SYN-ACK, and ACK flags.
- The three-step process looks like:
  - SYN from the client to initiate a connection.
  - SYN-ACK from the server to acknowledge the request.
  - ACK from the client to establish the connection.
 
- Example filter to capture this sequence:

 <img src="https://i.imgur.com/jhwYuR9.png" height="120%" width="85%" alt="Disk Sanitization Steps"/>
