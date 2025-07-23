## <h2 align="center">Operating System goals </h2>
- Maximum CPU utilization<br>
- Less process startvation (every process gets a fair chance to run )<br>
- Higher priority job execution<br>

### 🖥️ Types of Operating Systems

Operating Systems are classified based on how they work and how they manage resources.

---

## 1.  Batch Operating System

1. Firstly, user prepares his job using punch cards.
2. Then, he submits the job to the computer operator.
3. Operator collects the jobs from different users and sort the jobs into batches with
similar needs.
4. Then, operator submits the batches to the processor one by one.
5. All the jobs of one batch are executed together.

📌 Example: Payroll systems, Bank Statement Generation

## ⚠️ Limitations of Batch Operating Systems 

1. **Cannot Set Priorities**
   - All jobs are treated equally.
   - You can't mark a task as high or low priority.
   - Even urgent tasks must wait for earlier jobs to finish.

2. **May Lead to Starvation**
   - If a large batch of jobs is running, smaller or important jobs may wait too long.
   - This is called starvation — when a job doesn't get CPU time for a long time.

3. **CPU May Become Idle During I/O**
   - If a job is doing input/output work (like reading from a file), the CPU waits.
   - During this time, the CPU is not used — it stays idle.
   - This wastes processing time and reduces efficiency.

---

##  2. Time-Sharing Operating System

- Allows **multiple users to access the system at the same time**.
- The CPU works on each user's task for a short time, one after another.
- This quick switching is called **context switching**.
- It happens so fast that users feel like their program is running continuously.
- Helps in **better response time** and **efficient use of CPU**.
- Used in multi-user environments like servers.

📌 **Examples:** UNIX, Multics


---
## 3. Distributed Operating System

- A Distributed Operating System connects **multiple computers through a network.***
- The OS manages all the connected machines as if they are a single system.
- Users can run programs without knowing which computer in the network is handling the task.
- It allows for:
- Resource sharing (CPU, memory, storage, etc.)
- Load balancing (distributes tasks to avoid overloading one system)
- Improved performance, fault tolerance, and reliability

Example: LOCUS, Amoeba


---

## 4. 🚨 Real-Time Operating System (RTOS)

- Responds immediately to input or events.
- Used in systems where time is critical.

📌 Example: Medical devices, Air traffic control, Robots

---

## 4. Multiprogramming Operating System

- Increases CPU usage by keeping **multiple jobs in memory** at the same time.
- If one job is waiting for input/output (I/O), the CPU switches to another job.
- This way, the CPU **does not sit idle** and is always doing useful work.
- Uses **context switching** to move between processes.
- Only **one CPU** is used.

Summary:
- Single CPU
- Jobs loaded into memory together
- CPU switches only when a job goes to wait state (e.g., waiting for I/O)
- Reduces CPU idle time

---

## 5. Multitasking Operating System

- A **logical extension of multiprogramming**.
- Allows users to **run more than one task at the same time**.
- Tasks are switched quickly using **context switching and time sharing**.
- Only **one CPU**, but it gives the feel of doing many things at once.
- Improves **user responsiveness** and reduces idle time further.

Summary:
- Single CPU
- Supports multiple tasks
- Fast context switching
- CPU shares time among all tasks (time-sharing)
- Better user experience and responsiveness

---

## 6. Multiprocessing Operating System

- A system with **more than one CPU (processor)** in the same computer.
- All CPUs work together and **share the workload**.
- If one CPU fails, others can continue — this **increases reliability**.
- Can handle more tasks at once, so **throughput increases**.
- **Lesser process starvation**, since multiple CPUs handle more processes at the same time.

Summary:
- Multiple CPUs
- Increases performance and reliability
- One CPU can continue if another fails
- Better handling of processes
- Reduces waiting time for processes (less starvation)

---

## ✅ Summary Table

| OS Type              | Main Use                            | Example          |
|----------------------|--------------------------------------|------------------|
| Batch                | Runs jobs in bulk without interaction| Payroll systems  |
| Time-Sharing         | Multiple users at once               | UNIX             |
| Distributed          | Networked systems as one             | LOCUS            |
| Real-Time (RTOS)     | Immediate response                   | Medical devices  |
| Multi-User           | Multiple user accounts               | Linux, UNIX      |
| Multitasking         | Run many apps simultaneously         | Windows          |
| Mobile               | Smartphones and tablets              | Android, iOS     |


