# Smart City E-Governance Network (e-gov.bd)

![Logical Topology](Smart%20City%20E-Governance%20Network.png)

## Overview
A production-grade, enterprise network simulation engineered to support a secure municipal e-governance infrastructure. Built entirely within Cisco Packet Tracer using a single Class C public block (`192.170.25.0/24`), the architecture scales across **17 distinct subnets**, enforcing strict zero-trust segmentation between classified defense branches and general public administrative bodies.

## Quick Links
* **[Complete Project Report (PDF)](Smart%20City%20E-Governance%20Network.pdf)** - Read the full academic documentation, IPAM schemas, and validation evidence.
* **[Packet Tracer Simulation (.pkt)](Smart%20City%20E-Governance%20Network.pkt)** - Download and open the fully configured network file.
* **[Network Topology Schematic (PNG)](Smart%20City%20E-Governance%20Network.png)** - View the high-resolution architecture diagram.

---

## Technical Architecture & Specifications
* **Dynamic Routing:** OSPF Area 0 deployed across all core and ministerial gateways for automated path discovery and sub-millisecond route convergence.
* **IP Address Management (IPAM):** Advanced Variable Length Subnet Masking (VLSM) utilizing `/30` point-to-point transit links and `/29` departmental LANs to achieve zero IP waste.
* **Layer 2 Security:** Port Security configured with sticky MAC addressing (Max count: 1, Violation mode: Shutdown) on ministerial access switches.
* **WAN Perimeter:** External gateway integration featuring a simulated internet loopback interface (`8.8.8.8/32`).
* **Centralized Services:** Dedicated Data Center cluster hosting localized DNS (`e-gov.bd`), DHCP, FTP, SMTP, and HTTP web portal services.

---

## Subnet Allocation Matrix
| Zone / Department | Subnet IP | CIDR | Key Architectural Role |
| :--- | :--- | :--- | :--- |
| **ISP Edge Uplink** | `192.170.25.0` | `/30` | External WAN gateway & Loopback simulation (`8.8.8.8`) |
| **Server Farm Core** | `192.170.25.32` | `/29` | Centralized Data Center (`.34` DHCP, `.35` DNS, `.36` FTP, `.37` SMTP, `.38` HTTP) |
| **President Secretariat** | `192.170.25.28` | `/30` | High-security isolated executive VLAN node |
| **PMO & Cabinet Net** | `192.170.25.40` | `/29` | Prime Minister's Office, NSI, and Civil Service |
| **Health Ministry** | `192.170.25.48` | `/29` | EHR, emergency dispatch, and disease surveillance |
| **Finance Ministry** | `192.170.25.56` | `/29` | State treasury, payroll auditing, and taxation gateways |
| **Defense (Military)** | `192.170.25.64` | `/29` | Tri-VLAN segment for Army, Naval, Air Force, and BGB |
| **Defense (Law Enforcement)** | `192.170.25.72` | `/29` | Police ops, RAB, and CID forensics |
| **Defense (Emergency)** | `192.170.25.80` | `/29` | 999 Emergency dispatch and Coast Guard |
| **SecOps & Engineering** | `192.170.25.88` / `.96` | `/29` | CI/CD pipelines, staging hosts, and active SOC-SIEM monitoring |

---

## Implementation & Usage Guide
1. **Prerequisites:** Ensure you have **Cisco Packet Tracer (v8.0 or newer)** installed on your workstation.
2. **Open Simulation:** Download and open **`Smart City E-Governance Network.pkt`** in Packet Tracer.
3. **Verify Convergence:** Allow a few moments for Spanning Tree Protocol (STP) and OSPF Area 0 adjacencies to fully converge across all 17 subnets.
4. **Test Services:** 
   * Open the Web Browser on any departmental client PC and navigate to `http://e-gov.bd` to access the municipal portal.
   * Use the command prompt to test FTP file retrieval (`ftp 192.170.25.36`) and SMTP mail delivery.

---

## Verification & Testing Evidence
* **DNS & HTTP Resolution:** Confirmed proper domain mapping and rendering of the customized enterprise portal.
* **FTP & SMTP Operations:** Validated active file transfers and internal mail queue routing through data center server nodes.
* **OSPF Stability:** Verified real-time route recovery and stabilization during simulation stress tests.

---

## Author & Open Source Contribution
**Designed and Engineered by Fahim Uddin**  
*Undergraduate Department of Computer Science and Engineering, Southeast University*

### License
This project is open-source software licensed under the **MIT License**. You are free to use, modify, share, and contribute to this repository for educational, professional, and personal portfolio applications. Please review the LICENSE file for details.
