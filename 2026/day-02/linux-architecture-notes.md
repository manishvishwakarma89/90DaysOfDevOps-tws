## Linux Internals – DevOps Foundation
This document covers the core Linux concepts required for troubleshooting and system management in production environments.
1. Core Components of Linux
   Kernel
The Linux kernel is the main component of a Linux operating system (OS) and is the core interface between a computer’s hardware and its processes. It communicates between the 2, managing resources as efficiently as possible.
The kernel is so named because—like a seed inside a hard shell—it exists within the OS and controls all the major functions of the hardware, whether it’s a phone, laptop, server, or any other kind of computer.
What the kernel does
The kernel has 4 jobs:
1.	Memory management: Keep track of how much memory is used to store what, and where
2.	Process management: Determine which processes can use the central processing unit (CPU), when, and for how long
3.	Device drivers: Act as mediator/interpreter between the hardware and processes
4.	System calls and security: Receive requests for service from the processes

| **State** | **Full Form**                  | **Meaning**                                                        | **Real Scenario Example**                        |
| --------- | ------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------ |
| **R**     | Running                        | Process is actively executing on CPU or ready to run               | `nginx` handling a web request                   |
| **S**     | Sleeping (Interruptible Sleep) | Waiting for a resource (disk, network, input)                      | App waiting for DB response                      |
| **T**     | Stopped                        | Process is paused/stopped manually (e.g., via signal)              | Pressed `Ctrl+Z` in terminal                     |
| **Z**     | Zombie                         | Process finished execution but parent hasn’t collected exit status | Child process ended, parent didn’t call `wait()` |

Why Process States Matter
| **Issue**                    | **Related Process State(s)**                | **What It Indicates**                           | **What You Check as DevOps Engineer**                   |                           |
| ---------------------------- | ------------------------------------------- | ----------------------------------------------- | ------------------------------------------------------- | ------------------------- |
| **High CPU Usage**           | `R` (Running)                               | Process is actively consuming CPU               | `top`, `htop`, `ps -eo %cpu --sort=-%cpu`               |                           |
| **Memory Leaks**             | Usually `S` or `R`                          | Process memory keeps increasing without release | `top`, `ps aux --sort=-%mem`, `free -m`, check OOM logs |                           |
| **Stuck / Unresponsive App** | `S` (Sleeping), `D` (Uninterruptible Sleep) | Waiting for I/O, disk, network, or DB           | `ps -ef`, `strace -p <pid>`, check disk/network latency |                           |
| **Zombie Process**           | `Z` (Zombie)                                | Process finished but parent hasn’t cleaned it   | `ps -el                                                 | grep Z`, check parent PID |
| **Orphan Process**           | Any state (adopted by PID 1)                | Parent died before child                        | `ps -ef`, verify PPID = 1                               |                           |

