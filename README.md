# Operating System Simulation

## Overview
This project is a simulation of an operating system that creates a virtual machine capable of compiling and executing various multi-programming jobs. It implements concepts such as:
- **Paging** for memory management
- **Virtual Memory** allocation
- **Error Handling** for various execution scenarios

## Features
- **Job Scheduling**: Supports multiple jobs and manages execution efficiently.
- **Memory Management**: Implements paging and virtual memory.
- **Error Handling**: Detects and reports errors like opcode errors, operand errors, invalid page faults, time limit exceeded, and line limit exceeded.
- **File Handling**: Reads input jobs from a file (`input.txt`) and writes output to `output.txt`.
- **Instruction Execution**: Supports a set of machine-level instructions like `GD`, `PD`, `CR`, `SR`, `LR`, and `BT`.

## How It Works
1. **Job Initialization**:
   - Reads input jobs from `input.txt`
   - Allocates memory pages
   - Sets up job control blocks
2. **Execution Cycle**:
   - Fetches and decodes instructions
   - Executes operations (Read, Write, Load, Store, Compare, Branch, Halt)
   - Handles page faults dynamically
3. **Termination & Logging**:
   - Detects errors and terminates jobs accordingly
   - Logs execution details to `output.txt`

### Input File Format (`input.txt`)
The input file should contain job instructions following this format:
```
$AMJ <Job ID> <TTL> <TLL>
<Job Instructions>
$DTA
<Data Section>
$END
```

### Output File (`output.txt`)
After execution, results and error logs will be written to `output.txt`.

## Error Codes & Handling
| Error Code | Description |
|------------|-------------|
| 0 | No Error – Normal termination |
| 1 | Out of Data Error |
| 2 | Line Limit Exceeded |
| 3 | Time Limit Exceeded |
| 4 | Opcode Error |
| 5 | Operand Error |
| 6 | Invalid Page Fault |

