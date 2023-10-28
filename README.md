**Enhancements and Additions to XV6 Operating System**

**Introduction:**  
The XV6 operating system, a minimalistic teaching version of UNIX developed at MIT, underwent a series of modifications to improve its functionality and provide a more comprehensive understanding of OS concepts for educational purposes. This report elucidates these modifications.

---

**1. System Call Implementation:**

**1.1 Addition of report_statistics() System Call**
   - **Location:** `proc.c`, `syscall.c`, and related header files.
   - **Description:**  
     A new system call, `report_statistics()`, was developed. This call provides statistics and diagnostics about process execution.
   - **Purpose:**  
     To acquire data on process-related metrics useful for debugging, performance tuning, and system monitoring.

---

**2. Scheduler Enhancements:**

**2.1 FCFS (First-Come-First-Serve) Scheduling**
   - **Location:** `proc.c`
   - **Description:**  
     The default round-robin algorithm was replaced with a First-Come-First-Serve (FCFS) scheduling mechanism.
   - **Implementation Details:**
     1. **Sorting Based on Arrival Time:** Processes are ordered according to their `arrival_time`.
     2. **Modification to the Scheduler Loop:** Instead of the round-robin method, the loop selects the process with the earliest `arrival_time` in a RUNNABLE state.
   - **Purpose:**  
     To determine execution order based on when processes enter the system, allowing for a more predictable execution sequence.

**2.2 Adjustments for Context Switching:**
   - **Description:**  
     Necessary changes were implemented to ensure appropriate context switching, process state management, and to prevent process starvation, thus retaining system interactivity.
     
**2.3 Incorporation of New Attributes:**
   - **Description:**  
     New attributes such as `arrival_time`, `start_time`, and `end_time` were added to the `proc` structure. 
   - **Purpose:**  
     Assists the scheduler in ascertaining the order of process execution and furnishes data for performance analysis.

**2.4 Priority-Based Scheduling**
   - **Location:** `proc.c`, `syscall.h`, `syscall.c`, `sysproc.c`, `usys.S`, and `user.h`.
   - **Description:**  
     An enhancement was added to the scheduler to facilitate priority-based scheduling, ensuring that processes with higher priorities are scheduled before those with lower ones.
   - **Purpose:**  
     Enables critical tasks to be executed promptly, augmenting the system's overall efficiency and responsiveness.

---

**3. Error Handling and Diagnostics:**
   - **Location:** Various files, including `syscall.c` and `proc.c`.
   - **Description:**  
     Enhanced mechanisms were developed for error handling, making it easier to capture and report system anomalies.
   - **Purpose:**  
     Provides developers and users with clearer feedback, aiding in troubleshooting.

---

**4. Code Refactoring and Cleanup:**
   - **Location:** Various files throughout the system.
   - **Description:**  
     Intermittent refactoring and code cleanup exercises were carried out to amplify code readability, maintainability, and optimize performance.

---

**Conclusion:**  
With a series of substantial modifications ranging from the introduction of new system calls, scheduler modifications, to the addition of priority-based scheduling, the XV6 operating system now boasts enhanced functionality, reliability, and diagnostic capabilities. These refinements make the system more apt for contemporary needs while still preserving the pedagogic essence of XV6. Clients and developers are advised to closely review these changes to gain a comprehensive understanding of the advancements made.

--- 

Note: The successful implementation and functionality of the described features require a meticulous integration within the XV6 codebase.
