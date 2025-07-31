# LEC-16: Critical Section Problem and How to Address It

## 1. Process Synchronization

**Definition:**  
Process synchronization is a set of techniques used to control the order in which multiple processes or threads access shared resources, ensuring data consistency and correctness.

**Explanation:**  
When several threads or processes run at the same time and share data, synchronization ensures they don't interfere with each other and cause errors.

---

## 2. Critical Section (C.S)

**Definition:**  
The critical section is a segment of code where a process or thread accesses shared resources like variables or files and performs operations that may change those resources.

**Explanation:**  
Because multiple threads may run concurrently, one thread in its critical section could be interrupted, leading to inconsistent or incorrect data if another thread accesses the same resource simultaneously.

**Example:**  
Two threads trying to update the same bank account balance at the same time might overwrite each other's updates, causing the wrong final amount.

---

## 3. Race Condition

**Definition:**  
A race condition occurs when two or more threads access shared data and try to modify it at the same time, causing unexpected or incorrect results depending on the timing of their execution.

**Explanation:**  
Since thread scheduling can switch between tasks unpredictably, you cannot guarantee the order in which threads access the shared data.

**Example:**  
If `count = 5` and two threads increment it simultaneously, both might read `5`, add `1`, and write back `6`, resulting in `6` instead of the correct `7`.

---

## 4. Solutions to Race Condition

**Definitions:**  
- **Atomic operations:** Operations that happen in a single step without interruption.  
- **Mutual exclusion (locks):** Mechanisms such as locks that ensure only one thread can enter the critical section at a time.  
- **Semaphores:** More sophisticated synchronization tools that control access to shared resources.

**Explanation:**  
By making critical code atomic or by using locks/semaphores to prevent multiple threads from entering the critical section simultaneously, race conditions can be avoided.

---

## 5. Simple Flag Variable

**Definition:**  
A flag variable is a simple Boolean variable used to indicate whether a resource is in use.

**Explanation:**  
Using a simple flag to control access is not reliable because two threads may check the flag at the same time and both proceed, causing a race condition.

---

## 6. Peterson’s Solution

**Definition:**  
Peterson’s solution is a software algorithm designed to ensure mutual exclusion and prevent race conditions between exactly two processes or threads.

**Explanation:**  
It uses two flags and a turn variable to regulate who can enter the critical section, but it works only for two threads and does not scale to many.

---

## 7. Mutex (Locks)

**Definition:**  
A mutex (short for mutual exclusion) or lock is a synchronization tool that allows only one thread or process to access the critical section at a time.

**Explanation:**  
Threads must acquire the lock before entering the critical section and release it afterward, forcing others to wait if the lock is held.

**Disadvantages:**  
- Contention: Threads wait while the lock is held, which can cause delays.  
- Deadlocks: Threads may get stuck waiting for locks held by each other forever.  
- Debugging difficulties: Bugs due to locks may be timing-dependent and hard to reproduce.  
- Starvation: High-priority threads might be blocked indefinitely.


