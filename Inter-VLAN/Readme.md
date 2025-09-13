# Inter-VLAN Routing on Multi-Layer Switch (CCNA Practical)

##  Objective
Implement Inter-VLAN routing using a Multi-Layer Switch (MLS) with SVIs in Cisco Packet Tracer.

---

##  Tools
- Cisco Packet Tracer
- Multi-Layer Switch (MLS)
- PCs for different VLANs

---

##  Topology
- VLAN 10 → math Department (192.168.2.0/26)
- VLAN 20 → science Department (192.168.64.0/26)
- VLAN 30 → english Department (192.168.128.0/26)
- point to point connection b/w router and MLS (192.168.2.192/30)
- Multi-Layer Switch configured with SVIs for each VLAN

---

## Configuration Steps

Step 1: VLAN Creation
Switch(config)# vlan 10
Switch(config-vlan)# name math
Switch(config)# vlan 20
Switch(config-vlan)# name Science
Switch(config)# vlan 30
Switch(config-vlan)# name English

Step 2: Assign Ports to VLANs
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
(Repeat for VLAN 20, 30)

Step 3: Configure SVIs (Layer 3 Interfaces)
Switch(config)# interface fa0/1
Switch(config-if)# no switchport
Switch(config-if)# ip address 192.168.2.62 255.255.255.128
Switch(config-if)# no shutdown
(for vlan 20,30 respectively)

Step 4: Enable Routing
Switch(config)# ip routing

Step 5: Testing
Ping between VLAN 10, VLAN 20, and VLAN 30 PCs.
Use show ip route to verify routing table.

#Results

-Successful communication between VLANs.

-MLS handled both switching (Layer 2) and routing (Layer 3) functions.

-Reduced complexity compared to router-on-a-stick.


#Key Learnings

Practical use of Multi-Layer Switch for Inter-VLAN Routing

Configuring SVIs and enabling IP routing

Understanding enterprise-level Layer 3 switching
