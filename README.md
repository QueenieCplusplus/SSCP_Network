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
              
# Layer 7

skipped
              
# Layer 6, Presentation Layer, 表現層

* Remote Access Services, 遠端連線

  (1) VPN, Virtual Private Network

  (2) TELNET, Terminal Emulation Protocol

  (3) rLogin, rsh, rcp

  (4) Screen Scraper

  (5) Virtual Desktop & Virtual Apps

  (6) Vendor Backdoors

 (7) Vulnerabilities in OS or Firmware

# Layer 5, Session Layer, 會議層

* Tunneling, 隧道

  using PPP in Layer5 is as same as PPP used in Layer 2.

* RPC, Remote Procedure Call, 遠程呼叫

  It allows executing obj accross hosts, with a client sending instruction to an app resided on different host in network, there are some services in this category, such as: Distributed Computing Env.

  Plz note that RPC doesn't provide any service on its own, it only provides basic auth and address the target service. So it can be considered as a Broker.

# Layer 4

skip see https://github.com/QueenieCplusplus/QuickGoThru#ccda-cisco-certified-design-associate-網路架構師專業

* TCP

* UDP

# Layer 3

see see https://github.com/QueenieCplusplus/QuickGoThru#網路拓樸技術

* ICMP

* IGMP

* RADIUS, auth prototcol used in Layer 3 (single sign-on)
  
  it has some flaws such as:
  
  (1) can be attacked by Replay Attack.
  
  (2) has no Integrity Protection.
  
  (3) only transmit field using Encrpto.
  
# Layer 2, Link Layer, 鏈結層

skip see ARP or ICMPv6 in https://github.com/QueenieCplusplus/QuickGoThru#ccda-cisco-certified-design-associate-網路架構師專業 


# Layer 1, Phisical Layer, 物理層

* Endpoint (Host) Security

  (1) user may use limited access accounts in accordance with concept of "Least Previlege".

  (2) update anti-virus aand anti-malware software.
  
  (3) host-based firewall.
  
  (4) cnfg with unneeded services disabled
  
  (5) maitain ops
  
* Analog Communication

* Digital Communication

