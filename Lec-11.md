#  Swapping | Context Switching | Orphan Process | Zombie Process

---

## 1. Swapping

- **Swapping** is a memory management technique used in **time-sharing systems**.
- It temporarily moves a process out of main memory to **secondary storage (disk)** to free up RAM.

### Key Points:
- **Medium-Term Scheduler (MTS)** handles swapping.
- Swapping **reduces the degree of multiprogramming** (number of processes in memory).
- A swapped-out process can be **swapped back in** and **resume from where it left off**.

### When is Swapping Needed?
- To improve **process mix** in memory
- When **RAM is overcommitted**, and space must be freed

### Summary:
> Swap-out = move process from RAM → Disk  
> Swap-in = bring process back from Disk → RAM

---

## 2. Context Switching

- **Context Switching** occurs when the CPU switches from one process to another.
- It involves saving the current process's **state/context** and loading the new process’s context.

### Steps:
a. Save current process state (in its PCB)  
b. Load the new process state (from its PCB)  
c. CPU starts executing the new process

### Key Facts:
- **Done by the kernel**
- Considered **pure overhead** (no real computation happens during switching)
- Speed depends on:
  - **Number of registers**
  - **Memory speed**
  - **CPU architecture**

---

## 3. Orphan Process

- An **Orphan process** is a **child process whose parent has terminated**, but the child is still running.
- These processes are **adopted by `init` process** (PID = 1).

### Example:
If parent dies early, but the child is still executing, it becomes orphan.  
The **`init`** process ensures it is monitored and cleaned up.

---

## 4. Zombie Process (Defunct Process)

- A **Zombie** is a process that has **completed execution**, but its **entry still exists in the process table**.
- It occurs **after a child process finishes** but the parent hasn't read the exit status.

### Why Does This Happen?
- The **parent must call `wait()`** to collect the child’s exit info.
- Until then, the child remains a **Zombie**.
- Once `wait()` is called, the process is **"reaped"** and removed from the table.

### Summary:

| Feature          | Orphan Process                  | Zombie Process                       |
|------------------|----------------------------------|---------------------------------------|
| Status           | Running                         | Completed                            |
| Parent Process   | Terminated                      | Alive                                |
| Adopted by       | `init` process                  | Still linked to parent               |
| Removed by       | OS (via `init`)                 | Parent via `wait()` system call      |

---

## Process State Summary

- **Swapping**: Move processes in/out of memory
- **Context Switching**: Switch CPU from one process to another
- **Orphan**: Child still runs after parent dies
- **Zombie**: Child dies, but parent hasn’t collected its status
