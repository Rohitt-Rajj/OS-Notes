#  Process States and Queues

---

## 1. Process States

A process goes through multiple states during its life cycle:

| State       | Description |
|-------------|-------------|
| **New**     | The process is being created. OS has picked the program to convert into a process. |
| **Ready**   | The process is loaded into memory and waiting to be assigned CPU time. |
| **Running** | The process is currently being executed by the CPU. |
| **Waiting** | The process is waiting for an I/O operation to complete. |
| **Terminated** | The process has finished execution and is removed from the process table. |

---

## 2. Process Queues

The OS manages processes using different queues:

### a. Job Queue
- Contains **processes in the New state**
- Located in **secondary memory**
- Managed by the **Long-Term Scheduler (LTS)**, which selects and loads jobs into main memory

### b. Ready Queue
- Contains **processes in the Ready state**
- Located in **main memory**
- Managed by the **Short-Term Scheduler (STS)** (CPU Scheduler), which selects the next process to run

### c. Waiting Queue
- Contains **processes that are waiting** for I/O completion

---

## 3. Degree of Multiprogramming

- Defined as the **number of processes loaded into main memory** at one time.
- Controlled by the **Long-Term Scheduler (LTS)**.

---

## 4. Dispatcher

- A component of the OS that **gives control of the CPU** to the process selected by the Short-Term Scheduler.
- It handles:
  - Context switching
  - Switching to user mode
  - Jumping to the proper location in the program



