# SSCP_Network

DoD Model

              Application Layer (App Program: SNMP, DHCP, DNS, HTTP, LDAP, SMTP, FTP)
              -----------------
               Transport Layer (End-to-End, TCP/UDP, Stream, Seq Packets, Datagram, Channel, AppleTalk)
              -----------------
                Network Layer  (IP, ICMP, IGMP: Ping Scanning/Traceroute Exploitation, Packet Exchange, Data Delivery, Shortest Path Bridge, Carries Subnet Mask, Spec Next Hop Addr)
              -----------------
                 Link  Layer   (MAC, subnet)

OSI Model in 1994

              Application Layer
              -----------------
              
              
              Presentation Layer (Data to Apps: Data Conversion, Compression, Encrpto, code, services, Remote DB Access, RPC?, Remote Ops, Reliable Transfer, Distributed Transaction)
              
              
              -----------------
              
              
                Session Layer (Session between App, Session, Short Msg, Tunneling, Sockets, Auth)
                
              
              -----------------
               Transport Layer
              -----------------
                Network Layer
              -----------------
                 Link  Layer
              -----------------
              
              
               Physical Layer (Network Media)
               
               
              -----------------
              
# Layer 7 (APP)

* SNMP, Simple Network Mgmt Protocol

https://github.com/QueenieCplusplus/SNMP

   it involves a server (called as Manager) and a client which is a software install in network devices such as router/sw called agent.

   it allows manger to get values of variables which is set from agent. The varaibles includes Routing Table and performance info.

   even SNMP is upgraded to version 2, its vulnerability still remains, which is that its password is easy to be sniffed (transmission in plaintext) in the commands process then being faked one by Middleman, when server identifies itself against an agent (community string is sent to agent) and password is sent in commend. 

# Layer 6, Presentation Layer, 表現層

* Remote Access Services, 遠端連線

  (1) VPN, Virtual Private Network
  
     a vpn is a tunnel within encrpto between 2 hosts allowing them to do secret connection in untrusted internet. There are 2 way to do this implementation:
     
     1. point-to-point connection
     
     2. gw-to-gw connection between sites or business partener
     
        in this way, the GRE, generic routing encapsultation is implemented over tunnel between endpoint(GWs).
        
        However there are still a risk remained, which is auth way that the encrpt key is derived from users password, it is easier to be attacked. So it is better to use TFA, two factors authentication instead of password-based VPN.
       

  (2) TELNET, Terminal Emulation Protocol
  
     it is without protection from encrpto, so it is recommend used with rLogin via SSH. see below! 
     
     Telnet is a command line protocol to give cmd access to another host, this is present in many UNIX OS, which combines with NFS and NIS. 
     
     Actually a Telnet server is a equipment for any UNIX server.
     

  (3) rLogin, rsh, rcp
  
     rlogin usually performed in Unix Server, it is a protocol used for granting remote access to a machine.
     
     rsh, remote ssh grant direct remote cmd execution within copies data of rcp to and fro the remote machine. 
     
     if a rlogin daemon (called as rlogind) is running on a machine, rlogin access can be granted in 2 mechanisms, rlogin transmits data is without encryption and may easily being eavesdropped & intercepted :
     
     1. use of central config file (By Sys Admin)
     
     2. user config
     
   as mentioned above, the access mechanism applies to both of the rsh and rcp too:
     
     1. use of central config file (By Sys Admin)
     
     2. user config
    
   Auth can be considered to host/IP-based addr. Not the IDs actually! However, once the ID a remote client claims to possess is taken for granted due to a trust host that the request sending from.
   
   SSH is benefitial to its own drawback: remote access without password. It shall only be used in trusted network.
   
   
  (4) Screen Scraper
  
     a screen scraper is a program that can extract data on a display, this tech can be used in a nefarious way, such as image capture from users computer.


  (5) Virtual Desktop & Virtual Apps
  
     Virtual Network Terminal Services:
     
     virtual network terminal service us a tool frequently used for remote access to server resources, it allows desktop env to exported to a remote workstation for a server. Vice versa, It allows users to execute desktop cmd at the remote workstation as though they were sitting at the server terminal interface.
     
     such service may provided by VNC. this is an alternative to the SSH/ Telnet.
     It is recommend to be used due to Auth to user and server. (Log & Audit)
     
     
  (6) Vendor Backdoors
  
      (to be continued...)

  (7) Vulnerabilities in OS or Firmware
  
      (to be continued...)

