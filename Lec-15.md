# Introduction to Concurrency

---

## 🔁 What is Concurrency?

- **Concurrency** is the execution of **multiple instruction sequences simultaneously**.
- It occurs when the operating system allows **multiple threads or processes** to run in parallel.
- This is especially visible in **multi-core systems**.

---

## 🧵 What is a Thread?

- A **thread** is a **lightweight process** — a single sequence of execution within a process.
- Threads share the **same address space** of the process, but have their own:
  - Program Counter (PC)
  - Registers
  - Stack

### 🔹 Characteristics:
- Independent path of execution inside a process
- Used to achieve **parallelism**
- More efficient than creating new processes

### 🔹 Real-World Example:
> In a web browser:  
> - One thread handles typing  
> - Another checks spelling  
> - Another saves content automatically

---

## 🧠 Thread Scheduling

- Threads are scheduled based on **priority**.
- The OS assigns **time slices** to each thread, even though they’re part of the same process.
- Similar to process scheduling, but lighter and faster.

---

## 🔄 Thread Context Switching

When switching between threads:

- OS **saves the current thread's state** (in TCB - Thread Control Block)
- OS **loads the next thread’s state**
- Only **thread-specific data** like program counter, registers, and stack are saved
- **No memory space switching**, making it faster than process switching
- **CPU cache** is usually preserved, improving speed

---

## 🧩 How Threads Access CPU

- Each thread has its **own program counter (PC)**
- OS uses thread scheduling to decide which thread runs next
- Context switches may happen:
  - On **I/O** wait
  - On **time quantum (TQ)** expiry

---

## ❓ Will a Single-CPU System Benefit from Multithreading?

- ❌ **No significant performance gain**
- CPU still runs only **one thread at a time**
- Context switching adds **overhead**

---

## ✅ Benefits of Multithreading

| Benefit         | Explanation                                                                            |
|-----------------|----------------------------------------------------------------------------------------|
| **Responsiveness** | UI or app remains interactive even during background operations                     |
| **Resource Sharing** | Threads share process memory and resources efficiently                          |
| **Economy**         | Creating threads is cheaper than creating processes                                |
| **Multiprocessor Utilization** | Threads can run in parallel on multi-core systems for better performance |

> Creating and managing threads is **faster and lighter** than managing processes.

---

## 📦 Summary

- **Thread** = Light-weight process
- **Concurrency** = Managing multiple threads running "at once"
- **Thread Scheduling** = Similar to process scheduling, but within the same address space
- **Context switching** is **faster** for threads than for processes
- **Multithreading shines on multi-core CPUs**

