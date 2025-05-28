# Hybrid DRAM-NVM Memory System Simulation using DRAMSim2

This repository contains the design, implementation, and simulation results for a **Hybrid Memory System** that integrates **DRAM as a cache** and **NVM (Non-Volatile Memory) as main memory**, using the open-source memory simulator **DRAMSim2**.

> 📘 Developed as part of the Computer Architecture and Design course (ECE 6005) at **The George Washington University**

## 📌 Project Overview

As data-intensive applications grow, the demand for **high-performance and energy-efficient** memory systems has increased. This project addresses the **limitations of DRAM** (high power consumption) and the **challenges of NVM** (high write latency) by designing a **hybrid architecture** that uses:

- **DRAM** for low-latency access (hot data)
- **NVM** for energy-efficient storage (cold data)

## 🧠 Key Features

- Implemented DRAM as a **write-back cache** layer for NVM
- Customized memory configurations via `dram.ini` and `nvm.ini`
- Employed **LRU and FIFO cache replacement policies**
- Simulated memory access flows using C++ header files:
  - `HybridSystem.h`
  - `CacheController.h`
  - `MainMemoryController.h`
- Evaluated performance using metrics like **latency**, **power**, and **bandwidth**

## ⚙️ Tools & Technologies

- 🧠 **DRAMSim2** — Cycle-accurate DRAM memory simulator
- 💻 C++ — For system and cache controller implementation
- 📊 Custom `.ini` files for DRAM and NVM parameter configuration

## 📈 Results Summary

| Metric               | Hybrid System        | DRAM-Only System      |
|----------------------|----------------------|------------------------|
| **Bandwidth**        | 1.152 GB/s           | 1.073 GB/s             |
| **Min Latency**      | 39.0 ns              | 130.5 ns               |
| **Max Latency**      | 99.4 ns              | 160.5 ns               |
| **Power Consumption**| 1.552 W              | 3.349 W                |
| **Transactions**     | 58                   | 27                     |

✅ **Hybrid system outperforms DRAM-only in latency, energy, and efficiency.**

## 🧪 Evaluation Methodology

- Configured hybrid architecture via:
  - `HybridSystem.h`, `CacheController.h`, `MainMemoryController.h`
- Memory models defined in:
  - `dram.ini` – Configures DRAM latency, banks, refresh
  - `nvm.ini` – Models low-power NVM without refresh
  - `system.ini` – Defines cache size, associativity, and policy
- Simulations executed using DRAMSim2 on realistic access traces


