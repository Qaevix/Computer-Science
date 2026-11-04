# 🎮 What Is a GPU?

> A Graphics Processing Unit accelerates graphics and other workloads that benefit from processing many operations in parallel.

## 📖 Definition of a GPU

A **GPU (Graphics Processing Unit)** is a processor designed for high-throughput parallel computation.

GPUs are widely used to render images, animations, and video. They also accelerate suitable workloads in:

- **Artificial intelligence and machine learning**
- **Scientific computing**
- **Data processing**
- **3D rendering**
- **Image and video processing**

GPUs achieve high throughput by executing many operations concurrently across large amounts of data.

> 💡 A GPU is especially useful when a problem can be divided into many similar operations. It does not automatically make every program faster.

### GPU vs. Graphics Card

These terms are related but have different meanings:

- **GPU** — The processor itself.
- **Graphics card** — A board containing a GPU and supporting components such as memory, power-delivery circuitry, cooling, and display connections.

Integrated GPUs are part of a processor package or system design and do not require a separate graphics card.

---

## 🕰️ History of GPUs

| Period | Development |
| :--- | :--- |
| **1980s–1990s** | Graphics hardware increasingly accelerated display operations, followed by more advanced 2D and 3D rendering. |
| **Late 1990s** | Consumer graphics hardware integrated more stages of the 3D graphics pipeline. |
| **2000s** | Programmable shaders expanded what graphics processors could do. General-purpose GPU computing also developed. |
| **2010s** | GPU computing became increasingly important in deep learning, scientific research, and large-scale data processing. |
| **Later Developments** | Specialized hardware expanded acceleration for ray tracing, matrix operations, and media processing. |

Graphics rendering and general-purpose computation remain important parts of GPU development.

---

## ⚙️ How a GPU Works

Many workloads apply similar calculations to large collections of data.

For example:

- Calculating colors for many pixels
- Transforming vertices in a 3D scene
- Performing matrix operations
- Applying an image filter
- Updating elements in a scientific simulation

A GPU schedules many groups of threads across its execution resources.

```text
Large Workload
      │
      ▼
Many Smaller Operations
      │
      ▼
Parallel GPU Execution
      │
      ▼
Results
```

Actual execution depends on the architecture, available resources, memory access patterns, and program behavior.

### Throughput and Latency

- **Throughput** describes how much work is completed over time.
- **Latency** describes how long an individual operation takes.

GPU designs emphasize high throughput. Workloads with limited parallelism, frequent branching, or substantial communication overhead may benefit less.

---

## 🧩 Main GPU Components

| Component | Purpose |
| :--- | :--- |
| **Compute / Shader Units** | Execute graphics and general-purpose calculations |
| **Registers** | Hold data needed by active threads |
| **Caches and Local Memory Resources** | Reduce costly accesses to external memory |
| **Memory Controllers** | Transfer data between the GPU and its memory |
| **Texture Units** | Support texture sampling and related graphics operations |
| **Rasterization Hardware** | Converts geometric primitives into fragments for further processing |
| **Specialized Accelerators** | Accelerate supported operations such as ray traversal or matrix calculations |
| **Media Engines** | Encode or decode supported video formats |

The exact components and terminology vary by GPU architecture.

### What Is a Shader?

A **shader** is a program executed by the GPU.

Shaders can perform tasks such as:

- Transforming vertices
- Calculating surface appearance
- Processing pixels or fragments
- Running general compute operations

> 📌 A shader is software. Shader execution units are the hardware resources that run it.

### Specialized Acceleration

Some GPUs include hardware for:

- **Ray tracing operations**, such as traversal and intersection tests
- **Matrix operations**, useful in machine learning and other numerical workloads
- **Video encoding and decoding**

Feature availability and supported operations depend on the specific GPU.

---

## 🗂️ GPU Memory

GPUs need fast access to instructions, geometry, textures, intermediate results, and other data.

### Dedicated Graphics Memory

Discrete GPUs commonly use dedicated memory technologies such as:

- **GDDR**
- **HBM — High Bandwidth Memory**

The appropriate technology depends on the product and its intended workload.

### Shared System Memory

Integrated GPUs typically use system memory shared with the CPU.

Some systems provide a unified memory architecture in which processors access a common memory pool.

### Capacity vs. Bandwidth

| Specification | Meaning |
| :--- | :--- |
| **Memory Capacity** | How much data can fit in GPU-accessible memory |
| **Memory Bandwidth** | How much data can be transferred per second |
| **Memory Latency** | How long a memory access takes |

> 💡 More VRAM does not automatically mean a faster GPU. It is useful when a workload needs the additional capacity.

---

## 🖥️ GPU Integration Types

### Integrated GPU — iGPU

An integrated GPU is incorporated into a processor or system design.

Typical characteristics include:

- Shared system memory
- Compact integration
- Suitability for power-constrained systems
- Performance that varies substantially by implementation

Integrated GPUs can support everyday graphics, media processing, gaming, and compute workloads within their capabilities.

### Discrete GPU — dGPU

A discrete GPU is a separate processor, often installed on a graphics card or built into a laptop motherboard.

Typical characteristics include:

- Dedicated graphics memory
- Independent power and cooling requirements
- A wide range of performance levels
- Use in gaming, content creation, and compute systems

---

## 🏢 GPU Workload Categories

These categories describe intended uses and can overlap.

| Category | Common Priorities |
| :--- | :--- |
| **Consumer / Gaming** | Interactive graphics, display features, and game performance |
| **Professional / Workstation** | Application support, driver validation, reliability, and professional workflows |
| **Data Center / Compute** | Compute throughput, memory capacity, interconnects, and large-scale operation |
| **Embedded / Mobile** | Energy efficiency, integration, and device-specific requirements |

