# Process Scheduling | FCFS | Convoy Effect

---

## 📌 1. Introduction to Process Scheduling

- **Process Scheduling** is the **core of multiprogramming operating systems**.
- It helps the OS improve productivity by **efficiently allocating CPU** to processes.
- When a process is **waiting or its time quantum expires**, the CPU is taken away and assigned to another ready process.

---

## 🧠 2. CPU Scheduler

- The **CPU Scheduler** (Short-Term Scheduler) is invoked **whenever the CPU becomes idle**.
- It selects a process from the **Ready Queue** and assigns the CPU to it.

---

## 🔁 3. Types of Scheduling

### 🟠 Non-Preemptive Scheduling
- Once CPU is given to a process, it **keeps it** until it:
  - Terminates
  - Switches to I/O or wait state
- ❌ **Disadvantages**:
  - **Starvation**: Long burst time process can block others
  - **Low CPU utilization**

### 🟢 Preemptive Scheduling
- CPU can be **taken away** from a running process after:
  - A time quantum expires
  - It enters wait state or terminates
- ✅ **Advantages**:
  - Better responsiveness
  - Less starvation
  - Higher CPU utilization

---

## 🎯 4. Goals of CPU Scheduling

| Goal                 | Meaning                                                  |
|----------------------|----------------------------------------------------------|
| Max CPU Utilization  | Keep CPU as busy as possible                             |
| Min Turnaround Time  | Complete processes quickly (TAT = CT - AT)               |
| Min Waiting Time     | Reduce time spent in ready queue (WT = TAT - BT)         |
| Min Response Time    | Fast first response (ready → first CPU access)           |
| Max Throughput       | Increase number of completed processes per time unit     |

---

## 📚 5. Scheduling Terminologies

| Term            | Meaning                                                                |
|------------------|------------------------------------------------------------------------|
| Arrival Time (AT) | Time when process enters ready queue                                  |
| Burst Time (BT)   | Time required by the process to execute                               |
| Completion Time (CT) | Time when process finishes execution                               |
| Turnaround Time (TAT) | Total time in system: `TAT = CT - AT`                             |
| Waiting Time (WT) | Time spent waiting for CPU: `WT = TAT - BT`                           |
| Response Time     | Time from ready queue entry to first CPU use                         |

---

## 🧮 6. FCFS (First-Come, First-Serve) Scheduling

- Processes are scheduled in **order of arrival** (like a queue).
- **No preemption** — the first process to enter the ready queue gets CPU first.

### ❌ Problem with FCFS: Convoy Effect

- When a **long burst time process** is at the front of the queue:
  - Short processes have to wait unnecessarily.
  - Leads to **high average wait time** and **low CPU and I/O utilization**.
  
#### 🧱 Convoy Effect Definition:
> A situation where many short tasks are blocked behind a single long task holding the CPU or I/O, leading to **inefficient resource use**.

---

## ✅ Summary

| Feature             | Non-Preemptive      | Preemptive            |
|---------------------|---------------------|------------------------|
| CPU Reclaim         | No (runs till done) | Yes (time quantum/wait)|
| Starvation          | More likely         | Less likely            |
| CPU Utilization     | Low                 | High                   |
| Suitable for        | Simple, batch jobs  | Time-sharing systems   |
