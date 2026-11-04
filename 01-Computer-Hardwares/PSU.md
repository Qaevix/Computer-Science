# 🔌 What Is a PSU?

> A Power Supply Unit converts incoming electrical power into the regulated outputs required by computer components.

## 📖 Definition of a PSU

A **PSU (Power Supply Unit)** supplies electrical power to a computer.

In a typical desktop system, it converts **AC power from a wall outlet** into **regulated DC power** used by the motherboard, processor, graphics card, storage devices, and other components.

### AC and DC

- **AC — Alternating Current:** Current periodically changes direction.
- **DC — Direct Current:** Current flows in one direction.

Desktop components require regulated DC supplies rather than direct connection to household AC power.

> 💡 A PSU powers the system. Its wattage rating describes its output capability, not how much electricity the computer constantly consumes.

---

## ⚙️ How a PSU Works

A simplified conversion process includes:

1. **Input filtering** — Reduces electrical interference.
2. **Rectification** — Converts AC into DC.
3. **High-frequency switching and conversion** — Transforms electrical power efficiently.
4. **Output rectification and filtering** — Produces usable DC outputs.
5. **Regulation** — Keeps output voltages within their required ranges.

```text
Wall Outlet — AC
       │
       ▼
Filtering and Rectification
       │
       ▼
Switching and Conversion
       │
       ▼
Regulated DC Outputs
       │
       ▼
Computer Components
```

The motherboard and graphics card contain additional voltage regulators that convert PSU outputs into the lower voltages required by their chips.

---

## ⚡ Output Voltages

Traditional desktop ATX power supplies provide several outputs.

| Output | Common Uses |
| :--- | :--- |
| **+12 V** | CPU and GPU power-conversion circuits, fans, pumps, and some drive components |
| **+5 V** | Certain devices, interfaces, and storage electronics |
| **+3.3 V** | Motherboard circuits and compatible devices |
| **Standby Power** | Supports functions such as power-on control while the system is connected to power |

Exact power arrangements depend on the platform. Some designs move more voltage conversion onto the motherboard.

---

## 📊 Understanding PSU Wattage

A PSU's rated wattage indicates how much electrical power it can supply under its specified operating conditions.

For example, a **750 W PSU** does not constantly deliver 750 W.

Actual output depends on the connected system's demand.

### Choosing Capacity

Consider:

- CPU power requirements
- GPU power requirements
- Other components and peripherals
- Short-duration power-demand changes
- Operating temperature
- Manufacturer recommendations
- Reasonable allowance for future upgrades

> 📌 Higher wattage alone does not guarantee better quality, reliability, or efficiency.

---

## 🌱 Efficiency

Efficiency describes how much input power becomes usable output power.

```text
Efficiency = Output Power ÷ Input Power
```

For example, if a PSU supplies **400 W** at **90% efficiency**:

```text
Input Power ≈ 400 ÷ 0.90
            ≈ 444 W
```

Approximately **44 W** is lost, mainly as heat.

### Efficiency Certifications

Programs such as **80 PLUS** classify efficiency under defined test conditions.

An efficiency rating does not provide a complete assessment of:

- Electrical performance
- Noise
- Component quality
- Protection behavior
- Long-term reliability

Efficiency also varies with load and operating conditions.

---

## 🔗 Common PSU Connections

| Connection | Purpose |
| :--- | :--- |
| **24-Pin ATX** | Main power connection on many desktop motherboards |
| **4-Pin / 8-Pin CPU Power** | Supplies the motherboard's CPU power circuitry |
| **PCIe 6-Pin / 8-Pin** | Supplemental power for compatible graphics cards |
| **16-Pin GPU Power** | Used by graphics cards designed for compatible high-power connectors |
| **SATA Power** | Powers SATA storage devices and compatible accessories |
| **Peripheral Power** | Used by certain older devices and accessories |

Connector requirements vary by component.

### Cable Compatibility

- CPU and GPU power connectors are not interchangeable.
- Modular PSU cables may have different wiring at the PSU end.
- A cable that physically fits is not necessarily electrically compatible.
- Use cables explicitly approved for the exact PSU model.

> ⚠️ Do not mix modular cables between power supplies unless compatibility is explicitly confirmed by the manufacturer.

---

## 🧩 Modular PSU Types

### Non-Modular

All cables are permanently attached.

- Simple installation
- Unused cables remain inside the case

### Semi-Modular

Some cables are fixed, while others are removable.

### Fully Modular

The output cables are removable.

- Easier cable selection and routing
- Requires careful attention to cable compatibility

Modularity describes cable attachment, not electrical quality.

---

## 📐 PSU Form Factors

| Form Factor | Typical Use |
| :--- | :--- |
| **ATX** | Many desktop computer cases |
| **SFX** | Compact systems |
| **SFX-L** | Compact systems supporting a longer PSU chassis |
| **Proprietary** | Systems with manufacturer-specific physical or electrical requirements |

Check case clearance as well as the stated form factor. Cable space can also affect installation.

---

## 🛡️ Protection Features

Common protection mechanisms include:

| Protection | Purpose |
| :--- | :--- |
| **OCP — Overcurrent Protection** | Limits excessive current |
| **OVP — Overvoltage Protection** | Responds to excessive output voltage |
| **UVP — Undervoltage Protection** | Responds to output voltage falling below limits |
| **OPP — Overpower Protection** | Responds to excessive total load |
| **SCP — Short-Circuit Protection** | Responds to short circuits |
| **OTP — Overtemperature Protection** | Responds to excessive temperature |

Implementation and triggering thresholds vary between products.

---

## 🌡️ Cooling and Noise

PSUs generate heat during power conversion.

Cooling depends on:

- Load
- Efficiency
- Ambient temperature
- Airflow
- Fan design and control

Some models stop their fans at low loads. This behavior depends on the design and operating conditions.

Follow the case and PSU instructions for installation orientation and ventilation.

---

## 🔍 Choosing a PSU

Check:

- [ ] Suitable continuous output capacity
- [ ] Required connectors
- [ ] Compatibility with the case
- [ ] Appropriate electrical and protection performance
- [ ] Independent testing where available
- [ ] Efficiency across relevant loads
- [ ] Noise characteristics
- [ ] Warranty and support
- [ ] Compatibility of every modular cable

### Handling Precaution

Do not open a PSU enclosure. Internal components can retain dangerous electrical charge after it is unplugged.

---

## ✅ Key Takeaways

- A desktop PSU converts AC input into regulated DC outputs.
- Rated wattage is output capacity, not constant consumption.
- Efficiency and overall quality are different characteristics.
- Connector and cable compatibility are essential.
- Modularity affects cable management.
- Appropriate capacity, protections, and electrical performance matter more than wattage alone.

## 📝 Review Questions

1. Why do desktop computers need AC-to-DC conversion?
2. Does a 750 W PSU always consume 750 W?
3. How does efficiency affect heat and input power?
4. Why should modular PSU cables not be mixed without checking compatibility?
5. What is the difference between modularity and electrical quality?

---

[⬅️ **Back to Computer Hardware**](./README.md)
