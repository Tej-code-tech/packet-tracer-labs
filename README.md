# packet-tracer-labs
Here are the complete Network Topology Details for your project
“Context-Aware Segmented Smart Campus Architecture with Controlled Wireless Domain Enforcement” — written in a way suitable for report, viva, and diagram explanation.

⸻

# Smart Campus Network Topology Details

1️⃣ Network Architecture Model

The smart campus network follows a Hierarchical Network Design Model consisting of three layers:

Layer	Function
Core Layer	High-speed routing, backbone connectivity
Distribution Layer	Routing between VLANs, policy enforcement
Access Layer	End device connectivity
Wireless Layer	WiFi access for lecturer, students, guests
Data Center	Servers and centralized services

This design improves:
	•	Scalability
	•	Security
	•	Performance
	•	Fault tolerance
	•	Network management

2️⃣ Core Layer Topology

Devices Used
	•	Core Switch 1 (Layer 3)
	•	Core Switch 2 (Layer 3)
	•	ISP Router
	•	Data Center Switch

Connections

Device	Port	Connected To	Port
Core SW1	G0/1	Core SW2	G0/1
Core SW1	G0/2	Academic Dist	G0/1
Core SW1	G0/3	Admin Dist	G0/1
Core SW1	G0/4	Hostel Dist	G0/1
Core SW1	G0/5	Wireless Switch	G0/1
Core SW1	G0/6	Data Center Switch	G0/1
Core SW1	G0/0	ISP Router	G0/0

Core switches are connected using EtherChannel for redundancy and load balancing.

Core Layer Responsibilities
	•	Inter-VLAN Routing
	•	OSPF Routing
	•	ACL Security Policies
	•	DHCP Relay
	•	Default Route to Internet
	•	Network Redundancy (HSRP/VRRP)
	•	Traffic Filtering

3️⃣ Distribution Layer Topology

Distribution Switches

Distribution Switch	Department
Academic Distribution	Academic Blocks
Admin Distribution	Administrative Offices
Hostel Distribution	Student Hostels
Wireless Distribution	Access Points

Each distribution switch connects to the core switch via trunk link.

Distribution Layer Responsibilities
	•	VLAN Routing
	•	Access Control Lists
	•	Broadcast Control
	•	Policy Enforcement
	•	Inter-department communication control

⸻

4️⃣ Access Layer Topology

Access switches connect end devices.

Access Switch	Connected Devices
Academic Access	Faculty PCs
Smart Classroom Access	Digital TVs, Smart Boards, Lab Machines
Admin Access	Office PCs
Hostel Access	Student Devices
Wireless Access	Access Points

Access Layer Responsibilities
	•	Device connectivity
	•	VLAN assignment
	•	Port security
	•	Storm control
	•	Spanning Tree PortFast

5️⃣ Wireless Network Topology

SSIDs and VLAN Mapping

SSID	VLAN	Users
CAMPUS-LECTURER	VLAN 30	Lecturers
CAMPUS-STUDENT	VLAN 40	Students
CAMPUS-GUEST	VLAN 70	Visitors
SMART-DEVICES	VLAN 20	TVs & Lab Machines

Access Points connect to the Wireless Switch using trunk ports so multiple VLANs can pass through.

Wireless Network Rules
	•	Smart classroom devices work only in Lecturer WiFi
	•	Guest network → Internet only
	•	Student network → No Admin/Data Center access
	•	Lecturer network → Access to Smart Devices and LMS

6️⃣ Data Center Topology

Servers Located in Data Center VLAN 60

Server	Function
DHCP Server	Automatic IP addressing
DNS Server	Name resolution
LMS Server	Learning Management System
Database Server	Institutional data
RADIUS Server	Wireless authentication
Monitoring Server	Network monitoring
Syslog Server	Log management

Data center connects directly to Core Layer for high-speed access.

7️⃣ VLAN Segmentation Design

VLAN	Name	Network
VLAN 10	Academic	192.168.10.0/24
VLAN 20	Smart Devices	192.168.20.0/24
VLAN 30	Lecturer WiFi	192.168.30.0/24
VLAN 40	Hostel	192.168.40.0/24
VLAN 50	Admin	192.168.50.0/24
VLAN 60	Data Center	192.168.60.0/24
VLAN 70	Guest	192.168.70.0/24
VLAN 99	Management	192.168.99.0/24

This segmentation:
	•	Reduces broadcast traffic
	•	Improves performance
	•	Provides security isolation

8️⃣ Routing Topology (OSPF Multi-Area)

Area	Department
Area 0	Core Backbone
Area 10	Academic
Area 20	Administration
Area 30	Hostel
Area 40	Wireless
Area 60	Data Center

Benefits:
	•	Scalable network
	•	Fast convergence
	•	Reduced routing traffic
	•	Easy expansion

9️⃣ Security Topology

Access Restrictions

From	To	Allowed
Hostel	Admin	❌
Hostel	Data Center	❌
Guest	Admin	❌
Guest	Data Center	❌
Smart Devices	Lecturer WiFi	✅
Smart Devices	Data Center	✅
Academic	Data Center	✅
Lecturer	Smart Devices	✅

Security implemented using:
	•	ACL
	•	VLAN segmentation
	•	Port security
	•	WPA2 Enterprise
	•	RADIUS authentication
	•	DHCP Snooping
	•	Dynamic ARP Inspection

🔟 Redundancy Topology

Redundancy implemented at:

Component	Method
Core Switch	Dual Core
Gateway	HSRP
Links	EtherChannel
Routing	OSPF
Internet	Dual path (optional)

This ensures network never goes down during maintenance or failure.

Final Topology Summary

The smart campus network topology includes:
	•	Hierarchical network design
	•	VLAN segmentation for departments
	•	Multi-area OSPF routing
	•	Controlled wireless network for lecturers and smart devices
	•	Isolated hostel and guest networks
	•	Secure administrative and data center networks
	•	Centralized DHCP and authentication servers
	•	Redundant core switches and links
	•	Broadcast traffic control
	•	Centralized monitoring system
	•	Scalable architecture for future AI labs and IoT classrooms


The campus network is designed using a hierarchical topology consisting of core, distribution, and access layers. The core layer connects all major network segments including academic, administrative, hostel, wireless, and data center networks. VLAN segmentation is used to isolate different departments and reduce broadcast traffic. Multi-area OSPF is implemented for scalable routing. Smart classroom devices are restricted to operate only within the lecturer wireless network using VLAN and ACL policies. Administrative and data center networks are secured from hostel and guest networks. Redundancy is achieved using dual core switches, EtherChannel links, and HSRP gateway redundancy. Centralized DHCP, RADIUS authentication, and monitoring servers are placed in the data center for network management and security.
