# MUHAMMAD SYAKIR IZZ BIN SAMSUDIN
# 🚀 Parallel Computation of Mean for Large Numerical Datasets

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Stdlib Only](https://img.shields.io/badge/Dependencies-None-brightgreen)]()

> **ITT440 - Network Programming**  
> Individual Assignment: Parallel and Concurrent Programming  
---

## 📋 Project Information

| Field | Details |
|-------|---------|
| **Project Title** | Parallel Computation of Mean for Large Numerical Datasets |
| **Name** | MUHAMMAD SYAKIR IZZ BIN SAMSUDIN|
| **Student ID** | 2024274988 |
| **Class** |M3CS2554A|
| **Course** | ITT440 - Network Programming |
| **Lecturer** | SIR SHAHADAN BIN SAAD |

---

## 📌 Introduction

Effective numerical computation is crucial for machine learning, scientific computing, and data analysis in the big data age. When dataset sizes reach millions or billions of entries, traditional sequential programming becomes more inefficient since it uses a single CPU core to handle data one element at a time.

Although calculating the mean (average) of a big dataset is a basic statistical operation, performance can be significantly impacted by the method utilized. In order to calculate the mean of huge numerical datasets, this research examines three distinct programming paradigms: sequential, threading (concurrent), and multiprocessing (parallel). It also evaluates the execution performance of each paradigm.


---

## 🎯 Objectives

1.  To implement **sequential, concurrent (threading), and parallel (multiprocessing)** programming techniques
2.  To efficiently process **large-scale numerical datasets** (10M numbers)
3.  To **compare execution performance** across all three methods
4.  To understand the impact of Python's **Global Interpreter Lock (GIL)**
5.  To analyze **why certain methods outperform others** for CPU-bound tasks
6.  To demonstrate **workload distribution** across threads and processes

---

## 📊 Project Overview

This project develops a high-performance **Parallel Mean Calculator** with a beautiful GUI dashboard capable of:

- 📈 Computing statistical mean of **10+ million numbers**
- 🔄 Comparing **3 execution methods** in real-time
- 🎨 Displaying results in an **interactive GUI**
- 📊 Visualizing performance with **bar charts**
- 📁 Supporting **multiple data sources** (generate, manual, file)


---

## 🖥️ GUI Screenshots

### Tab 1: Data Setup
<img width="1915" height="835" alt="image" src="https://github.com/user-attachments/assets/08503d43-e676-44bd-9273-bbf64c49a4e8" />

### Tab 2: Preview Numbers
<img width="1918" height="986" alt="image" src="https://github.com/user-attachments/assets/56e9102f-c785-491c-803c-5f05d9f63efe" />

### Tab 3: Performance Results
<img width="1916" height="952" alt="image" src="https://github.com/user-attachments/assets/7bf6c4bf-e447-4d2a-b811-3eabe39be266" />

---

## 📊 Test Results

### Test Configuration


### Performance Results (Actual Output)

| Rank | Method | Time (s) | Speedup | Algorithm | Cores Used |
|:----:|--------|:--------:|:-------:|-----------|:-----------:|
| 🥇 | **Threading** | **0.0797** | **6.12×** | Built-in sum / 4 threads | 4 threads |
| 🥈 | Sequential | 0.4876 | 1.00× | Manual loop + variance | 1 core |
| 🥉 | Multiprocessing | 0.7490 | 0.65× | Built-in sum / 12 processes | 12 processes |

---
## 🔬 Algorithm Design
## Algorithm 1: Sequential Computation


    # ── PASS 1: Manual loop sum (slow Python bytecode) ──
    total = 0.0
    for x in data:          
        total += x          
    mean = total / n

    # ── PASS 2: Squared deviations (extra O(n) work) ──
    sq_dev = 0.0
    for x in data:          
        diff = x - mean
        sq_dev += diff * diff
    variance = sq_dev / n

    elapsed = time.perf_counter() - t0
    return mean, variance, elapsed

   ## Algorithm 2: Threading Computation
   def _thread_sum_worker(chunk: list, results: dict, idx: int):
    """Worker: Compute partial sum using C-speed built-in sum()"""
    results[idx] = sum(chunk)   # ✅ C implementation

def threaded_compute(data: list, num_threads: int) -> tuple:
    """
    Algorithm: Chunked data + built-in sum() per thread
    Time Complexity: O(n)
    Space Complexity: O(n) shared
    """
    n = len(data)
    chunk_size = math.ceil(n / num_threads)
    chunks = [data[i:i + chunk_size] for i in range(0, n, chunk_size)]

    t0 = time.perf_counter()
    results = {}
    threads = []

    # Create and start threads
    for i, chunk in enumerate(chunks):
        t = threading.Thread(
            target=_thread_sum_worker,
            args=(chunk, results, i)
        )
        threads.append(t)
        t.start()

    # Wait for all threads to complete
    for t in threads:
        t.join()

    # Combine partial results
    total = sum(results.values())
    mean = total / n
    elapsed = time.perf_counter() - t0
    return mean, elapsed

    
 ## Algorithm 3: Multiprocessing Computation


## Demonstrate Video



## Counclusion
