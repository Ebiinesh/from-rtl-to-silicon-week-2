# 🧩 Week 2 — BabySoC Fundamentals & Functional Modelling

> "The journey of a thousand circuits begins with a single idea."  
> — *VSD SoC Learning Path*

## 🚀 Introduction / Objective

This week's task focuses on building a foundational understanding of **System-on-Chip (SoC)** design and practicing **functional modelling** using simulation tools like **Icarus Verilog** and **GTKWave**. The goal is to comprehend the core components of an SoC and model a simplified **BabySoC** to explore its behavior before advancing to RTL and physical design stages. By the end, we will summarize key learnings in a concise write-up and visualize the SoC design flow.

---

## 🧠 Conceptual Overview

A **System-on-Chip (SoC)** integrates multiple components of a computer system into a single chip, enabling compact, power-efficient, and high-performance designs for devices like smartphones, IoT gadgets, and embedded systems.

### What is a System-on-Chip (SoC)?
- **Definition**: An SoC is an integrated circuit that combines a processor, memory, peripherals, and interconnects on a single chip.
- **Purpose**: Reduces size, power consumption, and cost while improving performance.
- **Examples**: Modern SoCs power devices like Raspberry Pi, mobile phones, and automotive systems.

### Components of a Typical SoC
- **CPU**: The brain of the SoC, executing instructions (e.g., RISC-V, ARM).
- **Memory**: Includes SRAM, DRAM, or ROM for data and instruction storage.
- **Peripherals**: Interfaces like UART, SPI, or I2C for external communication.
- **Interconnects**: Buses (e.g., AMBA, Wishbone) or Network-on-Chip (NoC) for data transfer between components.

### Why BabySoC?
- **Simplified Model**: BabySoC is a minimal SoC design with a basic CPU, memory, and peripherals, ideal for learning SoC concepts without overwhelming complexity.
- **Learning Tool**: Helps understand integration, communication, and verification before scaling to complex designs.

### Role of Functional Modelling
- **Purpose**: Functional modelling simulates the high-level behavior of an SoC without delving into hardware specifics.
- **Why Before RTL?** Allows validation of system behavior and architecture early, catching design flaws before detailed RTL coding.
- **Tools Used**: Icarus Verilog for simulation and GTKWave for waveform visualization.

---

## ⚙️ Technical Sections

### SoC Architecture
A typical SoC integrates:
- **CPU Core**: Executes software instructions.
- **Memory Hierarchy**: Cache, RAM, or ROM for fast data access.
- **Peripherals**: Enable interaction with external devices (e.g., sensors, displays).
- **Interconnect**: Facilitates communication using buses or NoC.

BabySoC simplifies this by using:
- A minimal RISC-V core.
- A small memory block.
- Basic peripherals (e.g., counter or UART).
- A simple bus for connectivity.

### Functional Modelling
- **Definition**: A high-level simulation of system behavior using abstract models.
- **Process**:
  1. Define system components (CPU, memory, peripherals).
  2. Model interactions using Verilog.
  3. Simulate using Icarus Verilog.
  4. Analyze waveforms in GTKWave.

### Simulation / Verification
- **Simulation**: Run Verilog code to mimic BabySoC behavior.
- **Verification**: Check if outputs match expected results (e.g., CPU reading/writing to memory).
- **Tools**:
  - **Icarus Verilog**: Compiles and simulates Verilog code.
  - **GTKWave**: Visualizes signal waveforms for debugging.

---

## 📊 Diagrams

### 1. BabySoC Block Diagram
```mermaid
graph TD
    A[CPU] -->|Bus| B[Memory]
    A -->|Bus| C[Peripherals]
    B -->|Data| A
    C -->|Control Signals| A
    subgraph BabySoC
        A
        B
        C
    end
```

### 2. Functional Modelling Process
```mermaid
sequenceDiagram
    participant Designer
    participant IcarusVerilog
    participant GTKWave
    Designer->>IcarusVerilog: Write Verilog code for BabySoC
    IcarusVerilog->>Designer: Simulate and generate VCD file
    Designer->>GTKWave: Load VCD file
    GTKWave->>Designer: Display waveforms
    Designer->>Designer: Verify functionality
```

### 3. SoC Design Flow
```mermaid
flowchart TD
    A[Concept] --> B[Functional Modelling]
    B --> C[RTL Design]
    C --> D[Synthesis]
    D --> E[Physical Design]
    E --> F[Tapeout]
```

---

## 🛠️ Tools Used

| Tool            | Purpose                                      |
|-----------------|----------------------------------------------|
| Icarus Verilog  | Compiles and simulates Verilog code          |
| GTKWave         | Visualizes simulation waveforms              |
| Verilog         | Hardware description language for modelling  |

---

## 🔌 Data Flow / Signal Chart

```mermaid
graph TD
    CPU[CPU] -->|Read/Write| MEM[Memory]
    CPU -->|Control Signals| PER[Peripherals]
    MEM -->|Data| CPU
    PER -->|Data/Status| CPU
    subgraph BabySoC
        CPU
        MEM
        PER
    end
```

This diagram illustrates the data flow in BabySoC:
- **CPU ↔ Memory**: Data and instructions are read/written via a bus.
- **CPU ↔ Peripherals**: Control signals manage peripheral operations.
- **Peripherals → CPU**: Status or data feedback.

---

## 📝 Summary

This week's task provided a deep dive into **SoC fundamentals** and the role of **functional modelling**. Key learnings include:
- **SoC Components**: Understanding the integration of CPU, memory, peripherals, and interconnects.
- **BabySoC**: A simplified model to grasp SoC concepts without overwhelming complexity.
- **Functional Modelling**: Validates system behavior before RTL, saving time and effort.
- **Tools**: Icarus Verilog and GTKWave enable simulation and verification.

This task lays the groundwork for future stages like **RTL design**, **synthesis**, and **physical design**, where we will translate high-level models into hardware realities.

---

## 📂 Repository / Credits

- **Project Name**: BabySoC Fundamentals
- **Author**: Ebinesh K
- **Course**: VSD SoC Journey
- **Tools Used**: Icarus Verilog, GTKWave
- **Week**: 2
- **Status**: Completed

> “From function to fabrication — every chip begins as an idea.”  
> — *VSD SoC Learning Path*