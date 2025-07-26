#  CPU Scheduling | SJF | Priority | Round Robin

---

## 🧠 1. Shortest Job First (SJF)

### SJF – Non-Preemptive

- Process with the **smallest Burst Time (BT)** is selected first.
- Once CPU is assigned, the process runs till completion.
- Requires **prior knowledge or estimation** of BT, which is often **inaccurate or impossible**.

#### 🔻 Issues:
- Suffers from **convoy effect**: if the first process has a long BT, others must wait.
- May cause **starvation** for long jobs.
- **Selection criteria**: `AT + BT`

---

### SJF – Preemptive (Also called Shortest Remaining Time First - SRTF)

- Process with the **shortest remaining BT** gets CPU.
- If a new process arrives with a **shorter BT**, it **preempts** the current one.

#### ✅ Benefits:
- Less starvation compared to non-preemptive SJF.
- No convoy effect.
- Gives **minimum average waiting time** in many scenarios.

---

## 🎯 2. Priority Scheduling

### Priority – Non-Preemptive

- Each process is assigned a **priority** at the time of creation.
- The process with the **highest priority** (lowest number) is executed first.
- **SJF is a special case of priority scheduling** where priority is inversely proportional to BT.

### Priority – Preemptive

- If a new process arrives with a **higher priority** than the current one, it **preempts** it.

#### ⚠️ Problem:
- May cause **indefinite starvation** of low-priority processes.

#### ✅ Solution: Ageing
- Gradually **increase priority** of long-waiting processes.
- Example: Increase priority by 1 every 15 minutes.

---

## 🔁 3. Round Robin (RR) Scheduling

- Most **widely used** CPU scheduling algorithm.
- Like FCFS but **preemptive**, designed for **time-sharing systems**.

### Key Features:
- Each process is given a **fixed time quantum (TQ)**.
- If the process does not finish within TQ, it is **preempted** and moved to the end of the ready queue.
- CPU scheduling decision is based on `AT + TQ`, **not on BT**.

### ✅ Advantages:
- No starvation.
- No convoy effect.
- Easy to implement.
- Good responsiveness for all processes.

### ⚠️ Trade-Off:
- If **TQ is too small**: too many context switches (high overhead)
- If **TQ is too large**: behaves like FCFS

---

## 📊 Summary Table

| Algorithm           | Preemptive | BT Required | Starvation Risk | Convoy Effect | Fairness       |
|---------------------|------------|-------------|------------------|----------------|----------------|
| FCFS                | No         | ❌           | High             | Yes            | Low            |
| SJF (Non-Preemptive)| No         | ✅           | High             | Yes            | Low            |
| SJF (Preemptive)    | Yes        | ✅           | Moderate         | No             | Medium         |
| Priority (Non-Pre)  | No         | ❌           | High             | Possible       | Low            |
| Priority (Preempt)  | Yes        | ❌           | High             | Possible       | Low (unless ageing) |
| Round Robin         | Yes        | ❌           | Very Low         | No             | High           |

---

## ✅ Terms Reminder:

- **BT** = Burst Time  
- **AT** = Arrival Time  
- **TQ** = Time Quantum  
- **WT** = Waiting Time  
- **TAT** = Turnaround Time

