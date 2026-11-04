# 💾 SSD & HDD

> SSDs and HDDs provide persistent storage, keeping programs and files available after power is removed.

## 📖 What Is Persistent Storage?

**Persistent storage** retains data without continuous electrical power.

Computers use it to store:

- Operating systems
- Applications
- Documents
- Photos and videos
- Databases
- Other saved data

Two common storage-device technologies are:

- **SSD — Solid-State Drive**
- **HDD — Hard Disk Drive**

> 💡 Storage retains saved data. RAM provides temporary working space for active programs.

---

## ⚙️ What Is an HDD?

An **HDD (Hard Disk Drive)** stores data magnetically on rotating platters.

### Main Components

| Component | Purpose |
| :--- | :--- |
| **Platters** | Hold magnetically recorded data |
| **Spindle Motor** | Rotates the platters |
| **Read/Write Heads** | Read and change recorded data |
| **Actuator** | Positions the heads over the required tracks |
| **Controller** | Manages commands, data transfers, and internal operations |
| **Cache** | Buffers data during operation |

### How an HDD Works

1. The controller receives a request.
2. The actuator moves the heads toward the required location.
3. The platter rotates until the target data passes beneath the head.
4. Data is read or written.

```text
Request
   │
   ▼
Head Positioning
   │
   ▼
Rotational Waiting
   │
   ▼
Read / Write
```

Mechanical movement contributes to access latency, particularly for scattered requests.

### Strengths

- Often economical for large storage capacities
- Useful for bulk files, backups, and other capacity-focused workloads

### Limitations

- Mechanical access delays
- Operating noise and vibration
- Sensitivity to physical shock, especially during operation

---

## ⚡ What Is an SSD?

An **SSD (Solid-State Drive)** stores data electronically, commonly using **NAND flash memory**.

It has no moving mechanical parts.

### Main Components

| Component | Purpose |
| :--- | :--- |
| **NAND Flash** | Stores data persistently |
| **Controller** | Manages data placement and device operations |
| **Firmware** | Implements internal management behavior |
| **DRAM, Where Present** | Supports tasks such as mapping and buffering |

Some SSDs operate without dedicated DRAM. Certain designs can use supported host-memory features.

### How an SSD Works

1. The controller receives a request.
2. It translates the requested logical address into an internal flash location.
3. Data is read or written electronically.
4. Background management maintains usable flash space and distributes wear.

Flash memory is generally programmed in **pages** and erased in larger **blocks**.

This requires management techniques such as:

- **Wear leveling**
- **Garbage collection**
- **Error correction**
- **Logical-to-physical address mapping**

### Strengths

- Low access latency
- Strong random-access performance
- Silent operation
- Greater resistance to mechanical shock than HDDs

### Limitations

- Finite flash-write endurance
- Performance that can vary with workload and available space
- Cost per unit of capacity that may be higher than HDDs

---

## ⚖️ SSD vs. HDD

| Feature | SSD | HDD |
| :--- | :--- | :--- |
| **Storage Technology** | Semiconductor memory | Magnetic recording |
| **Moving Parts** | No | Yes |
| **Access Latency** | Typically much lower | Includes mechanical delays |
| **Random Access** | Typically much faster | Limited by head movement and rotation |
| **Noise** | Silent storage mechanism | May produce mechanical noise |
| **Shock Resistance** | Generally higher | Mechanically sensitive |
| **Cost per Capacity** | Often higher | Often lower |
| **Write Behavior** | Managed around flash programming and erasing | Managed around magnetic recording |

Actual performance and durability depend on the model and workload.

---

## 🔗 Interfaces, Protocols, and Form Factors

These terms describe different characteristics.

| Category | What It Describes | Examples |
| :--- | :--- | :--- |
| **Form Factor** | Physical shape and dimensions | 2.5-inch, 3.5-inch, M.2 |
| **Interface / Interconnect** | How the device connects and transfers data | SATA, PCIe |
| **Command Interface / Protocol** | How software communicates storage commands | AHCI, NVMe |

### SATA

**SATA** is used by many HDDs and SSDs.

A SATA SSD can provide much lower access latency than an HDD while remaining limited by its SATA connection.

### PCIe and NVMe

**PCIe** provides the interconnect used by many high-performance SSDs.

**NVMe** is a storage protocol designed for non-volatile storage, commonly used over PCIe.

### M.2

**M.2 describes a physical form factor and connector arrangement.**

An M.2 SSD may use:

- SATA
- PCIe with NVMe

Compatibility depends on the SSD and the motherboard slot.

> 📌 Not every M.2 SSD is NVMe, and not every NVMe SSD uses the M.2 form factor.

