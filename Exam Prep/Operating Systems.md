Distributed Systems (Part of Week 10) is not in the exam. But Virtualisation and other stuff in Week 10 is there for the exam.

There might be some pseudo code to read or to write in the exam.

**Answer tips**: Don't just answer yes/no. Explain the reason behind that in short.

#### Acronyms & Definitions
- MMU - Memory Management Unit : Translates virtual addresses to physical addresses
- ALU - Arithmetic Logical Unit
- TLB - Translation Lookaside Buffer : Stores recent translations of vrirtual to physical memory
- Quantum Time - Used for scheduling processes. It means a short amount of time or a slice of time.
- Deterministic - If you know the initial condition, you can know the behaviour of the program on everything in the system and we can create all the actions that are happening.
- Real-time operating systems: These systems have deadlines that ensure a process get executed in a given amount of time. Eg: Planes, nuclear power plants, consoles, etc.
- Paging - Breaking down memory units to smaller elements called pages (usually 4kb but can be as large as 1mb) for the purpose of memory protection.

#### Components in CPU:
- Different cores
	- ALU - Arithmetic Logical Unit
	- PC - 
	- SP - 
	- R1 - Register 1
	- R2 - Register 1
	- L1 Data Cache - Small cache in core
	- L2 Data Cache - Small cache in core
	- Instruction Cache - Copied instructions from memory
	- Prediction Cache - Predicts next steps in the process
	- TLB Cache - Transaction Local Head Buffer Cache
- L3 Data Cache - Large cache shared by all cores

#### Introduction to CPUs
##### 1. Transistors and Gates
- CPUs are made of transistors and transistors allow for creating logical gates like AND/OR/NAND gates
- NAND is the opposite of AND
- NOR is the opposite of OR
- For XOR - same same is 0, if either is 1, then 1
- Logical gates can be combined to create digital circuits like adders (circuit for addition of numbers), multipliers, etc.
- Adders can be combined to create n-bit adders like 32-bit adder, etc
- In the same way, we can create multipliers, random number generators, etc
- When designing circuits, it's always a trade-off between the size, footprint of the transistor and the latency needed.
- The processors on the graphics cards were used to be created in such a way that the latency was not so important. 
- With CPUs latency is important cos it's about doing operations as quickly as possible.

##### 2. Registers and Arithmetic units
- Precomputed tables (I think precomputed gates) were often implemented in circuits
	- These were good for shorter latency, simpler design and for implementing difficult circuits like multiplication, divsion.
	- But not good in terms of scaling and precision
- ALU (Arithmetic Logical Unit) processes all the arithmetic operations (addition, multiplication, etc)
- Cache is a copy of what we get in the memory.
- Intruction cache stores a copy of instructions from memory. This cache is separate from data cache in order to avoid reloading which would decrease the performance
- Why the cache sizes are different and why different cache sizes are needed: Smaller caches (L1 & L2) are closer to the ALU, so the computations can be done quicker. The bigger cache (L3) while it can fit a lot of data is farther and is share among all cores, so the information retrieval is a bit slower.
- Prediction cache: Based on the conditions in the code, it'll predict where the code is going to go next and write that data into it.
- ==If there are 'if else' conditions in the code, the processor doesn't look ahead or read further cause, there are multiple paths for the program to diverge into. It could be any one of the number of if and else paths. At some point, the processor has to decide which path to take, meaning which if or else conditoin to look ahead, if not, it will be executing only one instruction at a time. If the predicted path is correct then no clock cycles are lost. But if it's incorrect, then some clock cycles are lost and the program is going to continue to look ahead.==
- Circuits (Adders, multipliers) deal directly with Registers in CPUs, not memory
- ==A register won't be an address fixed inside an ALU, but it will be one location inside the buffer and this location can change. This is cos, the compiler might produce code with some registers and reuse the same registers for independent instructions.==

##### 3. CPU Pipeline
- If the instructions are independed, the processor might reorder them. Meaning, if the second instruction is not dependent on the first one, it might get reordered.
- The time it takes to move an instruction from one part of the CPU to another is depended on the frequency of the processor and the distance.
- Power dissipated by the processor depends on frequency and voltage. However, power consumption doesn't increase linearly with the increase in frequency. Power = Frequency x Voltage ^ 2

##### 4. SIMD Programming
- SIMD - Single Instruction Multiple Data
- 






#### Scheduling
- **==Scheduling==** is the operating system trying to figure out which program to run next on the processor
- **==Scheduler==** is part of the operating system managing scheduling
- **==Scheduling algorithm==** is the algorithm used by the scheduler
- **==Process Switching / Context Switching==** consists of switching between different tasks
	- Its costly and resource intensive
- Scheduling needs to be done in a couple of scenarious
	- When a new process is created
	- When a process gets blocked or interrupted
	- When a process gets terminated
	- or When the time allocated for a process has ended
