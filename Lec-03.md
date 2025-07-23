## Multi-Tasking vs Multi-Threading

**Program:** A Program is an executable file which contains a certain set of instructions written
to complete the specific job or operation on your computer.
• It’s a compiled code. Ready to be executed. <br>
• Stored in Disk

## Process in Operating System

- A process is a **program in execution**.
- When a program runs, it becomes a process.
- The OS creates and manages the process.

### Difference between Program and Process:

- **Program**: Passive file stored on disk (e.g., .exe, .py).
- **Process**: Active entity that is running, using CPU, memory, and other resources.

### Key Features of a Process:

- Has its own memory space
- Executes instructions step by step
- Can be in different states (running, waiting, etc.)
- May create other processes (called child processes)

### Example:

- You click on Chrome → Program becomes a Process
- OS allocates memory, opens files, assigns CPU time

### Note:

- One program can create multiple processes.
- Each process is independent and managed by the OS.

## Thread in Operating System

- A thread is the **smallest unit of execution** in a process.
- A single process can have **multiple threads** running at the same time.
- All threads in a process **share the same memory and resources**, but each thread runs independently.

### Key Points:

- Threads help in performing **multiple tasks at once** inside a single process.
- Threads share:
  - Code section
  - Data section
  - Open files
- Each thread has:
  - Its own program counter
  - Stack
  - Registers

### Advantages of Using Threads:

- **Faster context switching** than processes
- **Less memory usage** (shared memory)
- **Improved performance** in multi-core systems
- Useful in programs like web browsers, servers, games, etc.

### Example:

- In a browser:
  - One thread loads a web page
  - Another plays a video
  - Another handles user input

All these threads run **within the same process** (the browser).

### Note:

- Threads are also called **lightweight processes**.
- Errors in one thread can affect others because they share the same memory.

## Multitasking vs Multithreading in Operating System

### Multitasking

- Allows **multiple processes** to run at the same time.
- Each task (process) has its **own memory space**.
- Handled by the Operating System.
- Heavier on system resources.
- Example: You can run a browser, music player, and text editor at the same time.

### Multithreading
- A process is divided into several different sub-tasks called as threads, which has its own path of execution. This concept is called as multithreading.
- Allows **multiple threads** to run within a single process.
- Threads share the **same memory space**.
- Handled by the application/program.
- Uses fewer resources than multitasking.
- Example: A web browser can:
  - Load pages in one thread
  - Play videos in another
  - Respond to clicks in another

### Key Differences:

| Feature            | Multitasking                         | Multithreading                            |
|--------------------|--------------------------------------|--------------------------------------------|
| Unit of execution  | Process                              | Thread                                     |
| Memory             | Each process has separate memory     | Threads share same memory                  |
| Speed              | Slower (heavier context switch)      | Faster (lightweight switching)             |
| Resource usage     | More                                 | Less                                       |
| Isolation          | More secure (processes are isolated) | Less secure (threads can affect each other)|
| Example            | Browser + Music Player               | Tabs inside one browser                    |

## Thread Scheduling

- Thread scheduling is the process of selecting which thread should run next.
- Threads are scheduled for execution based on their priority. 
- Even though threads are executing within the runtime, all threads are assigned processor time slices by the operating system.

- It is used when a process has multiple threads running in parallel.
- The OS uses thread scheduling to share CPU time fairly and efficiently among threads.

### Types of Thread Scheduling:
1. **Preemptive**: OS can interrupt and switch threads at any time.
2. **Cooperative**: Thread runs until it yields control voluntarily.

---

## Difference Between Thread Context Switching and Process Context Switching

| Feature                 | Thread Context Switching                     | Process Context Switching                        |
|-------------------------|-----------------------------------------------|--------------------------------------------------|
| Unit Switched           | Thread (same process)                        | Entire process                                   |
| Speed                   | Faster                                        | Slower                                           |
| Memory Switching        | Not required (shared memory)                 | Required (separate memory for each process)      |
| Overhead                | Low                                           | High                                             |
| Example                 | Switching between tabs in a browser          | Switching from a browser to a text editor        |
| Controlled By           | OS Thread Scheduler                          | OS Process Scheduler                             |

### Note:
- Thread switching is **lightweight** because threads share resources.
- Process switching is **heavier** because each process is isolated and requires full context change.