---

## 📐 Common Physical Formats

### 3.5-Inch

Commonly used by desktop and capacity-focused HDDs.

### 2.5-Inch

Used by many SATA SSDs and smaller HDDs.

### M.2

A compact module format commonly used for internal SSDs.

Module length, electrical support, and available clearance must match the system.

### External Drives

External storage combines a drive with an enclosure and a connection such as USB.

Performance depends on both the internal drive and the external connection.

---

## 📊 Understanding Storage Performance

### Sequential Performance

Measures access to large, contiguous ranges of data.

Relevant to tasks such as copying large files.

### Random Performance

Measures access to scattered locations.

Important for operating systems, applications, and many database workloads.

### Latency

The time taken to complete an operation.

Low latency contributes to system responsiveness.

### IOPS

**IOPS — Input/Output Operations Per Second** measures the number of operations completed per second under specified conditions.

IOPS figures are meaningful only alongside details such as:

- Request size
- Read/write mix
- Queue depth
- Access pattern

### Sustained Performance

Performance during a long transfer may differ from short benchmark results.

SSD behavior can change because of:

- Write-cache exhaustion
- Temperature
- Available free space
- Background maintenance
- Workload characteristics

> 💡 Peak sequential speed does not describe every aspect of real-world storage performance.

---

## 🧬 SSD Flash Types

NAND categories describe how many bits are stored per cell.

| Type | Bits per Cell |
| :--- | :--- |
| **SLC** | 1 |
| **MLC** | 2 |
| **TLC** | 3 |
| **QLC** | 4 |

Storing more bits per cell increases density but introduces trade-offs in programming behavior and endurance.

The complete drive design matters. Flash type alone does not determine overall quality.

Some SSDs use part of their flash in an **SLC-like caching mode** to improve short-duration write performance.

---

## 🛡️ Endurance and Reliability

### SSD Endurance

A common endurance specification is **TBW — Terabytes Written**.

It describes an amount of host-written data associated with the manufacturer's specified endurance or warranty conditions.

TBW is not a precise countdown to device failure.

### HDD Reliability

HDDs can experience mechanical, electronic, and recording-related failures.

Their suitability depends on the workload, environment, and product design.

### Monitoring

Storage devices may expose health information through **SMART** or other health logs.

These tools can provide useful indicators, but they cannot predict every failure.

> ⚠️ Any storage device can fail. Important data needs separate, recoverable backups.

### RAID Is Not a Backup

RAID can improve availability or performance, depending on its configuration.

It does not replace protection against:

- Accidental deletion
- Malware
- Theft
- Fire
- Application errors
- Other shared failures

---

## 🧹 TRIM and SSD Maintenance

**TRIM**, or an equivalent deallocation command, allows the operating system to tell an SSD which logical storage ranges are no longer needed.

This helps the controller manage flash more effectively.

### Practical Considerations

- Keep sufficient free space for normal operation.
- Allow the operating system to manage supported SSD optimization.
- Do not routinely apply traditional HDD-style defragmentation to an SSD.
- Follow manufacturer guidance for firmware maintenance.

Deleting a file or issuing TRIM is not a universal guarantee of secure data erasure.

---

## 🎯 Choosing Between SSD and HDD

| Requirement | Typical Choice |
| :--- | :--- |
| **Responsive operating system and applications** | SSD |
| **Fast access to active project files** | SSD |
| **Large amounts of economical bulk storage** | HDD may be suitable |
| **Mixed performance and capacity needs** | SSD for active work, HDD for bulk data |
| **Backups** | Either can be appropriate as part of a suitable backup strategy |

Before choosing, consider:

- Capacity
- Compatibility
- Workload
- Sustained performance
- Endurance requirements
- Noise and power use
- Backup and recovery needs
- Cost

---

## ✅ Key Takeaways

- SSDs and HDDs retain saved data without continuous power.
- HDDs use magnetic platters and moving heads.
- SSDs commonly use NAND flash and have no moving parts.
- Form factor, interface, and protocol describe different things.
- M.2 does not automatically mean NVMe.
- Latency and random performance matter alongside sequential speed.
- Endurance ratings and health indicators do not eliminate the need for backups.

## 📝 Review Questions

1. How does persistent storage differ from RAM?
2. Why are HDD random accesses affected by mechanical movement?
3. What does an SSD controller manage?
4. How do SATA, PCIe, NVMe, and M.2 differ?
5. Why might an SSD's sustained write speed differ from its peak speed?
6. What does TBW describe?
7. Why does RAID not replace backups?

---

[⬅️ **Back to Computer Hardware**](./README.md)
