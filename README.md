# Basic-Routed-LAN-with-Cisco-Packet-Tracer
# 🧾 Technical Documentation: Basic Routed LAN with Cisco Packet Tracer

### 📌 Project Title:
**Small Office Network with Two Subnets and Secured Access**

---

### 🎯 Objective:
Design and configure a small office network using Cisco Packet Tracer. The network consists of two separate subnets connected via a central router, each with its own switch and set of PCs. The project includes IP configuration, securing access to network devices, and testing connectivity.

---

### 🧱 Network Topology:

| Device | Model                   | Quantity |
| ------ | ----------------------- | -------- |
| Router | Cisco 2911              | 1        |
| Switch | Cisco 2960              | 2        |
| PCs    | Generic PC              | 4        |
| Cables | Copper Straight-Through | 6        |

---

### 🗺️ Logical Design:

| Subnet | Devices           | IP Network     | Default Gateway |
| ------ | ----------------- | -------------- | --------------- |
| A      | PC0, PC1, Switch0 | 192.168.1.0/24 | 192.168.1.1     |
| B      | PC2, PC3, Switch1 | 192.168.2.0/24 | 192.168.2.1     |

---

### 🔌 Device Connections:

| From    | To      | Interface (Device A → Device B) |
| ------- | ------- | ------------------------------- |
| PC0     | Switch0 | FastEthernet0 → Fa0/1           |
| PC1     | Switch0 | FastEthernet0 → Fa0/2           |
| Switch0 | Router  | Fa0/24 → G0/0                   |
| Router  | Switch1 | G0/1 → Fa0/24                   |
| PC2     | Switch1 | FastEthernet0 → Fa0/1           |
| PC3     | Switch1 | FastEthernet0 → Fa0/2           |

---

### 🖥️ PC IP Configuration:

| PC  | IP Address   | Subnet Mask   | Default Gateway |
| --- | ------------ | ------------- | --------------- |
| PC0 | 192.168.1.10 | 255.255.255.0 | 192.168.1.1     |
| PC1 | 192.168.1.11 | 255.255.255.0 | 192.168.1.1     |
| PC2 | 192.168.2.10 | 255.255.255.0 | 192.168.2.1     |
| PC3 | 192.168.2.11 | 255.255.255.0 | 192.168.2.1     |

---
### 🧪 Testing and Verification:
 * ping from PC0 to PC1 — ✅ success

 * ping from PC0 to PC2 — ✅ success (via router)

 * ping from PC0 to Switch0 — ✅ success

 * ping from PC2 to 192.168.2.1 (router G0/1) — ✅ success

 * show ip interface brief on router confirms both interfaces are up/up

 * Switch ports show connected with show interfaces status

---
### ✅ Results:
 * PCs in different subnets can communicate via router.

 * Console and VTY access are secured on all network devices.

 * Interfaces are properly configured and up.

 * VLAN interfaces on switches respond to ping for management.

---
