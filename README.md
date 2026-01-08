# CPU Scheduling Simulator (C++)

## Overview
This project is a C++ simulator for common CPU scheduling algorithms used in Operating Systems.
It demonstrates and compares the behavior of different scheduling strategies under various input scenarios, while calculating key performance metrics.

The simulator prints a simple textual Gantt chart and computes scheduling statistics to help analyze algorithm efficiency and fairness.

## Implemented Algorithms
- First Come First Serve (FCFS)
- Shortest Remaining Time (SRT)
- Round Robin (RR)

## Performance Metrics
- Waiting Time
- Turnaround Time
- CPU Utilization
- Response Time (tracked in the PCB model)

## Project Structure
cpu-scheduling/
├── docs/
│   ├── examples.md
│   └── test-cases.md
├── input/
│   └── process.txt
├── src/
│   ├── main.cpp
│   ├── algorithms.h
│   ├── handle.h
│   └── PCB.h
├── .gitignore
└── README.md

## Input Format
The input file is located at input/process.txt and follows this format:

1. Quantum (used for Round Robin)
2. Context switch time
3. Each following line represents a process:
process_id arrival_time cpu_burst

Example:
4
8
1 0 10
2 2 5
3 4 8
4 6 6
5 8 7

## How to Run
1. Clone the repository.
2. Make sure a C++ compiler is installed (e.g., g++).
3. Compile the project using:
g++ -std=c++17 -O2 -o cpu-scheduling src/main.cpp
4. Run the program:
./cpu-scheduling

The simulator will execute all scheduling algorithms sequentially and print:
- Gantt chart output
- Per-process statistics
- Overall performance metrics

## Testing
- Manual testing was performed using predefined scenarios.
- Test cases are documented in docs/test-cases.md.
- Example input scenarios are available in docs/examples.md.
- Edge cases such as tie conditions and small quantum values are included.

## Known Limitations
- Input validation is limited (e.g., negative burst times are not explicitly handled).
- Number of processes is currently fixed in the code.
- Output is text-based with no graphical visualization.

## Future Improvements
- Add automated unit tests for metric calculations.
- Improve input validation and error handling.
- Allow dynamic number of processes.
- Add optional Gantt chart visualization or result export.

## Purpose
This project was developed as part of an Operating Systems course and demonstrates:
- Understanding of CPU scheduling concepts
- Algorithm analysis and comparison
- System behavior evaluation and manual testing practices