- **==Multitasking==**
	- **Non-Multitasking** (DOS)
		- Scheduling is sequential, meaning one process runs after the other.
	- **Co-Operative Multitasking** (Windows 2.1)
		- The process blocks itself when needed. The process sends the instruction to the processor saying that it no longer needs to be scheduled.
		- <u>Advantage</u>: It's more deterministic. If implemented properly, it's faster to schedule and safe. If you want to prove something is working correctly in a pre-defined environment, then co-operative multitasking can be used.
		- <u>Disadvantage</u>: If there is a bug in the process and it loops continuously, then it will consure system resources and slows down the operating system.
	- **Preemptive Multitasking** (Windows 95, Linux)
		- OS interrupts the processes when quantum time (alloted time) has lapsed or when the process needs to wait for resources
		- <u>Advantage</u>: Safer. One bug doesn't bring down the whole system. It's more interactive cos you can easily switch between processes.
		- <u>Disadvantages</u>: 
			- Less safe in terms of process execution, we don't know if the process has executed correctly and completely.
			- More overhead. Need to decide which process to schedule next cos unlike in pre-emptive, the OS handles the scheduling and interrupts processes many many times. So scheduling has to be done more often.
- **==Scheduling Environment==**
	- Depending on the evironment (smartphone vs computer) we can have different goals
	- For <u>interactive environments</u>, preemptive scheduling is the best option as there could be a lot of interactions from the user within a short amount of time.
	- For <u>batch envrionments</u>, like simulation, they are usually done in supercomputers and data centres. In those cases, co-operative multitasking is still a good option cos it's the user that decides the resources needed and based on that scheduling can be done.
	- **Sub-Schedulers**:
		- <u>Long-Term Scheduler</u>: For long term tasks like background tasks that need to keep running. Eg: Disk fragmentation
		- <u>Mid-Term Scheduler</u>: For tasks that need to run from time to time often. Eg: Virtual memory management
		- <u>Short-Term Scheduler</u>: For shorter tasks like running a powerpoint, a small application, etc.
	- Scheduling is usually not deterministic meaning we don't know how the operating system is going to schedule the processes. In an interactive environment like laptop, that's fine. But in a real-time environment like a financial-system maybe, that will have real business impact. 
- **==Schedulers==**
	- **Round Robin**: This is the most commonly used scheduler in interactive environments. It has a FIFO list in which each process is alloted a certain amount of time (Eg: 10ms). After the time has lapsed, the process gets rescheduled if not completed.
	- **Highest Response Ratio Next**: In this, a priority is calculated and assigned to each process and the process with the lowest priority gets rescheduled. It's used in Linux OS.
	- **Fair Share Scheduling**: Fixed amount of CPU resources are distributed among users/groups
- It's important to dynamically analyse the operating system and know the waiting time for each process.

#### Memory Management
- ==**Heap**== stores dynamic variables that are allocated dynamically (as required) when the program runs. When the program is compiled, there might be some varibles which can be know explicitly to be required by the program such as global variables. Even these are stored in the heap. 
- ==**Stack**== is a very small memory area, usually around 4 kilobytes. Not sure what it actually does!
- **==Operating System Objectives regarding Memory Management==**
	- To keep track to how much memory is in use and what parts of it is
	- To allocate and de-allocate memory between for processes
	- To move data to storage when memory is at capacity
	- To communicate to the application that there is enough memory available even when there isn't. The reason this is done is so that processes can be executed even when the physical memory available is low. 
	- The way it's done is, operating system creates a virtual memory (say 4 GB) and  communicates that to the process. 
	- Each process will have it's own virtual memory address but this address could be the same for another process as well. The location on the physical memory however will be different.
	- These virtual addresses are translated to physical address in hardware using MMU and TLB.
- **==5 requirements for memory management==**: 
	- <u>Protection</u>: 
		- Particularly if one process can access the memory of another process, it could potentially corrupt the data or cause security issues. 
		- Memory protection is not possible at compilation time.
		- Memory protection can be done using CPU support by breaking down memory units into smaller elements called pages (usually 4kb but can be as large as 1mb). These pages then have some properties like 'non-executable bits' and 'memory allocation status'.
	- <u>Sharing</u>:
		- Sometimes memory sharing might be necesasry like sharing libraries.
		- It could be harder to do with memory protection.
		- There are mechanisms available to support memory sharing through 'virtual memory' and 'pages'.
	- <u>Relocation</u> : As new processes are created and old processes are terminated, the physical location of the process on the memory can be changed anytime by the operating system.
	- <u>Logical Organization</u>
	- <u>Physical Organization</u>
- **==Memory Partitioning==** : Memory can be partitioned in different ways depending on the usecases
	- **Partitionning Techniques**
		- <u>Fixed Partitioning</u> : This divides memory into different partitions based on number of processes. One process per partition. It's done when the operating system starts. Some issues here would be when the process is larger than the partition and it it's smaller, there might be a loss of memory space. It's typically used in Aircraft systems. 
		- <u>Dynamic Partitioning</u> : Partitions are created dynamically, it's efficient but could become complex as extra opertions are required.
		- <u>Paging</u> : Mostly used for smartphones and laptopsaa
		- Segmentation
		- Memory Allocation
		- Virtual Memory