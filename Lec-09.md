# Lec-9: Introduction to Process

---

## 1. What is a Program?

- A **program** is a **compiled piece of code** that is ready to be executed.
- It is **passive**: just a file stored on disk, not currently doing anything.

---

## 2. What is a Process?

- A **process** is a **program under execution**.
- It is **active**: occupies memory, uses CPU, and performs tasks.

---

## 3. How Does the Operating System Create a Process?

The OS converts a program into a process using the following steps:

### Steps:

a. **Load the program and static data** into memory  
b. **Allocate runtime stack** for function calls and returns  
c. **Allocate heap memory** for dynamic memory usage  
d. Perform **I/O operations** (e.g., load files or devices if needed)  
e. **Handoff control to `main()`** function of the program  

---

## 4. Architecture of a Process

A typical process is divided into the following memory segments:

- **Text (Code) Segment** – holds the compiled program instructions  
- **Data Segment** – stores global and static variables  
- **Heap Segment** – for dynamically allocated memory (`malloc`, `new`)  
- **Stack Segment** – stores function calls, local variables, return addresses  

---

## 5. Attributes of a Process

- Every process has **unique attributes** to identify and manage it.
- The OS keeps track of all active processes using a **Process Table**.

### Process Table:

- A table-like structure maintained by the OS
- Each row represents one process
- Each entry is called a **Process Control Block (PCB)**

---

## 6. What is PCB (Process Control Block)?

- A **data structure** used by the OS to **store information about a process**.

### Information stored in a PCB includes:

- Process ID (PID)
- Process state (Running, Waiting, Ready, etc.)
- Program counter
- CPU registers
- Priority
- Memory pointers
- Accounting and I/O status

---

## 7. PCB and CPU Context Switching

- When a **process is paused** (e.g., its time slice expires):
  - The **CPU registers** related to that process are saved into its **PCB**
- When the process is **resumed**:
  - Those values are **restored from PCB back into CPU registers**

> This mechanism allows the OS to **pause and resume processes efficiently**, enabling multitasking.

---

## Summary

- **Program** = Passive code  
- **Process** = Active execution of that code  
- OS uses **PCB** to manage all process-related data  
- During context switch, **register values are saved/restored** using PCB

