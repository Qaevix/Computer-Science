# ⚙️ CPU Modes

> CPU operating modes define how a processor executes instructions, addresses memory, and applies architectural rules.

## 📖 What Are CPU Modes?

A **CPU operating mode** determines important aspects of processor behavior, including:

- Which instruction features are available
- How memory addresses are interpreted
- Which protection mechanisms can be used
- How software interacts with the processor

Different processor architectures define different modes.

This guide focuses on **x86 and x86-64**, followed by a separate explanation of **user mode and kernel mode**.

> 📌 Operating modes, privilege levels, and power states describe different aspects of CPU operation.

---

## 🧭 Main x86 Operating Modes

| Mode | Main Purpose | Key Characteristics |
| :--- | :--- | :--- |
| **Real Mode** | Legacy execution and early startup | 16-bit environment without protected-mode memory isolation |
| **Protected Mode** | Protected execution for operating systems | Supports privilege levels, memory protection, and optional paging |
| **Virtual 8086 Mode** | Legacy execution within a protected-mode system | Runs real-mode-style software under operating-system supervision |
| **Long Mode** | x86-64 execution environment | Includes 64-bit mode and compatibility mode |
| **System Management Mode** | Firmware-level system management | Separate execution environment entered through a system management interrupt |

---

## 🕰️ Real Mode

**Real mode** provides an execution environment based on the original 8086 programming model.

### Main Characteristics

- Uses 16-bit default operand and address sizes
- Calculates addresses using segment-and-offset addressing
- Does not provide protected-mode privilege isolation
- Does not use paging

The original 8086 used a **20-bit address space**, corresponding to **1 MiB** of addressable memory. Later processors include additional legacy-addressing details.

### Where It Appears

- Legacy operating systems such as DOS
- Traditional BIOS startup code
- Early stages of conventional x86 processor startup

> 💡 Real mode is important for understanding x86 history and boot behavior, even though modern operating systems use more capable execution environments.

---

## 🛡️ Protected Mode

**Protected mode** introduces mechanisms that allow operating systems to control access to memory and privileged operations.

It was introduced with the 80286 and extended with 32-bit capabilities in the 80386.

### Main Characteristics

- Supports privilege levels
- Uses descriptor-based segmentation
- Supports memory-access protection
- Supports paging on the 80386 and later processors
- Can execute 16-bit and 32-bit code, depending on configuration

### Why It Matters

An operating system can use these mechanisms to isolate applications and protect its own memory.

For example, an application attempting an unauthorized memory access can trigger an exception instead of freely accessing another program's data.

> 📌 Protected mode provides mechanisms. The operating system must configure and use them correctly.

---

## 🕹️ Virtual 8086 Mode

**Virtual 8086 mode**, commonly called **virtual-8086 mode** or **VM86**, supports real-mode-style programs within a protected-mode environment.

### Main Characteristics

- Available on the 80386 and later supporting processors
- Allows an operating system to supervise legacy execution
- Restricts or intercepts certain operations
- Is not available while long mode is active

### Important Distinction

Virtual 8086 mode is a specific x86 architectural feature.

It is **not the same as a modern virtual machine** running through a hypervisor.

---

## 🚀 Long Mode

**Long mode** is the x86-64 execution environment.

Intel documentation also calls this environment **IA-32e mode**.

It contains two submodes:

```text
Long Mode / IA-32e Mode
├── 64-Bit Mode
└── Compatibility Mode
```

### 64-Bit Mode

Designed for 64-bit operating-system and application code.

Features include:

- 64-bit general-purpose registers
- Additional general-purpose registers
- A larger virtual address space than traditional 32-bit execution
- Revised segmentation behavior
- Paging as a required part of the environment

The number of implemented address bits depends on the processor and system configuration.

> 📌 A 64-bit processor does not necessarily implement a full 64-bit physical or virtual address space.

### Compatibility Mode

Allows supported 16-bit or 32-bit protected-mode code to execute under a 64-bit operating system.

Actual application support depends on the operating system and its software environment.

Compatibility mode does **not** directly provide real-mode or virtual-8086 execution.

---

## 🔧 System Management Mode — SMM

**System Management Mode** is a separate environment used for certain firmware-controlled platform-management tasks.

The processor enters SMM in response to a **System Management Interrupt (SMI)**.

### Main Characteristics

- Executes firmware handlers in a separate environment
- Uses a protected memory region commonly called **SMRAM**
- Saves processor state before running the handler
- Returns to the interrupted environment using a special resume operation

SMM is distinct from ordinary operating-system kernel execution.

---

## 🔐 Privilege Levels: User Mode and Kernel Mode

Operating modes describe the execution environment.

