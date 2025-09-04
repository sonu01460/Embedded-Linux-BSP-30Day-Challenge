# 📅 Day 1 – Introduction to BSP

## 📌 What is a BSP?
A **Board Support Package (BSP)** is the software layer that allows Linux to run on custom hardware.  
It ties together:
- **Bootloader (U-Boot)** → Runs first, initializes hardware, loads kernel.
- **Linux Kernel** → Manages CPU, memory, and peripherals.
- **Device Tree (DTS/DTB)** → Hardware description passed to the kernel.
- **Root Filesystem (rootfs)** → Userland: BusyBox, applications, libraries.
- **Drivers** → Software that makes peripherals usable.

---

## 📌 Example: Boot Flow
Typical boot sequence of an ARM board:  
Power On → BootROM → U-Boot → Linux Kernel → Init → Shell

**Explanation:**
1. **Power On** → Hardware reset.  
2. **BootROM** → Chip vendor ROM code loads U-Boot from flash/SD/eMMC.  
3. **U-Boot** → Initializes DRAM, storage, and loads Linux kernel + DTB.  
4. **Kernel** → Starts drivers, mounts rootfs.  
5. **Init process** → First user-space process (BusyBox/systemd).  
6. **Shell** → You get the Linux prompt.

---

## 📌 Task for Day 1
1. Draw your board’s boot sequence.  
2. Make a list of peripherals (UART, GPIO, I²C, SPI, Ethernet, etc.).  

Example (for an ARM Cortex-A9 board):  
- UART0 for serial console  
- I²C1 for temperature sensor  
- SPI0 for external flash  
- GPIO for LEDs/buttons  
- Ethernet for networking  

---

## ✅ Checkpoint
Be able to:
- Explain what a BSP is.
- Describe the **boot flow** from power-on to Linux shell.
