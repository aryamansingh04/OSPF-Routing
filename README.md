# 🚀 Computer Networks Lab  
## 📡 Experiment 11 & 12 – Routing using OSPF, RIP, and EIGRP

---

## 📌 Overview
This project demonstrates routing in computer networks using three protocols:
- 🔹 OSPF (Open Shortest Path First)
- 🔹 RIP (Routing Information Protocol)
- 🔹 EIGRP (Enhanced Interior Gateway Routing Protocol)

The implementation is done using Cisco Packet Tracer.

---

## 🧱 Network Topology
```
PC1 ── R1 ── R2 ── R3 ── PC3
         │
        PC2
```

---

## 🛠️ Devices Used
- 3 Routers (R1, R2, R3)
- 3 PCs
- Serial DCE cables
- Copper straight-through cables

---

## 🌐 IP Addressing Scheme

| Device | Interface | IP Address |
|--------|----------|-----------|
| R1 | Fa0/0 | 192.168.10.1 |
| R1 | S0/0/0 | 10.1.1.1 |
| R2 | Fa0/0 | 192.168.20.1 |
| R2 | S0/0/0 | 10.1.1.2 |
| R2 | S0/0/1 | 10.2.2.1 |
| R3 | Fa0/0 | 192.168.30.1 |
| R3 | S0/0/1 | 10.2.2.2 |

---

# 🔵 EXP 11: OSPF Configuration

## 🎯 Aim
To configure and verify OSPF routing protocol.

---

## ⚙️ Configuration

### 🔹 Router R1
```bash
router ospf 1
network 192.168.10.0 0.0.0.255 area 0
network 10.1.1.0 0.0.0.3 area 0
```

### 🔹 Router R2
```bash
router ospf 1
network 192.168.20.0 0.0.0.255 area 0
network 10.1.1.0 0.0.0.3 area 0
network 10.2.2.0 0.0.0.3 area 0
```

### 🔹 Router R3
```bash
router ospf 1
network 192.168.30.0 0.0.0.255 area 0
network 10.2.2.0 0.0.0.3 area 0
```

---

## 🔍 Verification
```bash
show ip route
show ip ospf neighbor
```

---

## ✅ Result
OSPF routing was successfully configured and verified.

---

# 🔁 EXP 12: RIP Configuration

## 🎯 Aim
To configure and verify RIP protocol.

---

## ⚙️ Configuration (All Routers)
```bash
router rip
version 2
no auto-summary

network 192.168.10.0
network 192.168.20.0
network 192.168.30.0
network 10.0.0.0
```

---

## 🔍 Verification
```bash
show ip route
show ip protocols
```

---

## ✅ Result
RIP routing was successfully configured.

---

# 🚀 EXP 12: EIGRP Configuration

## 🎯 Aim
To configure and verify EIGRP protocol.

---

## ⚙️ Configuration (All Routers)
```bash
router eigrp 100
no auto-summary

network 192.168.10.0
network 192.168.20.0
network 192.168.30.0
network 10.0.0.0
```

---

## 🔍 Verification
```bash
show ip route
show ip eigrp neighbors
```

---

## ✅ Result
EIGRP routing was successfully configured.

---

# 🧠 Key Differences

| Feature | OSPF | RIP | EIGRP |
|--------|------|-----|------|
| Type | Link State | Distance Vector | Hybrid |
| Speed | Fast | Slow | Very Fast |
| Metric | Cost | Hop Count | Bandwidth + Delay |

---

# 📂 Submission
- Packet Tracer `.pkt` file  
- README.md  

---

# 💯 Author
Aryaman Singh
