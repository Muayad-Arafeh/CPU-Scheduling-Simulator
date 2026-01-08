# Manual Test Cases – CPU Scheduling Simulator

This document describes manual test cases used to validate the behavior of the CPU scheduling algorithms implemented in this project.

---

## TC-01: FCFS Basic Scheduling
**Description:** Verify that processes are executed in order of arrival time.  
**Input:** Processes with increasing arrival times.  
**Expected Result:**  
- Processes are executed in arrival order.  
- Waiting time and turnaround time are calculated correctly.

---

## TC-02: FCFS with Context Switch
**Description:** Verify correct time calculation when context switch time is enabled.  
**Input:** Context switch time > 0.  
**Expected Result:**  
- Total execution time increases by the context switch duration after each process.  
- CPU utilization reflects context switch overhead.

---

## TC-03: Shortest Remaining Time Preemption
**Description:** Verify preemption when a new process arrives with a shorter remaining burst time.  
**Input:**  
- A long-running process starts execution.  
- A shorter process arrives while it is running.  
**Expected Result:**  
- The currently running process is preempted.  
- The process with the shortest remaining time executes next.

---

## TC-04: SRT Completion Handling
**Description:** Verify correct calculation when a process finishes execution in SRT.  
**Input:** Multiple processes with different burst times.  
**Expected Result:**  
- Finish time, waiting time, and turnaround time are calculated correctly.

---

## TC-05: Round Robin Basic Execution
**Description:** Verify Round Robin scheduling with a valid quantum.  
**Input:** Quantum < CPU burst time of some processes.  
**Expected Result:**  
- Processes execute for at most one quantum at a time.  
- Remaining burst time is updated correctly.

---

## TC-06: Round Robin Quantum Larger Than Burst
**Description:** Verify behavior when quantum is larger than the remaining burst time.  
**Input:** Quantum > remaining burst.  
**Expected Result:**  
- The process completes without preemption.  
- Correct finish and turnaround times are recorded.

---

## TC-07: Round Robin Small Quantum (Edge Case)
**Description:** Verify behavior with very small quantum (e.g., quantum = 1).  
**Input:** Quantum = 1.  
**Expected Result:**  
- Frequent context switching occurs.  
- Remaining burst time decreases correctly until completion.

---

## TC-08: Tie Case – Same Arrival Time
**Description:** Verify deterministic behavior when multiple processes have the same arrival time.  
**Input:** Two or more processes with identical arrival times.  
**Expected Result:**  
- A consistent tie-breaking rule is applied (e.g., process ID order).

---

## TC-09: Tie Case – Same Burst Time
**Description:** Verify scheduling behavior when multiple processes have equal burst times.  
**Input:** Two or more processes with identical burst times.  
**Expected Result:**  
- Scheduling remains stable and consistent.

---

## TC-10: Input File Validation (Known Limitation)
**Description:** Verify behavior when invalid input is provided.  
**Input:** Negative or zero CPU burst time.  
**Expected Result:**  
- Input validation is not currently enforced.  
- Behavior is undefined (documented as a known limitation).
