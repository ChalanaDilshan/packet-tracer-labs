# Lab02: Basic Switch and End Device Configuration

## Objective

* Set up a basic network topology with switches and PCs
* Configure basic device settings such as hostnames and prevent DNS lookups
* Secure access to switches using Console and Privileged EXEC passwords
* Configure Switch Virtual Interfaces (SVI) for remote management
* Verify end-to-end connectivity using ping

---

## Topology

### Interconnected Switches and PCs

S1 (F0/1) -------- (F0/1) S2
 |                        |
 | (F0/6)                 | (F0/18)
 |                        |
PC-A                     PC-B

(Add your screenshot here: topology.png)

---

## IP Configuration

### PC-A

* IP: 192.168.1.10
* Subnet: 255.255.255.0

### PC-B

* IP: 192.168.1.11
* Subnet: 255.255.255.0

---

### Switch 1 (RegNo-S1) - VLAN 1

* IP: 192.168.1.1
* Subnet: 255.255.255.0

### Switch 2 (RegNo-S2) - VLAN 1

* IP: 192.168.1.2
* Subnet: 255.255.255.0

---

## Steps

### Part 1: Set Up the Network Topology

1. Connect S1 and S2 using a **Copper Cross-Over cable** (F0/1 to F0/1)
2. Connect PC-A to S1 (F0/6) and PC-B to S2 (F0/18) using **Copper Straight-Through cables**
3. Visually inspect network connections (wait for green link lights)

---

### Part 2: Configure PC Hosts

1. Assign static IP addresses and subnet masks to PC-A and PC-B
2. Verify PC settings

---

### Part 3: Configure and Verify Basic Switch Settings

1. Access the switch via Console and enter Global Configuration Mode (`configure terminal`)
2. Assign hostnames (`hostname RegNo-S1`)
3. Disable DNS lookup (`no ip domain-lookup`)
4. Configure Console password (`line console 0` -> `password 1234` -> `login`)
5. Configure encrypted Privileged EXEC password (`enable secret class`)
6. Encrypt all plain-text passwords (`service password-encryption`)
7. Configure the MOTD banner (`banner motd #Authorized Access Only#`)
8. Assign IP addresses to VLAN 1 (SVI) and enable the interfaces (`no shutdown`)
9. Save the running configuration to NVRAM (`copy running-config startup-config`)

---

## Testing

From PC-A:
ping 192.168.1.11 (Testing PC to PC connectivity)
ping 192.168.1.1 (Testing PC to Switch connectivity)

---

## Result

* PC-A successfully communicates with PC-B
* PC-A successfully communicates with both switches (S1 and S2)
* Switch configurations are successfully secured and saved

---

## Key Learning

* Familiarized with Cisco IOS command modes (User EXEC, Privileged EXEC, Global Config)
* Securing device access is a critical first step in network configuration
* Switch Virtual Interfaces (SVIs) allow Layer 2 switches to have IP addresses for remote management
* Unsaved configurations are lost when a device reboots; always save to `startup-config`

---