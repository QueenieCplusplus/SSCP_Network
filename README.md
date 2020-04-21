# SSCP_Network

DoD Model

              Application Layer (App Program: DHCP, DNS, HTTP, LDAP, SMTP, FTP)
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
              
# Presentation Layer, 表現層
# Remote Access Services (遠端連線)

* VPN, Virtual Private Network

* TELNET, Terminal Emulation Protocol

* rLogin, rsh, rcp

* Screen Scraper

* Virtual Desktop & Virtual Apps

# RPC, Remote Procedure Call

It allows executing obj accross hosts, with a client sending instruction to an app resided on different host in network, there are some services in this category, such as: Distributed Computing Env.

Plz note that RPC doesn't provide any service on its own, it only provides basic auth and address the target service. So it can be considered as a Broker.

# Session Layer, 會議層
# Tunneling (隧道)

using PPP in Layer5 is as same as PPP used in Layer 2.

