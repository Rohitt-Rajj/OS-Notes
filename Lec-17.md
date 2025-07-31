# LEC-17: Conditional Variables and Semaphores for Thread Synchronization

---

## 1. Conditional Variable

- A **Conditional Variable** is a synchronization mechanism that allows a thread to **wait until a specific condition is met**.
- It is always used **along with a lock** (mutex).

### 🔄 How It Works:
1. A thread acquires the lock.
2. It checks a condition.
3. If the condition is false, it **waits** using the conditional variable.
4. While waiting, it **releases the lock** so other threads can make progress.
5. When another thread updates the condition and **signals**, the waiting thread wakes up.
6. The awakened thread **reacquires the lock** and resumes execution.

### ✅ Why Use Conditional Variables?
- To **avoid busy waiting** (where CPU cycles are wasted in checking the condition repeatedly).
- Helps achieve **better CPU efficiency**.
- **No contention** because waiting threads release the lock.

---

## 2. Semaphores

- A **semaphore** is a synchronization primitive that controls **access to shared resources**.
- It is represented by an **integer value**, which indicates the number of available resources.

### 🔹 Types of Semaphores:

#### a. Binary Semaphore (Value: 0 or 1)
- Also called a **mutex lock**.
- Used to allow **one thread at a time** to access a resource.

#### b. Counting Semaphore (Value: 0 to N)
- Can be used when there are **multiple instances** of a resource.
- Allows up to `N` threads to access the critical section **concurrently**.

### ✅ Characteristics:
- A **mutex** allows only one thread at a time.
- A **counting semaphore** allows **multiple threads** to access a **limited number** of instances.

---

### ⚙️ How Semaphore Works (wait & signal)

- `wait(S)`:
  - If the value of `S` > 0, decrement it and allow the thread to continue.
  - If `S <= 0`, the thread is **blocked** and placed in the **waiting queue**.
  - The thread's state becomes **Waiting** and CPU is given to another thread.

- `signal(S)`:
  - Increments the value of `S`.
  - If any thread is waiting in the queue, it is **woken up** using a `wakeup()` operation.
  - The woken thread is moved to the **Ready Queue**.

### 🔁 No Busy Waiting:
- Semaphores avoid busy waiting by blocking the thread **instead of looping**.
- Scheduler picks another process during that time.

---

## 🔃 Summary Table

| Feature               | Conditional Variable                          | Semaphore                          |
|-----------------------|-----------------------------------------------|-------------------------------------|
| Purpose               | Wait for a specific condition                 | Control access to shared resources  |
| Works with            | Must be used with a lock                      | Can be standalone                   |
| Avoids Busy Waiting   | ✅ Yes                                         | ✅ Yes                               |
| Blocking/Waiting      | Threads wait for a condition to be signaled  | Threads wait if resource not free   |
| Binary Type           | ❌ (not binary)                               | ✅ Binary Semaphore = mutex lock     |
| Counting Type         | ❌                                            | ✅ Counting Semaphore                |
| Thread Wakeup         | Uses signal/broadcast                        | Uses signal + wakeup operation      |

---

## ✅ Key Takeaways

- Use **conditional variables** when you want a thread to wait for some **event or condition**.
- Use **semaphores** when you want to **control the number of threads** that access shared resources.
- Both avoid **busy waiting** and improve **CPU efficiency**.