A workstation or data-center GPU is not simply a gaming GPU with a different label. Product capabilities, software support, and operating requirements may differ.

---

## 🏭 GPU Vendors and Architecture Names

Examples of GPU developers include **NVIDIA, AMD, and Intel**. Other companies also develop integrated graphics for mobile and other systems.

Architecture names identify design families rather than universal performance rankings.

| Developer | Architecture Examples |
| :--- | :--- |
| **NVIDIA** | Kepler, Maxwell, Pascal, Turing, Ampere, Ada Lovelace, Hopper |
| **AMD** | GCN, RDNA families, CDNA families |
| **Intel** | Xe architecture families |

These examples are not a complete release history. Consumer and data-center designs can follow different product paths.

> 📌 **Ada Lovelace is one architecture name.** GPU architectures should not be treated as a single sequence covering every product category.

### Comparing Execution-Unit Counts

Terms such as **CUDA cores**, **stream processors**, and **execution units** describe resources within particular designs.

Their counts are not directly interchangeable across vendors or architectures.

---

## 🖼️ A Simplified Graphics Pipeline

A typical rasterization-based rendering process includes:

1. **Geometry processing** — Transform objects and vertices.
2. **Rasterization** — Determine which fragments are covered by geometric primitives.
3. **Shading** — Calculate appearance using materials, textures, and lighting.
4. **Output processing** — Apply operations such as depth testing and blending.
5. **Presentation** — Make the completed image available for display.

```text
Geometry → Rasterization → Shading → Output → Display
```

This is a simplified overview. Real rendering systems may include additional stages and combine rasterization with ray tracing.

### Ray Tracing

Ray tracing calculates visibility and light interactions by tracing rays through a scene.

Specialized GPU hardware can accelerate parts of this process, but final performance also depends on scene complexity and rendering software.

### Upscaling and Frame Generation

- **Upscaling** reconstructs a higher-resolution image from lower-resolution input and other available information.
- **Frame generation** creates additional frames using information from rendered frames and related inputs.

These techniques have different effects on image quality, responsiveness, and performance.

---

## ⚖️ GPU vs. CPU

| Aspect | CPU | GPU |
| :--- | :--- | :--- |
| **Design Emphasis** | General-purpose execution and complex control flow | High-throughput parallel execution |
| **Typical Strength** | Responsive execution across varied tasks | Similar operations across large datasets |
| **Common Workloads** | Application logic, operating systems, and compilation | Graphics, matrix calculations, and suitable simulations |
| **Parallelism** | Supports parallel execution across cores and other resources | Schedules large numbers of threads across compute resources |

CPUs and GPUs work together. Both support parallelism, but their designs favor different workload characteristics.

> 💡 GPU acceleration depends on the algorithm, implementation, data size, memory behavior, and communication overhead. There is no universal CPU-to-GPU speedup ratio.

---

## ⭐ Where GPUs Are Used

### Gaming

- Real-time rendering
- Visual effects
- Supported ray-tracing workloads
- Image reconstruction and related techniques

### Artificial Intelligence and Machine Learning

- Neural-network training
- Model inference
- Matrix and tensor operations

### Scientific Computing

- Numerical simulations
- Molecular modeling
- Weather and climate calculations
- Other parallel research workloads

### Content Creation

- 3D rendering
- Video effects
- Image processing
- Supported media encoding and decoding

### Data Processing

- Parallel analytics
- Suitable database operations
- Large-scale numerical computation

The benefits depend on software support and workload suitability.

---

## 📊 GPU Performance Factors

| Factor | Why It Matters |
| :--- | :--- |
| **Architecture** | Determines execution capabilities and resource organization |
| **Compute Resources** | Affect throughput for supported operations |
| **Clock Speed** | Influences operating frequency |
| **Memory Capacity** | Determines how much workload data can remain in GPU memory |
| **Memory Bandwidth** | Affects data transfer rates |
| **Cache Design** | Can reduce external memory traffic |
| **Numerical Precision Support** | Matters for different scientific and AI calculations |
| **Power and Cooling** | Influence sustained performance |
| **Software and Drivers** | Affect compatibility, efficiency, and available features |

### Choosing Relevant Benchmarks

Compare GPUs using workloads that match your needs:

- Games at the intended resolution and settings
- Rendering applications you use
- Specific AI models and precision settings
- Relevant scientific workloads
- Required media formats

A single specification cannot describe overall GPU performance.

---

## 🚀 Areas of Development

GPU development continues to focus on:

- Higher compute and memory throughput
- Greater energy efficiency
- Improved graphics and ray-tracing capabilities
- Specialized matrix acceleration
- Faster communication between processors
- Better software tools and workload support
- Advanced packaging and memory integration

Progress depends on both hardware design and the software that uses it.

---

## ✅ Key Takeaways

- A **GPU accelerates workloads with substantial parallelism**.
- A GPU and a graphics card are related but different things.
- **Shaders are programs**, executed by GPU hardware.
- Memory capacity and memory bandwidth describe different capabilities.
- Integrated and discrete GPUs describe integration, while gaming and workstation describe intended uses.
- Execution-unit counts are not directly comparable across all architectures.
- Real performance depends on the workload, software, memory, power, and cooling.

## 📝 Review Questions

1. What makes a workload suitable for GPU acceleration?
2. How does a GPU differ from a graphics card?
3. What is a shader?
4. How do integrated and discrete GPUs differ?
5. Why does more VRAM not automatically mean higher performance?
6. Why is comparing GPUs by core count alone misleading?
7. How do upscaling and frame generation differ?

---

[⬅️ **Back to Computer Hardware**](./README.md)
