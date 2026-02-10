# 🔐 Secure Enterprise Network Design using VLAN, Inter-VLAN Routing, NAT & Simulated ISP

## 📌 Project Overview

This project demonstrates the design and implementation of a secure enterprise network using Cisco Packet Tracer.  

The goal of this project is to simulate a real-world company network where multiple departments are logically separated using VLANs, connected through Inter-VLAN routing, and provided internet access using NAT (PAT) with a simulated ISP.

Through this implementation, I learned practical networking concepts including VLAN segmentation, router-on-a-stick, NAT configuration, routing, and network troubleshooting.

---

## 🏢 Problem Statement

In enterprise environments:

- All departments should NOT share the same network
- Internal traffic must be controlled and secure
- Private IPs must access the internet
- Internal IPs must be hidden from external networks

To solve this, I designed a segmented and secure architecture using:

- VLANs for isolation
- Router for routing
- NAT for internet access
- Simulated ISP for external connectivity

---

## 🎯 Project Objectives

- Create separate VLANs for HR, IT, and Finance
- Implement Inter-VLAN routing using Router-on-a-Stick
- Provide internet connectivity using NAT Overload (PAT)
- Simulate ISP and public server
- Ensure network segmentation and security
- Understand real enterprise architecture

---

## 🖥️ Network Architecture

> <img width="958" height="633" alt="Screenshot 2026-02-10 110718" src="https://github.com/user-attachments/assets/96bb2b0b-dc1d-4c65-b495-9944b5333b77" />



Internal PCs
↓
Switch (VLANs + Trunk)
↓
Enterprise Router (Inter-VLAN + NAT)
↓
ISP Router
↓
Public Server (8.8.8.8)



---

## 📊 VLAN & IP Addressing Scheme

| Department | VLAN | Network Address | Default Gateway |
|------------|--------|----------------|----------------|
| HR | 10 | 192.168.10.0/24 | 192.168.10.1 |
| IT | 20 | 192.168.20.0/24 | 192.168.20.1 |
| Finance | 30 | 192.168.30.0/24 | 192.168.30.1 |

### WAN Network
200.0.0.0/30

### Public Network
8.8.8.0/24

---

## ⚙️ Technologies & Concepts Used

- VLAN configuration
- Access ports & trunk ports
- 802.1Q encapsulation
- Router-on-a-stick
- Inter-VLAN routing
- Static routing
- Default routing
- NAT (PAT Overload)
- Access Control Lists (ACL)
- ISP simulation
- Network troubleshooting

---

## 🔧 Implementation Steps

### 1️⃣ VLAN Creation (Switch)

- Created VLAN 10 (HR)
- Created VLAN 20 (IT)
- Created VLAN 30 (Finance)
- Assigned access ports to each VLAN
- Configured trunk port to router

---

### 2️⃣ Inter-VLAN Routing (Router-on-a-Stick)

- Created subinterfaces:
  - G0/0.10
  - G0/0.20
  - G0/0.30
- Assigned IP addresses as gateways
- Enabled 802.1Q encapsulation

This allows communication between VLANs through the router.

---

### 3️⃣ NAT Configuration

- Marked inside interfaces (LAN)
- Marked outside interface (WAN)
- Created ACL for private networks
- Enabled NAT Overload

This converts private IPs into a single public IP for internet access.

---

### 4️⃣ Simulated ISP Setup

Since Packet Tracer does not have real internet:

- Added ISP Router
- Created public network (8.8.8.0/24)
- Added public server (8.8.8.8)
- Added static route back to enterprise

This simulates real-world internet behavior.

---

## 🔄 Packet Flow Explanation

When HR PC (192.168.10.2) pings 8.8.8.8:

1. PC sends packet to gateway
2. Router performs NAT → converts to 200.0.0.1
3. Packet goes to ISP router
4. ISP forwards to public server
5. Server replies
6. Router reverses NAT
7. Reply reaches PC

---

## 🔐 Security Features Implemented

### VLAN Segmentation
Departments are isolated from each other.

### Controlled Inter-VLAN Routing
Traffic must pass through router.

### NAT Protection
Internal IPs are hidden from external network.

### Reduced Broadcast Traffic
Each VLAN forms its own broadcast domain.

---

## 🧪 Testing & Verification Commands

Used the following commands for troubleshooting:

show ip route
show ip interface brief
show ip nat translations
show ip nat statistics
show access-lists


Verified:
- Routing works
- NAT translations created
- Internet simulation successful

---

## 🧠 Key Learnings

Through this project, I gained:

- Hands-on VLAN configuration experience
- Understanding of router subinterfaces
- Practical NAT implementation
- Knowledge of enterprise network design
- ISP simulation concept
- Troubleshooting skills

This project strengthened my foundation in Networking and Cybersecurity.

---

## 🛠 Tools Used

- Cisco Packet Tracer
- Cisco 1941 Router
- Cisco 2960 Switch
- CLI Configuration

---

## 🚀 Future Improvements

- Add firewall rules
- Implement ACL-based filtering
- Configure DHCP server
- Add DMZ network
- Implement port security
- Add IDS/IPS
- Upgrade to Layer 3 switch

---

## 📁 Files Included

- Packet Tracer file (.pkt)
- Network topology screenshot
- Project documentation (PDF)
- README.md

---

## 👨‍💻 Author

Jesowin Raja  
Networking & Cybersecurity Enthusiast  
CCNA Learner  

---

## ⭐ Conclusion

This project simulates a real enterprise network environment with proper segmentation, routing, and secure internet connectivity.  

It demonstrates practical implementation skills required for roles such as:

- Network Engineer
- Cybersecurity Engineer
- SOC Analyst
- Infrastructure Engineer

This hands-on experience helped me understand how enterprise networks are built and secured in real-world organizations.

