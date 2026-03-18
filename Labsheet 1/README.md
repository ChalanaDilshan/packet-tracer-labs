# Lab01: Introduction to Packet Tracer, Putty and CISCO IOS

## Objective

* Establish communication between two PCs using a direct connection
* Establish communication between two PCs using a switch
* Verify connectivity using ping

---

## Topology

### 1. PC to PC (Direct Connection)

PC0 -------- PC1

### 2. PC to Switch Network

PC2 ---- Switch ---- PC3

(Add your screenshot here: topology.png)

---

## IP Configuration

### PC0

* IP: 192.168.1.1
* Subnet: 255.255.255.0

### PC1

* IP: 192.168.1.2
* Subnet: 255.255.255.0

---

### PC2

* IP: 192.168.2.1
* Subnet: 255.255.255.0

### PC3

* IP: 192.168.2.2
* Subnet: 255.255.255.0

---

## Steps

### Part 1: PC to PC

1. Connect PC0 and PC1 using **Copper Cross-Over cable**
2. Assign IP addresses
3. Test using ping

---

### Part 2: PC to Switch

1. Connect PCs to switch using **Copper Straight-Through cables**
2. Assign IP addresses
3. Wait until links turn green
4. Test using ping

---

## Testing

From PC0:
ping 192.168.1.2

From PC2:
ping 192.168.2.2

---

## Result

* PC0 successfully communicates with PC1
* PC2 successfully communicates with PC3

---

## Key Learning

* Same network devices communicate without a router
* Correct cable type is critical
* Switch operates at Layer 2 (forwarding frames)
* IP configuration must be in the same subnet

---
