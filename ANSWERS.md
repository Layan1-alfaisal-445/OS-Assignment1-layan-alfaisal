# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

A process is an independent program with its own memory space 
while a thread is a smaller unit of execution that runs inside a process and shares the same memory
One important difference is memory sharing threads share memory which makes communication faster
Another difference is creation overhead threads are lightweight and faster to create compared to processes
Using threads in SchedulerSimulation made it easier to simulate CPU scheduling and switch between processes efficiently


---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

In Round-Robin scheduling if a process does not finish within its time quantum it is stopped and added again to the end of the ready queue
For example after a thread finishes executing its time quantum using currentThread.join() the program checks if the process is finished using if (!process.isFinished())
If it is not finished it is re-added to the queue using addProcessToQueue(process, processQueue, processMap)

**Explanation of example:**
P1 executing quantum
P1 yields CPU for context switch
P1 added to ready queue

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

thread goes through states: New, Runnable, Running, Waiting, and Terminated
It starts with new Thread() and moves to execution using start() During execution sleep() puts it in Waiting state
Also join() makes the main thread wait When the task finishes the thread reaches the Terminated state

1. **New**:P1 is in the New state when it is created using new Thread(process) before it starts execution

2. **Runnable**: P1 becomes Runnable when currentThread.start() is called and it is ready to run

3. **Running**: P1 is in the Running state when it starts executing the run() method on the CPU

4. **Waiting**: P1 enters the Waiting state when Thread.sleep() is used during execution causing it to pause temporarily

5. **Terminated**: P1 is in the Terminated state when it finishes execution and remainingTime <= 0

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [web server]

**Description**: 
A web server handles multiple user requests at the same time, where each request runs as a separate thread

**Why Round-Robin works well here**: 
Round-Robin ensures that every request gets a fair share of CPU time. It improves responsiveness because no single request can block others. It also keeps the system predictable and prevents long waiting times for users

### Example 2: [mobile applications]

**Description**: 
Mobile apps run multiple tasks in the background such as downloading data, playing music and updating the UI

**Why Round-Robin works well here**: 
Round-Robin allows all tasks to run smoothly by giving each one a small time slice. This keeps the app responsive and prevents freezing. It also ensures fairness between background and foreground tasks

---

## Summary

**Key concepts I understood through these questions:**
1. 
2. 
3. 

**Concepts I need to study more:**
1. 
2. 
