# Operating Systems – Week 10: Thread and Process Exercises

**Course:** Operating Systems  
**Topics:** Threading, Multiprocessing, and Amdahl’s Law  

This repository contains **three fundamental implementations** and an **Amdahl’s Law calculator**, prepared to reinforce the concepts covered in the **Week 10 lecture** of the Operating Systems course.

---

## 📂 Contents and Explanations

### 1. Multithreading (Threading)
**File:** `1_coklu_programlama.py`

This application simulates the concept of **concurrency** on a single CPU. Two functions are executed simultaneously using Python’s `threading` library.

**Observation:**  
Since the operating system rapidly switches the CPU between threads, the output appears in an interleaved and non-deterministic order.

**Theoretical Context:**  
Threads share the same process resources (code, data, and files). This approach improves performance, especially for **I/O-bound operations**.

---

### 2. Multiprocessing
**File:** `2_coklu_islemci.py`

This application demonstrates **parallelism** by utilizing the power of modern multi-core systems through Python’s `multiprocessing` library.

**Observation:**  
Each process is assigned a unique **PID (Process ID)** by the operating system. This confirms that processes run in **separate memory spaces** and can execute simultaneously on different CPU cores.

**Theoretical Context:**  
In multi-core systems, each core is treated as an independent CPU by the operating system, enabling true parallel execution.

---

### 3. Comparison: Thread vs Process
**File:** `3_karsilastirma.py`

This program analyzes the structural differences between **threads and processes** by examining **Process IDs (PID)** and **Thread IDs**.

**Result:**  
- In threading, all threads share the same PID (shared resources).  
- In multiprocessing, each process has a distinct PID (isolated memory).

**Inference:**  
Creating a process is more resource-intensive than creating a thread, but it provides full memory isolation.

---

### 4. Amdahl’s Law Calculator
**File:** `4_amdahl_yasasi.py`

This program calculates the **maximum theoretical speedup** achievable when transitioning to a multi-core system.

**Formula Used:**
Speedup ≤ 1 / (S + ((1 - S) / N))


Where:
- **S** = Fraction of serial (non-parallelizable) code  
- **N** = Number of CPU cores  

**Note:**  
According to Amdahl’s Law, even if the number of cores increases indefinitely, the overall speedup is always limited by the serial portion of the program.

---

## 🚀 How to Run

Make sure **Python** is installed on your system. Open a terminal or command prompt and navigate to the directory containing the files:

# To run the threading example:
python 1_coklu_programlama.py

# To run the Amdahl’s Law calculator:
python 4_amdahl_yasasi.py