**Privilege levels** determine which operations executing software is allowed to perform within that environment.

On x86, privilege levels are commonly called **rings**:

```text
Ring 0 → Highest privilege
Ring 1
Ring 2
Ring 3 → Lowest privilege
```

Many general-purpose operating systems mainly use:

- **Ring 0** for kernel execution
- **Ring 3** for application execution

### User Mode

Applications normally execute with restricted privileges.

They cannot freely:

- Execute privileged instructions
- Modify protected processor configuration
- Access kernel memory
- Directly control arbitrary hardware

An application can access memory and resources that the operating system has made available to it.

### Kernel Mode

The operating-system kernel executes with elevated privileges.

It manages responsibilities such as:

- Memory mappings and protection
- Process and thread scheduling
- Interrupt handling
- Device access
- System-call processing

Kernel privilege does not mean every address is automatically accessible under every configuration. Memory mappings and architectural protections still matter.

### Comparison

| Aspect | User Mode | Kernel Mode |
| :--- | :--- | :--- |
| **Typical Software** | Applications | Operating-system kernel and many drivers |
| **Privilege** | Restricted | Elevated |
| **Privileged Instructions** | Not directly permitted | Permitted subject to architectural rules |
| **Memory Access** | Limited to allowed mappings | Broader access under operating-system control |
| **System Services** | Requested through defined interfaces | Implemented or coordinated by the kernel |

> 💡 A 64-bit application can run in user mode while the 64-bit kernel runs at a higher privilege level. Both can execute in 64-bit mode.

---

## 🔄 How Applications Request Kernel Services

Applications use **system calls** to request operations managed by the operating system.

Examples include:

- Opening or reading a file
- Creating a process
- Sending data through a socket
- Requesting memory-management operations

A simplified flow is:

```text
Application in User Mode
           │
           │ System Call
           ▼
Kernel Entry and Validation
           │
           │ Perform Requested Operation
           ▼
Return to User Mode
```

The kernel checks arguments, permissions, and other conditions before carrying out a request.

A system call can change the privilege level without switching from 64-bit mode to a different architectural operating mode.

---

## 🧵 Mode Switch vs. Context Switch

These concepts are related but different.

### Privilege Transition

Execution moves between privilege levels, such as entering the kernel from an application.

This does not necessarily change which task is running.

### Context Switch

The operating system changes the running thread or process.

It saves the required execution state and restores the state of another task.

| Event | Necessarily Changes the Running Task? |
| :--- | :--- |
| **System Call** | No |
| **Interrupt** | No |
| **Context Switch** | Yes |

The operating system may decide to schedule another task while handling a system call or interrupt, but that is a separate decision.

---

## 🖥️ What About Virtualization?

Hardware virtualization provides additional controls for running guest operating systems.

For example:

- Intel uses **VMX root** and **VMX non-root** operation.
- AMD provides virtualization facilities through **AMD-V / SVM**.

These controls are separate from ordinary user/kernel privilege levels.

A guest operating system can run its own kernel at guest ring 0 while remaining subject to hypervisor controls.

> 📌 “Ring −1” is an informal description sometimes used for a hypervisor. It is not an additional numbered x86 privilege ring.

---

## 🔋 What CPU Modes Are Not

The word “mode” is also used informally for other processor features.

### Power and Idle States

Power-management mechanisms affect activity, energy use, and responsiveness.

They do not replace architectural execution modes such as protected mode or long mode.

### Performance Settings

Boost behavior, frequency scaling, and power profiles influence performance and power consumption.

They are not the same as user mode, kernel mode, or 64-bit mode.

### Safe Mode

An operating system's **Safe Mode** is a reduced software-startup configuration.

It is not a CPU architectural operating mode.

---

## ✅ Key Takeaways

- CPU modes depend on the processor architecture.
- **Real mode** preserves a legacy x86 execution environment.
- **Protected mode** provides mechanisms for controlled and isolated execution.
- **Long mode** includes 64-bit mode and compatibility mode.
- **SMM** provides a separate firmware-management environment.
- **User mode and kernel mode describe privilege**, rather than separate 32-bit or 64-bit execution environments.
- A system call does not necessarily cause a context switch.
- Virtualization controls and power states are separate concepts.

## 📝 Review Questions

1. What changes when a CPU operates in a different architectural mode?
2. How does protected mode differ from real mode?
3. What are the two submodes of long mode?
4. Why are user mode and 64-bit mode not competing categories?
5. How does a system call differ from a context switch?
6. Why is virtual 8086 mode different from a modern virtual machine?
7. How does SMM differ from ordinary kernel execution?

---

[⬅️ **Back to Computer Hardware**](./README.md)
