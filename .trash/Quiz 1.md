---
sources:
  - "[[G5 (22-25) (CN, OS, DB)/OS/Intro]]"
  - "[[3 Disk Scheduling]]"
  - "[[4 Virtual Memory]]"
  - "[[2 Address Binding]]"
---
> [!question] The kernel is the `____` of the operating system and manages `____`.
>> [!success]- Answer
>> heart, system resources

> [!question] The primary function of an operating system is to manage applications directly.
>> [!success]- Answer
>> False

> [!question] Explain the difference between static and dynamic linking.
>> [!success]- Answer
>> Static linking copies all required code, including libraries, into the executable at compile time, resulting in larger executables but no runtime dependencies. Dynamic linking links external libraries at runtime, creating smaller executables but requiring those libraries to be present during execution.

> [!question] Match the page replacement algorithm to its description.
>> [!example] Group A
>> a) LRU
>> b) OPT
>> c) FIFO
>> d) LFU
>
>> [!example] Group B
>> n) Removes the least recently used page
>> o) Removes the least frequently used page
>> p) Replaces the page that won't be used for the longest time
>> q) Removes the oldest page
>
>> [!success]- Answer
>> a) -> n)
>> b) -> p)
>> c) -> q)
>> d) -> o)

> [!question] Select all that apply: Which of the following are subsystems of a modern operating system?
> a) File Manager
> b) Memory Manager
> c) Process Manager
> d) I/O Manager
> e) Security & Access Control
> f) Network Manager
>> [!success]- Answer
>> a) File Manager
>> b) Memory Manager
>> c) Process Manager
>> d) I/O Manager
>> e) Security & Access Control

> [!question] Which of the following is NOT a type of operating system discussed in the text?
> a) Batch OS
> b) Time-Sharing OS
> c) Multiprogramming OS
> d) Quantum OS
>> [!success]- Answer
>> d) Quantum OS

> [!question] Discuss the concept of thrashing in the context of virtual memory and explain how the principle of locality helps mitigate it.
>> [!success]- Answer
>> Thrashing occurs when a system spends more time swapping pages in and out of memory than executing processes, drastically reducing performance. This happens when the working set of processes exceeds available RAM. The principle of locality, which states that processes tend to access recently used data or nearby data, helps to reduce page faults. This minimizes swapping, improving performance and mitigating thrashing.  If locality holds, the system runs smoothly; if not, excessive page faults and subsequent thrashing result.

