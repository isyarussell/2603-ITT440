# 🃏Solitaire Parallel Programming Simulator
- Name : 'Aina Maisarah bt Mohd Shuhaimi
- Student ID :2024230508
- Course code : ITT440

## Abstract
This project presents the development of a Python-based simulation program designed to compare the performance of sequential, concurrent, and parallel programming techniques. The application simulates a large volume of solitaire game outcomes using probabilistic models.  

The program implements threading as a concurrent technique and multiprocessing as a parallel technique. Performance is evaluated based on execution time when processing millions of simulated games. The results demonstrate that multiprocessing achieves the best performance for CPU-bound tasks, while threading is limited due to Python’s Global Interpreter Lock (GIL).  

## Introduction
With the advancement of multi-core processors, parallel programming has become essential for improving computational efficiency. Different programming techniques such as sequential execution, threading, and multiprocessing offer various levels of performance depending on the nature of the task.

This project aims to develop a simulation system that processes a large volume of data in the form of solitaire game outcomes. The program compares execution performance using three approaches:

- Sequential programming
- Concurrent programming (threading)
- Parallel programming (multiprocessing)

## Objectives

- To develop a Python program that simulates a large number of solitaire games
- To implement concurrent programming using threading
- To implement parallel programming using multiprocessing
- To compare execution performance between different techniques
- To analyze the effect of CPU cores on program efficiency
  
## System Requirements
- Operating System: Kali Linux
- Python Version: Python 3.8 or higher
- CPU: 4 cores
- RAM: Minimum 4GB


## Installation Steps
Step 1: Install Python
sudo apt update  
sudo apt install python3  

## ▶️ How to Run the Program  
1. Open terminal  
2. Navigate to file location  
Run:
phyton ITT440.py

## 🎮 Program Features

### 🎯 Game Types

| No. | Game Type  | Win Rate |
|-----|-----------|---------|
| 1   | Klondike  | 45%     |
| 2   | Spider    | 35%     |
| 3   | Freecell  | 55%     |
| 4   | Pyramid   | 30%     |
| 5   | Tripeaks  | 40%     |

### 📊 Difficulty Levels
| Level  | Number of Games |
| ------ | --------------- |
| Easy   | 10,000,000      |
| Medium | 20,000,000      |
| Hard   | 30,000,000      |
| Expert | 40,000,000      |
| Master | 50,000,000      |


## Sample Input


## Sample Ouput

## Sample Output Files

## Sample Graph 

## Conclusion
This project successfully demonstrates the differences between sequential, concurrent and parallel programming.

Multiprocessing is proven to be the most efficient approach for handling large-scale computational tasks, while threading is less effective due to inherent limitations in Python.

The program fulfills all assignment requirements by processing a large volume of data and clearly demonstrating performance differences between execution methods.
