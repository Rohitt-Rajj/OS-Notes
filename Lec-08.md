# Storage Devices Basics

Computers use various types of memory to store and access data during processing. These memories differ in size, speed, cost, and volatility.

---

## Different Types of Memory in a Computer System

### 1. Register
- **Smallest and fastest** memory unit.
- Located **inside the CPU** itself.
- Used to **quickly accept, store, and transfer** data and instructions being used **immediately** by the CPU.
- A register may store:
  - Instructions
  - Memory addresses
  - Temporary data
  - Bit sequences or characters
- **Very limited in size** but crucial for instruction execution.

---

### 2. Cache Memory
- High-speed memory **between the CPU and RAM**.
- Temporarily stores **frequently accessed instructions and data**.
- Helps reduce the time CPU takes to fetch data from main memory.
- Improves **overall system performance**.
- Usually divided into:
  - **L1 Cache**: Fastest, closest to CPU core
  - **L2 Cache**
  - **L3 Cache**: Larger but slightly slower

---

### 3. Main Memory (RAM)
- Known as **Primary Memory** or **Main Memory**.
- Stores **currently active programs and data**.
- Directly accessible by the CPU.
- **Volatile**: Data is lost when the system is powered off.
- Faster than secondary memory but slower than cache.

---

### 4. Secondary Memory
- Used for **permanent storage** of data and software.
- **Non-volatile**: Retains data even when the computer is powered off.
- Examples include:
  - Hard Disk Drives (HDD)
  - Solid State Drives (SSD)
  - USB Flash Drives
  - CDs/DVDs
- Slower than primary memory but **much larger and cheaper**.

---

## Comparison of Storage Types

### 1. Cost
- **Primary storage** (Registers, Cache, RAM) is **more expensive**.
- **Registers** are the **most expensive**, due to high-performance semiconductors and manufacturing complexity.
- **Secondary storage** is **cheaper**, making it suitable for long-term data storage.

---

### 2. Access Speed
- **Primary memory** has a **higher access speed** than secondary memory.
- Speed hierarchy:

---

### 3. Storage Size
- **Registers** have the **smallest capacity**.
- **Cache** is small but larger than registers.
- **RAM** is larger than cache.
- **Secondary memory** (e.g., HDDs, SSDs) provides the **largest storage space**.

---

### 4. Volatility
- **Primary memory** (Registers, Cache, RAM) is **volatile**, meaning data is lost when power is turned off.
- **Secondary memory** is **non-volatile**, and retains data without power.

---

## Summary Table

| Feature         | Register | Cache Memory | Main Memory (RAM) | Secondary Memory |
|-----------------|----------|--------------|-------------------|------------------|
| Speed           | Fastest  | Very Fast    | Fast              | Slow             |
| Size            | Very Small | Small      | Medium            | Very Large       |
| Cost            | Highest  | High         | Medium            | Low              |
| Volatile        | Yes      | Yes          | Yes               | No               |
| Location        | CPU      | Near CPU     | Motherboard       | Internal/External|
| Usage           | Immediate data & instructions | Frequently accessed data | Running programs | Permanent storage |

---



## Memory Hierarchy Table

| Memory Type       | Description                   |
|-------------------|-------------------------------|
| Register          | Fastest, smallest, in CPU     |
| Cache             | Very fast, stores recent data |
| RAM               | Fast, stores active programs  |
| Secondary Memory  | Large, permanent storage      |

---

**Access Speed:**  
`Register > Cache > RAM > HDD/SSD`

**Storage Capacity:**  
`HDD/SSD > RAM > Cache > Register`
