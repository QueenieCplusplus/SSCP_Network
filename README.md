# SSCP Network


DoD Model

               --------------------------------------------------------------------  
               

               Application Layer
               
         (App Program: SNMP, DHCP, DNS, HTTP, LDAP, SMTP, FTP)
         
         
               -------------------------------------------------------------------- 
              
              
                Transport Layer 
                
        (End-to-End, TCP/UDP, Stream, Seq Packets, Datagram, Channel, AppleTalk)
                
               
               --------------------------------------------------------------------  
               
               
                 Network Layer  
                 
        (IP, ICMP, IGMP: Ping Scanning/Traceroute Exploitation, Packet Exchange, Data Delivery, Shortest Path Bridge, Carries Subnet Mask, Spec Next Hop Addr)
                
                
               --------------------------------------------------------------------  
               
               
                 Link  Layer
                 
                (MAC, subnet)
                 
                 
               -------------------------------------------------------------------- 
      
          
                  Physical Layer
                  (Digital Signal)


OSI Model in 1994


              --------------------------------------------------------------------   

              核心應用
              
              Application Layer
              
              --------------------------------------------------------------------          
              
              壓縮加密
              
              Presentation Layer 
              
              (Data to Apps: Data Conversion, Compression, Encrpto, code, services, Remote DB Access, RPC?, Remote Ops, Reliable Transfer, Distributed Transaction)
                        
              --------------------------------------------------------------------              
              
              驗證與通道建立(封包封裝)
              
              Session Layer 
              
              (Session between App, Session, Short Msg, Tunneling, Sockets, Auth)
                
              -------------------------------------------------------------------- 
              
              封包的序列
              
              Transport Layer
              
              -------------------------------------------------------------------- 
              
              封包的傳遞
              
              Network Layer 
              
              -------------------------------------------------------------------- 
                 
               Link  Layer (Vlan/ARP)
                 
              -------------------------------------------------------------------- 
              
               Physical Layer (Network Media)
               
              -------------------------------------------------------------------- 
              
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
  
  https://github.com/QueenieCplusplus/VM/blob/master/README.md#virtual-desktop
  
     Virtual Network Terminal Services:
     
     virtual network terminal service us a tool frequently used for remote access to server resources, it allows desktop env to exported to a remote workstation for a server. Vice versa, It allows users to execute desktop cmd at the remote workstation as though they were sitting at the server terminal interface.
     
     such service may provided by VNC. this is an alternative to the SSH/ Telnet.
     It is recommend to be used due to Auth to user and server. (Log & Audit)
     
     
  (6) Vendor Backdoors
  
    https://github.com/QueenieCplusplus/SSCP_System#attack-in-sys-level

  (7) Vulnerabilities in OS or Firmware
  
      (to be continued...)

# Layer 5, Session Layer, 會議層

SSL https://github.com/QueenieCplusplus/ITsec_TLS 

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

* SSL, tunneling in Layer 4

* TCP

* UDP

# Layer 3 (Logical)

see see https://github.com/QueenieCplusplus/QuickGoThru#網路拓樸技術

skip see ARP or ICMPv6 in https://github.com/QueenieCplusplus/QuickGoThru#ccda-cisco-certified-design-associate-網路架構師專業 

* TUN, tunneling in Layer 3

* ICMP

https://github.com/QueenieCplusplus/ICMP

* IGMP

* RADIUS, auth prototcol used in Layer 3 (single sign-on)
  
  it has some flaws such as:
  
  (1) can be attacked by Replay Attack.
  
  (2) has no Integrity Protection.
  
  (3) only transmit field using Encrpto.
  
* ND

https://github.com/QueenieCplusplus/ND (Neighbor Router Discovering by advertisement)
  
# Layer 2（Data Link/ Link State） 

skip see ARP or ICMPv6 in https://github.com/QueenieCplusplus/QuickGoThru#ccda-cisco-certified-design-associate-網路架構師專業 

https://github.com/QueenieCplusplus/CCNP_DataLink 

* TAP, tunneling in Layer 2

* Vlan 

a vlan is a set of workstations within a LAN that can communicate with each other as though they were on a single, isolated LAN:

(1) Broadcast packets sent by one of the workstations will reach all the others only in the LAN.

https://github.com/QueenieCplusplus/ARP (Broadcast)

(2) The workstations can all communicate with each other without requirement to go thru a GW. (it is ARP in this section for IP connection)

(3) GW in this process no funtion such as packet forward or packet drop.

(4) Without involvement of GW, so routing protocol is not needed.

* advantage of using Vlan

1. Performance: 

   without Router involved in, the data rate does not matter with performance.

2. Resource Partition: 

  with Vlan limitations, the access control is implemented.

3. Flexibility

   workers can move their physical place to anywhere, without bothering to be member of the Vlan.

4. Workgroup

There are 2 Types of Vlan.

* port-based Vlan criteria (criterion) p522

Ports of SW is assigned to Vlan, which is defined for Vlan membership, which is devices connected to a given port. 

Then the SW is automatically divided into sub-SW.

* protocol-based Vlan p524

      to be continued...

# Layer 1, Physical Layer, 物理層

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

Attacks in Layer 4,7 https://github.com/QueenieCplusplus/Network_Attacks

Attacks in Layer 2 https://github.com/QueenieCplusplus/CCNP_DataLink/blob/master/README.md#attack-in-layer-2

Tools https://github.com/QueenieCplusplus/Network_Tools


