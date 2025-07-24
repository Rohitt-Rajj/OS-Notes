# Booting Process in a Computer

The booting process is the sequence of events that a computer follows when it is powered on, to load the operating system.

---

## i. PC is Powered On

- When the power button is pressed, the CPU gets power and begins the booting process.

---

## ii. BIOS or UEFI is Loaded

- The CPU looks for a special firmware program stored in a **ROM chip** on the motherboard.
- This firmware is called:
  - **BIOS** (Basic Input/Output System) in older systems
  - **UEFI** (Unified Extensible Firmware Interface) in modern systems

### What is BIOS?
- A low-level firmware stored in ROM.
- Allows the system to initialize and test hardware components.
- Provides access to setup configuration.

### What is UEFI?
- A more advanced replacement for BIOS.
- Can do everything BIOS can, and much more (like network booting, secure boot).
- Acts like a small operating system itself.
- Often includes **Intel Management Engine**, which supports remote management features.

---

## iii. POST (Power-On Self-Test)

- The CPU executes BIOS/UEFI to perform POST.
- POST checks the basic hardware (RAM, CPU, storage, etc.).
- If something is wrong (like no RAM), the system throws an error and stops.
- If everything is fine, the system moves to the next step.

---

## iv. BIOS/UEFI Hands Off Control to Bootloader

- Once POST is successful, BIOS/UEFI looks for a storage device (HDD/SSD).
- It looks for a **bootloader** program, stored in:
  - **MBR (Master Boot Record)** in BIOS-based systems
  - **EFI system partition** in UEFI-based systems

### What is MBR?
- A special section at the beginning of a storage device.
- Contains a small piece of code (bootloader) to load the operating system.

---

## v. Bootloader Loads the Operating System

- The bootloader is responsible for loading the actual OS.
- It loads the **kernel** and starts the **user space** programs.

### Common Bootloaders:
- **Windows**: Uses **Windows Boot Manager** (`bootmgr.exe`)
- **Linux**: Uses **GRUB** (GNU GRand Unified Bootloader)
- **macOS**: Uses **boot.efi**

---

## Summary Flow:

1. Power button pressed
2. CPU loads BIOS/UEFI from ROM
3. BIOS/UEFI performs POST (hardware check)
4. BIOS/UEFI finds bootloader from MBR or EFI partition
5. Bootloader loads OS kernel and starts user space

