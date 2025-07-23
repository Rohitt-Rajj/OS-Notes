# Components of OS
## Kernel vs User Space

### 1. Kernel

- The kernel is the **core part of the Operating System**.
- It directly interacts with the **hardware** (CPU, memory, storage).
- It performs all the critical tasks like:
  - Managing memory
  - Scheduling processes
  - Handling device input/output
- The **first part of the OS to load** when the system starts (boot loader loads the kernel).
- Runs in **privileged (protected) mode** with full access to hardware.

Summary:
- Core component of the OS
- Talks directly to hardware
- First to load on startup

### 2. User Space

- The user space is where **application software** (like browsers, editors, media players) runs.
- Applications in user space **do not access hardware directly**.
- They communicate with the kernel to get things done using **system calls**.
- Provides interfaces like:
  - **GUI (Graphical User Interface)** – buttons, windows, etc.
  - **CLI (Command Line Interface)** – terminal or command prompt

Summary:
- Where all user apps run
- Cannot access hardware directly
- Communicates with the kernel for hardware tasks

### Example:

When you open a file in a text editor:
- App (in user space) requests the file
- Request goes to the kernel
- Kernel reads the file from disk and gives it back to the app



## Functions of Kernel

The kernel is responsible for managing the system's key resources. Its main functions include:

---

### 1. Process Management

- Handles all tasks related to **processes** (running programs).
- Manages:
  - **Process scheduling** – deciding which process runs when
  - **Creating and deleting** processes (both user and system)
  - **Suspending and resuming** processes
  - Providing tools for **synchronization** and **inter-process communication (IPC)**

Example:
- Running multiple apps like Chrome, VS Code, and Spotify — kernel manages them all.

---

### 2. Memory Management

- Manages the computer's **RAM (main memory)**.
- Responsibilities:
  - Allocates memory when needed and frees it when not used
  - Keeps track of **which part of memory is in use**, and by which process

Example:
- Ensures Chrome and Word do not overwrite each other’s memory.

---

### 3. File Management

- Handles everything related to **files and directories**.
- Responsibilities:
  - Creating and deleting files and folders
  - Organizing files into directories
  - Mapping files to **secondary storage** (like HDD or SSD)
  - Supports **backups** and file recovery

Example:
- When you save a file in Notepad, the kernel ensures it is stored on disk safely.

---

### 4. I/O Management (Input/Output)

- Manages all **input and output devices**, like keyboard, mouse, printer, etc.
- Handles data transfer smoothly using:

#### a. Spooling
- Stands for "Simultaneous Peripheral Operation On-Line"
- Used when **devices are slower than CPU**
- Stores data temporarily until the device is ready
- Example: **Print spooling**, **mail spooling**

#### b. Buffering
- Temporary storage used during data transfer within a job
- Helps match speed between CPU and devices
- Example: **Buffering YouTube video** while watching

#### c. Caching
- Stores frequently used data in faster memory
- Increases speed and reduces delay
- Example: **Memory cache**, **web browser cache**

---

### Summary

| Function           | Description                                       |
|--------------------|---------------------------------------------------|
| Process Management | Manages running programs and their execution      |
| Memory Management  | Allocates and tracks memory usage                 |
| File Management    | Handles file creation, deletion, and organization |
| I/O Management     | Controls all input/output operations              |

## Types of Kernels in Operating System

---

### 1. Monolithic Kernel

- All core OS functions are inside the **kernel space**.
- All system services (file management, memory, process, I/O) run in the kernel.
- **Large in size** and uses **more memory**.
- **High performance** due to fast communication (no user-kernel mode switching).
- **Less reliable**: if one part crashes, the whole system may fail.

#### Key Features:
- All services in kernel
- Fast performance
- Bulky and less modular
- High memory usage
- Less stable in case of failure

**Examples**: Linux, Unix, MS-DOS

---

### 2. Microkernel

- Only **essential services** are in the kernel (e.g., memory and process management).
- Other services like **file system and I/O** run in **user space**.
- **Small in size**, more secure and reliable.
- **Slower performance** due to frequent switching between user mode and kernel mode.

#### Key Features:
- Only core parts in kernel
- Smaller and more modular
- More reliable and stable
- Slower due to user ↔ kernel mode communication

**Examples**: MINIX, L4 Linux, Symbian OS

---

### 3. Hybrid Kernel

- A combination of **monolithic and microkernel**.
- Tries to get the **performance** of monolithic and the **stability** of microkernel.
- Some services (like file system) are in user space; others stay in kernel space.
- **Less switching overhead** compared to microkernel.

#### Key Features:
- Mixed design
- Good performance and stability
- Moderate memory use
- Modular but not fully separated

**Examples**: Windows NT, Windows 7/10, macOS

---

### 4. Nano Kernel / Exo Kernel

#### Nano Kernel:
- Contains only the **most basic functionalities**, like low-level hardware control.
- Everything else is handled outside the kernel.
- Extremely **small and lightweight**.

#### Exo Kernel:
- Minimal kernel that gives applications **direct access to hardware**.
- Offers maximum control to developers.
- Used in **research or high-performance systems**.

#### Key Features:
- Minimal design
- Customization and flexibility
- High efficiency but complex to manage

**Examples**: ExoKernel (MIT research), KeyKOS (nano-style)

---

## Summary Table

| Kernel Type     | Size      | Performance | Reliability | Example OS             |
|------------------|-----------|-------------|-------------|--------------------------|
| Monolithic       | Large     | High        | Low         | Linux, Unix, MS-DOS      |
| Microkernel      | Small     | Lower       | High        | MINIX, Symbian, L4 Linux |
| Hybrid Kernel    | Medium    | Balanced    | Balanced    | Windows NT/10, macOS     |
| Nano/Exo Kernel  | Very Small| High (custom)| High       | ExoKernel, KeyKOS        |

## Shell in Operating System

- A shell is a **program that provides an interface between the user and the kernel**.
- It allows users to interact with the OS by **entering commands** or using graphical elements.
- The shell receives user commands, passes them to the kernel, and shows the output.

### Functions of Shell:
- Takes user input (command or click)
- Communicates with the OS kernel
- Displays results or output to the user

### Types of Shell:

1. **Command-Line Interface (CLI)**
   - Text-based interface
   - User types commands manually
   - Examples: Bash, Zsh, PowerShell

2. **Graphical User Interface (GUI)**
   - Visual interface using windows, icons, and menus
   - User interacts using mouse/keyboard
   - Examples: Windows Explorer, GNOME, KDE

### Example:

- You type `ls` in a terminal (CLI shell) →  
  The shell asks the kernel to list files →  
  The output (list of files) is shown on the screen

### Summary:
- Shell = Interface between user and kernel
- CLI and GUI are two types
- Important part of how users control the OS