# Layer 5, Session Layer, 會議層

* Tunneling, 隧道

  using PPP in Layer 5 is as same as PPP used in Layer 3.
  https://github.com/QueenieCplusplus/PPP
  
  *** PPP, P2P protocol
  
  P2P apps are often designed to open a (uncontrolled) channel thru internet. However it indeed exist some vulnerabilty inside this P2P way due to its overlapped master & slave nodes:
  
  if one node are detected and shut down, the Bot still can make one of the slave nodes as master and use the redundant staging point to do unimpeded Bot ops.
  
  (1) Botnet 
  
  (2) Spyware app
  
  (3) Virus got entrypoint

* RPC, Remote Procedure Call, 遠程呼叫

  It allows executing obj accross hosts, with a client sending instruction to an app resided on different host in network, there are some services in this category, such as: Distributed Computing Env.

  Plz note that RPC doesn't provide any service on its own, it only provides basic auth and address the target service. So it can be considered as a Broker.

# Layer 4 (Transmission)

* TCP

* UDP

# Layer 3 (Logical)

see see https://github.com/QueenieCplusplus/QuickGoThru#網路拓樸技術

skip see ARP or ICMPv6 in https://github.com/QueenieCplusplus/QuickGoThru#ccda-cisco-certified-design-associate-網路架構師專業 

* ICMP

* IGMP

* RADIUS, auth prototcol used in Layer 3 (single sign-on)
  
  it has some flaws such as:
  
  (1) can be attacked by Replay Attack.
  
  (2) has no Integrity Protection.
  
  (3) only transmit field using Encrpto.
  
# Layer 2（Link） 

skip see ARP or ICMPv6 in https://github.com/QueenieCplusplus/QuickGoThru#ccda-cisco-certified-design-associate-網路架構師專業 

* Vlan 


# Layer 1, Phisical Layer, 物理層

* Endpoint (Host) Security

  (1) user may use limited access accounts in accordance with concept of "Least Previlege".

  (2) update anti-virus aand anti-malware software.
  
  (3) host-based firewall.
  
  (4) cnfg with unneeded services disabled
  
  (5) maitain ops
  
Below 2 data communication shows analog is worse than digital when going to promise the data integrity.
  
* Analog Communication using Waveforms thru twisted pair or wireless

  Analog signals use electronic properties (frequency:High pitch/Low pitch & amplitude:Greater Louder/Lesser) to present information, for instance:
  
   Human Speaks ---> Voices ---> Acoustical Energy ----> Electrical Equivalent

* Digital Communication using Electronic States tru cable, Optical fiber or wireless

  Digital signals use electronic properties (on/off) to present information, the convention is as below:
  
  1 is assigned to on state ; 0 is assigned to off state.
  
  010010000000100001000000001111110101000000000101 (a series of the two states of electronics)
  
# Attack in Network 

1. p.533 --- SNMP
2. p.539 --- Eavesdropping using tool: Network tap or span
3. p.541 --- Spam
4. p.542 --- Filtering (by addr/ by service)
5. p.543 --- Packet Filter (Static Packet/Stateful or Dynamic Packet)
6. p.544 --- Proxy (Web level/App level/Circut level)
7. p.545 --- Scanning (Port/FIN/TCP seq) using tool: Nessus/Nmap
8. p.550 --- Tool
9. p.551 --- Attack FW by Overlapping Fragment
10. p526 --- Data-Link Attack --- MAC Flood --- p529 --- MACsec
11. p527 --- Data-Link Attack --- Inter-SW Level Attack
12. p527 --- Data-Link Attack --- 802.1Q Vlan Atack
13. p528 --- Data-Link Attack --- ARP attack
14. p529 --- Data-Link Attack --- Spanning-Tree Attack
15. p529 --- Data-Link Attack --- Multicast Brute Force Attack
16. p529 --- Data-Link Attack --- Random Frame Stress Attack
