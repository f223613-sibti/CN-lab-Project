# Multi-Campus University Network Infrastructure Design 🌐

**Course:** Computer Networks (BSCS-5th Semester)  
**Tools Used:** Cisco Packet Tracer  
**Status:** Completed ✅

## 📌 Project Overview
This project involves the design and simulation of a robust network infrastructure for a **multi-campus university** with six geographically distributed branches across the country. The design simulates a scalable, secure, and redundant network connecting a Head Office (Data Center) to five regional campuses.

The project implements enterprise-grade networking concepts including **VLSM (Variable Length Subnet Masking)**, **OSPF Routing**, **Inter-VLAN Routing**, and **WAN Redundancy**.

---

## 🏢 Campus Architecture
[cite_start]The network consists of 6 Campuses, each with specific requirements[cite: 1, 3]:

| Campus | Region | Role | Departments |
| :--- | :--- | :--- | :--- |
| **Campus A** | Head Office | Data Center / Core | Admin, Faculty, Students, Server Farm |
| **Campus B** | North | Regional Branch | Admin, Faculty, Students |
| **Campus C** | South | Regional Branch | Admin, Faculty, Students |
| **Campus D** | East | Regional Branch | Admin, Faculty, Students |
| **Campus E** | West | Regional Branch | Admin, Faculty, Students |
| **Campus F** | Central | Regional Branch | Admin, Faculty, Students |

### Department Requirements per Campus
* **Students:** 500-1000 users (High density, requires /22 subnets)
* **Faculty:** 50-100 users
* **Admin:** 20-40 users
* **Wi-Fi Zone:** Wireless access for mobile clients

---

## ⚙️ Key Technologies & Features

### 1. IP Addressing Strategy (VLSM)
[cite_start]We used the **10.0.0.0/8** private address block, subnetted efficiently using VLSM to minimize IP wastage[cite: 5].

| Location | Network ID | CIDR | Usable Hosts |
| :--- | :--- | :--- | :--- |
| **Campus A (LAN)** | `10.10.0.0` | `/16` | 65,000+ |
| **Campus B (LAN)** | `10.20.0.0` | `/16` | 65,000+ |
| **WAN Links** | `10.99.0.0` | `/30` | 2 per link |

### 2. Routing Protocols
* [cite_start]**OSPF (Open Shortest Path First):** Configured as the Interior Gateway Protocol (IGP) to allow dynamic communication between all 6 routers[cite: 7].
* [cite_start]**Redundancy:** implemented using a Ring/Mesh topology to ensure if one WAN link fails, traffic automatically reroutes via the backup path[cite: 6].

### 3. Network Services
* **VLANs:** Traffic separated into VLAN 10 (Admin), VLAN 20 (Faculty), and VLAN 30 (Students) for security.
* **DHCP:** Automatic IP assignment for all end devices.
* **Server Farm:** Simulated DNS and Web Servers hosted at Campus A.
* [cite_start]**Security:** Basic ACLs applied to restrict student access to Admin servers[cite: 8].

---

---

## 🚀 How to Run the Simulation
1.  **Prerequisite:** Install **Cisco Packet Tracer** (Version 8.0 or newer).
2.  Clone this repository:
    ```bash
    git clone [https://github.com/your-username/university-network-design.git](https://github.com/your-username/university-network-design.git)
    ```
3.  Open the file `Final_Project.pkt`.
4.  Wait for the amber lights to turn green (Spanning Tree convergence).
5.  Use the "Add Simple PDU" (P) tool to test connectivity between campuses.

---

## 📄 License
This project is for educational purposes as part of the BSCS Computer Networks curriculum.
