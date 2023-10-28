**Priority Scheduling Algorithm: Enhancements and Additions to XV6 Operating System**

---

**Introduction**  
The XV6 operating system, designed as a teaching tool at MIT, emulates a simplified version of the UNIX operating system. This project saw the introduction of numerous enhancements and additions to the core XV6 system. This report serves to detail these modifications.

---

**1. System Call Implementation**  
**1.1 Addition of report_priority() System Call**  
- **Location**: proc.c, syscall.c, and associated header files.
  
- **Description**:  
  - A fresh system call, report_priority(), has been introduced. This system call delivers statistics and diagnostics about the priority of processes, helping in system introspection.
  
- **Purpose**:  
  - To extract insights about priority-based metrics which can assist in debugging, performance optimization, and system monitoring.

---

**2. Scheduler Enhancements**  
**2.1 Priority Scheduling**  
- **Location**: proc.c
  
- **Description**:  
  - Transition from the default round-robin algorithm to a Priority Scheduling mechanism.
  
- **Implementation**:  
  1. **Priority Queue Based Scheduling**:
    - Processes are placed in priority queues based on their priority attribute.
    - Ensures higher priority processes get scheduled before lower priority ones.
  2. **Modification to the Scheduler Loop**:
    - Rather than the typical round-robin, the loop selects the highest priority process that's in a RUNNABLE state.
  
- **Purpose**:  
  - To prioritize processes based on their importance or urgency, optimizing system responsiveness and throughput.

**2.2 Adjustments for Context Switching**:
- **Description**:
  - Essential changes made to guarantee efficient context switching and process state management under the new scheduling mechanism.
  - Ensures fair scheduling and maintains the interactive nature of the system.
  
**2.3 Introduction of New Attributes**:
- **Description**:
  - New attributes such as priority_level and last_run_time are integrated into the proc structure.
  - These assist the scheduler in making informed scheduling decisions and offer metrics for performance evaluation.

---

**3. Error Handling and Diagnostics**  
- **Location**: Various files including syscall.c, proc.c.
  
- **Description**:  
  - Advanced error detection mechanisms have been incorporated to identify and communicate system anomalies.
  - Furnishes more transparent feedback for developers and users, facilitating effective troubleshooting.

---

**4. Code Refactoring and Cleanup**  
- **Location**: Across multiple system files.
  
- **Description**:  
  - Regular refactoring and code cleaning exercises were carried out to improve code legibility, sustainability, and efficiency.

---

**Conclusion**  
Post modifications, the XV6 operating system exhibits improved functional, diagnostic, and reliability attributes. With updates ranging from the introduction of new system calls to changes in the scheduling logic, the system is now aptly equipped to meet modern requirements while still preserving the educational intent of XV6. Users are advised to delve deeper into these changes for a comprehensive understanding of the enhancements introduced.
