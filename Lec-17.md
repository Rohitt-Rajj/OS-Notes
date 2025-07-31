# LEC-17: Conditional Variables and Semaphores for Thread Synchronization

## 1. Conditional Variable

**Definition:**  
A *conditional variable* is a synchronization tool that allows a thread to wait (sleep) until a specific condition is true or an event occurs. It always works together with a lock (mutex).

**Explanation:**  
A thread can only enter a waiting state on a conditional variable if it first acquires the lock. When the thread waits, it *releases* the lock and goes to sleep until another thread signals that the condition is met. After being notified, the waiting thread wakes up, re-acquires the lock immediately, and continues execution. This avoids the problem of *busy waiting*, where a thread wastes CPU cycles repeatedly checking a condition.

**Why use conditional variables?**  
- To wait efficiently without using CPU cycles unnecessarily (no busy waiting).  
- To synchronize threads based on certain conditions or events.

**Example:**  
Imagine a producer-consumer scenario where the consumer waits until the producer has placed an item in a shared buffer. The consumer thread waits on a conditional variable, releasing the lock, until the producer signals that an item is available. Then the consumer wakes up, acquires the lock, and processes the item.

---

## 2. Semaphores

**Definition:**  
A *semaphore* is a synchronization method that uses an integer value to control access to a finite number of resources. It is used to allow multiple threads to manage shared resources safely.

**Types:**
- **Binary Semaphore:** Value is either 0 or 1. It behaves like a mutex lock, allowing one thread at a time.
- **Counting Semaphore:** Can have a range of integer values, representing how many instances of a resource are available.

**Explanation:**  
Multiple threads can enter their critical sections concurrently, up to the number of available resources counted by the semaphore. Semaphores help coordinate access to limited resources, unlike mutexes which control exclusive access to a single resource.

To avoid busy waiting:
- When a thread calls `wait()` (or P operation) on a semaphore whose value is zero or less, it does not spin in a loop but *blocks* itself and is placed in a waiting queue.
- When another thread executes `signal()` (or V operation), it wakes up one waiting thread, which then becomes ready to run.

**Example:**

Imagine a printer queue shared by several threads but only 3 printers are available. A counting semaphore with initial value 3 can be used. Each time a thread wants to print:


---

**Summary:**  
- *Conditional variables* let threads sleep efficiently, waiting for a condition to become true, working alongside locks.  
- *Semaphores* manage access to a finite number of shared resources, allowing multiple threads to proceed up to the resource limit.  
- Both prevent busy waiting by blocking and waking threads appropriately, ensuring efficient CPU usage in thread synchronization.

