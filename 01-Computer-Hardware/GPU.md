# What is a GPU

 A Graphics Processing Unit (GPU) is a specialized processor designed to accelerate the rendering
 of images, animations, and video. Unlike a CPU, which is optimized for general-purpose tasks, GPU's
 are optimized for **parallel processing**, allowing them to handle thousands of simultaneous operations.
 Today, GPUs are not only used for gaming and graphics but also for **Artifical Intelligence (AI), High-
 Performance Computing (HPC), Machine Learning, Data Science, and Cryptocurrency Mining.**

 ## History of GPU 

 - **1980s-1990s:** Early graphics cards (2D accelerators) were mostly used to offload simple rendering
tasks from CPUs. Companies like Matrox, S3, and 3dfx pioneered consumer graphics.

- **1999: NVIDIA** introduced the **GeForce 256**, officially marketing it as the "**world's first GPU**".
It brought hardware transform and lighting (T&L), which was revolutionary for 3D gaming.

- **2000s: AMD** (through ATI acquisition) became NVIDIA's biggest competitor with the ** Radeon series**.
The competition focused on **DiretX and OpenGL performance**.

- **2010s:** GPUs became essential for more than gaming. With CUDA (NVIDIA, 2006) and OpenCL, GPUs were adopted
in scientific research, AI and big data.

- **Today:** Modern GPUs are capable of real-time ray tracing, AI-powered rendering (DLSS, FSR), and data
center-level AI training (NVIDIA A100, H100, AMD Instinct MI300).

## How GPU Works

 GPUs are built with hundreds to thousands of cores optimized for parallel processing.

 - CPUs handle sequential task  efficiently

 - GPUs break down large workloads (like rendering a 3D scene or training an AI model) into many smaller tasks
processes simultaneously.

### Key components:

- Cores (CUDA cores for NVIDIA, Stream Processors for AMD) -> handle massive parallelism.

- VRAM (Video RAM, e.g., GDDR6, HBM) -> provides fast memory access.

- Shaders -> execute graphical and compute instructions.

- Ray Tracing Units (RT cores in NVIDIA, Ray Accelerators ind AMD) -> simulate realistic lightining.

- Tensor Cores (NVIDIA) -> accelerate AI and deep learning.

## Types of GPU

**1. Integrated GPUs (iGPU):**

- Built into the CPU (Intel UHD, AMD Vega, Apple M-series).
- Lower performance but energy efficient.
- Used in laptops, office PCs.

**2. Dedicated/Discrete GPUs:**

- Separate hardware unit (NVIDIA GeForce, AMD Radeon).
- High performance, gaming, and content creation.

**3. Workstation GPUs:**

- Designed for 3D rendering, CAD, simulations (NVIDIA Quadro/RTX A series, AMD Radeon Pro).

**4. Data Center/AI GPUs:**

- Optimized for HPC, AI training, cloud computing (NVIDIA A100/H100, AMD Instinct MI250/MI300).

## Major Manufacturers & Architectures 

### NVIDIA
