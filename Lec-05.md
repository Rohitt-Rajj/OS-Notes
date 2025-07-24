# System Calls in Operating System

## What is a System Call?

- A **system call** is a mechanism used by **user programs** to request services from the **operating system kernel**.
- Since user programs run in **user mode**, they **do not have permission** to directly:
  - Access hardware devices (keyboard, printer, disk)
  - Allocate or free memory
  - Create or manage processes
  - Perform file operations

- A **system call is the only way** for a program to **enter kernel mode** from user mode to perform such operations.

---

## How Do Applications Interact with the Kernel?

Applications interact with the kernel **indirectly** using system calls. Here's how it works:

1. The **user program** issues a system call (like `open`, `read`, `exec`).
2. The **system call interface** in the OS **traps** (interrupts) the normal flow and switches the CPU from **user mode to kernel mode**.
3. The kernel **performs the requested task**.
4. Control returns back to the **user program**.

---

# Types of System Calls in Operating System

System calls are grouped based on the type of operations they perform. Below are the major categories:

---

## 1. Process Control

These system calls manage **process creation, execution, and termination**.

- `end`, `abort` – Terminate a process
- `load`, `execute` – Load a program into memory and run it
- `create process`, `terminate process` – Start or stop processes
- `get process attributes`, `set process attributes` – Access or modify process info
- `wait for time` – Make a process wait for a specific duration
- `wait event`, `signal event` – Synchronize processes
- `allocate and free memory` – Manage memory used by processes

---

## 2. File Management

Used to perform **file operations** such as creation, reading, writing, and deletion.

- `create file`, `delete file` – Manage file lifecycle
- `open`, `close` – Access or close a file
- `read`, `write`, `reposition` – Perform file I/O
- `get file attributes`, `set file attributes` – Access or update metadata (like file size, permissions)

---

## 3. Device Management

These system calls handle **input/output devices** like printers, disks, keyboards, etc.

- `request device`, `release device` – Reserve or free a device for use
- `read`, `write`, `reposition` – Device I/O operations
- `get device attributes`, `set device attributes` – Access or change device configurations
- `logically attach or detach devices` – Manage connections with devices

---

## 4. Information Maintenance

Used to **get or set system-related information** such as time, date, system stats, and attributes.

- `get time or date`, `set time or date` – Manage system clock
- `get system data`, `set system data` – Read or update OS configuration
- `get process, file, or device attributes` – View details about system objects
- `set process, file, or device attributes` – Modify attributes or permissions

---

## 5. Communication Management

These system calls are used for **inter-process communication (IPC)**, whether local or remote.

- `create`, `delete communication connection` – Setup or remove communication channels
- `send`, `receive messages` – Exchange information between processes
- `transfer status information` – Share progress or results between processes
- `attach or detach remote devices` – Manage remote access or connections

---

## Summary Table

| Category               | Purpose                                  | Common Actions                          |
|------------------------|------------------------------------------|------------------------------------------|
| Process Control        | Manage processes                         | Create, terminate, wait, allocate memory |
| File Management        | Handle files                             | Open, read, write, close, delete         |
| Device Management      | Control I/O devices                      | Request, release, read, attach           |
| Information Maintenance| System data access and modification     | Get/set time, attributes, config         |
| Communication          | Data exchange between processes          | Send, receive, connect, detach           |


# Examples of Windows & Unix System Calls

System calls vary across different operating systems. Here's a comparison of common system calls in **Windows** and **Unix/Linux** grouped by category.

---

## 1. Process Control

| Category         | Windows Functions                   | Unix/Linux Functions     |
|------------------|-------------------------------------|---------------------------|
| Create Process   | `CreateProcess()`                   | `fork()`                  |
| Exit Process     | `ExitProcess()`                     | `exit()`                  |
| Wait for Process | `WaitForSingleObject()`             | `wait()`                  |

---

## 2. File Management

| Category                  | Windows Functions                               | Unix/Linux Functions        |
|---------------------------|-------------------------------------------------|------------------------------|
| Create File               | `CreateFile()`                                  | `open()`                     |
| Read File                 | `ReadFile()`                                    | `read()`                     |
| Write File                | `WriteFile()`                                   | `write()`                    |
| Close File                | `CloseHandle()`                                 | `close()`                    |
| File Permissions (Security)| `SetFileSecurity()`<br>`InitializeSecurityDescriptor()`<br>`SetSecurityDescriptorGroup()` | `chmod()`<br>`umask()`<br>`chown()` |

---

## 3. Device Management

| Category      | Windows Functions                    | Unix/Linux Functions   |
|---------------|--------------------------------------|-------------------------|
| I/O Control   | `SetConsoleMode()`                   | `ioctl()`               |
| Read Device   | `ReadConsole()`                      | `read()`                |
| Write Device  | `WriteConsole()`                     | `write()`               |

---

## 4. Information Management

| Category               | Windows Functions            | Unix/Linux Functions   |
|------------------------|------------------------------|-------------------------|
| Get Process ID         | `GetCurrentProcessID()`      | `getpid()`              |
| Set Timer              | `SetTimer()`                 | `alarm()`               |
| Sleep / Wait           | `Sleep()`                    | `sleep()`               |

---

## 5. Communication

| Category               | Windows Functions                  | Unix/Linux Functions         |
|------------------------|------------------------------------|-------------------------------|
| Pipes                  | `CreatePipe()`                     | `pipe()`                      |
| Shared Memory          | `CreateFileMapping()`<br>`MapViewOfFile()` | `shmget()`<br>`mmap()`   |

---

## Summary

- **Windows** system calls are implemented using functions in the **Windows API**, which internally interact with the Windows kernel.
- **Unix/Linux** system calls are more direct and follow **POSIX standards**.


