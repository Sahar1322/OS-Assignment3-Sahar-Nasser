# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Sahar Nasser Alkhudhyr] |
| **Student ID** | [446052174] |
| **University Email** | [446052174]@std.psau.edu.sa |
| **GitHub Username** | [Sahar1322] |
| **Repository Link** | [https://github.com/Sahar1322/OS-Assignment3-Sahar-Nasser] |
 
---

## 🎥 Video Link

**Video Link**: [446052174_Assignment3_Demo.mp4](https://youtu.be/ovTSR0MVmTA?si=ZezgLSn4eKsYKmAY)

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 15, 2026, 8:22 PM]
**What I did**: Read the assignment instructions and examined the original scheduler output

**Details**:
I reviewed the roles of SharedStats, ReadyQueue, Process, and CpuWorker
I checked that the program used my student ID, 446052174. The output showed 10 processes, a time quantum of 5000 ms, and 2 CPUs
Both CPUs selected P1, and CPU-2 threw an IllegalThreadStateException
I kept the original output for the comparison in Part C

**Challenges**:
The verification block passed even though one CPU threw an exception, which made the result confusing

**Solution**:
I examined the output before the verification block and traced the failure to the unprotected read and removal operations in ReadyQueue.poll(). I understood that correct totals alone did not prove that both CPUs had worked correctly

**Time spent**: 2 hours

---

### Entry 2 - [November 15, 2026, 10:25 PM]
**What I did**: Added a ReentrantLock to protect the shared ready queue

**Details**:
I used queueLock in add(), poll(), processOf(), and snapshot() after adding it to ReadyQueue
Since the list and map reflect linked queue information, I used the same lock to protect them
Within the protected poll() method, I retained RaceWindow.pause()
In the final block of each protected method, I freed the lock

**Challenges**:
I put the head read, pause, remove, and empty check in the same restricted area
This stops two CPUs from choosing the same Thread object

**Solution**:
I put the head read, pause, removal, and empty check in the same secured area
This stops the same Thread object from being chosen by two CPUs

**Time spent**: 1:30 hours

---

### Entry 3 - [November 15, 2026, 11:10 PM]
**What I did**: Protected the shared statistics with separate locks

**Details**:
I added contextSwitchLock, completedProcessLock, and serviceTimeLock to SharedStats
I protected each update method and its matching getter with the same lock
I used separate locks because the three statistics are independent
I left the original read-modify-write statements and RaceWindow.pause() calls unchanged inside the protected sections

**Challenges**: I needed to understand why the getters required protection as well as the update methods

**Solution**: I used the matching lock for both reading and updating each variable so the threads coordinate their access and observe completed updates correctly

**Time spent**: 40 minutes

---

### Entry 4 - [November 16, 2026, 12:00 AM]
**What I did**:Replaced polling with a counting semaphore and added CPU shutdown handling

**Details**:
I added the available semaphore with an initial value of 0
I added available.release() after a process is inserted into the ready queue
I added waitForProcess(), which calls available.acquire(), and changed CpuWorker to wait before polling
I removed the polling delay and the busyWaitPolls increment from the CPU loop
I added shutdownSignaled and protected it with queueLock so the shutdown notification is sent only once

**Challenges**:A CPU blocked in acquire() would not automatically wake up when the final process completed

**Solution**:
I called signalShutdown() when the completed count reached the total number of processes
The method releases one shutdown permit per CPU, and a CPU exits when poll() returns null after waking

**Time spent**: 1:35 hours

---

### Entry 5 - [November 16, 2026, 2:00 AM]
**What I did**:Checked the updated output and prepared the written explanation

**Details**:
I compared the original output with the updated output
In the updated run, CPU-1 selected P1 and CPU-2 selected P2, and both CPUs continued executing processes
The verification showed 22 context switches, 10 completed processes, 78727 ms of total service time, and 0 busy-waiting polls
No exception or watchdog message appeared in the supplied final output

**Challenges**:I needed to explain the improvement even though the original verification block had also passed

**Solution**:
I used the duplicate selection of P1 and the original IllegalThreadStateException as evidence of the starter failure
I explained that the updated run removed this failure while preserving the correct totals

**Time spent**: 30 minutes

---

### Entry 6 - [November 16, 2026, 7:00 AM]
**What I did**:Reviewed the technical answers in MY_WORK.md

**Details**:
Compared the original and final verification blocks
Explained why both blocks showed correct totals despite the exception in the original run
Completed the table of critical sections and their locks
Checked that the explanations matched my code

**Challenges**:The identical verification totals made the improvement difficult to explain

**Solution**:
I described the duplicate selection of P1 and the IllegalThreadStateException in the original run, then explained that both CPUs continued working without this exception in the final run

**Time spent**: 30 minutes

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [6:45 hours]

**Most challenging part**:
The most challenging part was understanding the CPU shutdown logic, because an empty ready queue does not necessarily mean that every process has finished

**Most interesting learning**:
The most interesting point was that the original program could pass all numerical checks while still containing a serious concurrency failure

**What I would do differently next time**:
Next time, I would save the output after each feature and record the development log immediately after each work session
---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[I learned that correct totals do not always mean that a concurrent program is working correctly. 
In my original output, both CPUs selected P1, and CPU-2 threw an IllegalThreadStateException even though the verification checks passed. Protecting the ready queue with a ReentrantLock prevents two CPUs from removing the same thread. 
I also learned that a shared counter update contains separate read and write operations that need protection. 
A counting semaphore allows a CPU to block until work becomes available instead of repeatedly checking an empty queue. 
Finally, I learned that blocked workers need an explicit shutdown notification when no more work will arrive.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part for me was understanding how the CPUs should stop after the final process completed. 
An empty queue can be temporary because another CPU may still be running a process that will return to the queue. 
Therefore, I could not use an empty queue alone to decide that the simulation was finished. 
A CPU waiting inside available.acquire() also needs a signal before it can continue and exit. 
I used the completed-process count to detect completion and shutdownSignaled to prevent repeated shutdown notifications.
This helped me understand the difference between waiting for more work and stopping permanently.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I worked through the three features separately and traced how each one affected the program. 
I started by examining the original output and the operations inside ReadyQueue.poll(). 
I then followed the shared statistics methods and checked that each getter used the same lock as its matching update method. 
For the semaphore, I traced what happens when a process is added, when a CPU waits, and when all processes finish. 
I asked for clarification about the semaphore name and the location of the shutdown checks, then compared the explanation with the instructor's example. 
Finally, I compared the updated output with the starter output and checked both the verification values and the absence of exceptions.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization is needed when multiple workers access shared information. 
In a ticket-booking system, a protected reservation operation can prevent two customers from booking the same seat. 
In a banking system, coordinating balance updates can prevent one transaction from overwriting another transaction's result. 
A print queue resembles the ready queue because jobs are added by producers and removed by workers. 
A semaphore can make a worker wait until a print job becomes available. 
These applications also need a clear shutdown procedure so waiting workers do not remain blocked after the service stops.]

### Optional: What would you like to learn more about?

[I would like to learn more about fair locks, starvation, and how synchronization is implemented inside operating-system kernels]

### Optional: How confident do you feel about synchronization concepts now?

[Intermediate. I understand the purpose of mutex locks, critical sections, and counting semaphores, but I still need more practice with shutdown protocols and more complex deadlock scenarios.]

### Optional: Feedback on the assignment

[The assignment was useful because the broken starter made concurrency failures visible. 
The verification block helped me check the shared values, while the original exception showed why numerical checks alone were not enough. 
A short shutdown timeline would make the semaphore section easier to understand.]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[In my original run, CPU-1 and CPU-2 both selected P1, and CPU-2 threw an IllegalThreadStateException when the same Thread object was started again. However, all verification values matched: 22 context switches, 10 completed processes, 78727 ms of service time, and 0 busy-waiting polls, so the numerical difference was zero for every check. 
The surviving CPU continued processing the workload, which explains why the totals were correct despite the concurrency failure. 
As a separate example of a possible lost update, two process threads running under CPU-1 and CPU-2 could both read contextSwitchCount as 12, pause, and then both write 13 instead of reaching 14. 
This can happen without RaceWindow because a real operating system can interrupt execution between the read and write, and the timing-dependent interleaving makes the problem difficult to reproduce.]

Verification block of the **original starter**:
```
[═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 22       observed 22       ✔
  Completed processes                    expected 10       observed 10       ✔
  Total service time (ms)                expected 78727    observed 78727    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.
  
  [CPU-1] picks P1
[CPU-2] picks P1
Exception in thread "CPU-2" java.lang.IllegalThreadStateException
    at java.base/java.lang.Thread.start(Thread.java:1416)
    at CpuWorker.run(SchedulerSimulationSync.java:283)]
```

Verification block of **my final version**:
```
[═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 22       observed 22       ✔
  Completed processes                    expected 10       observed 10       ✔
  Total service time (ms)                expected 78727    observed 78727    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.
  
  The verification totals were correct in both runs. However, the starter run contained an IllegalThreadStateException after both CPUs selected P1. 
  In the final run, both CPUs continued executing processes without this exception, so the improvement was correct concurrent execution rather than different totals]
```

**Explanation of the timeline:**
[First, the process thread running under CPU-1 reads contextSwitchCount as 12. 
Before it writes the new value, the process thread running under CPU-2 also reads 12. 
The first thread writes 13, and the second thread then writes 13 using its own earlier copy. 
The final value is 13 instead of 14, so one increment is lost.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[The queueLock protects list and map in ReadyQueue.add(), poll(), processOf(), and snapshot(), and it also protects the shutdownSignaled check and update in signalShutdown(). 
Separate locks protect the update method and matching getter for contextSwitchCount, completedProcessCount, and totalServiceTime. 
I chose one lock per statistic because the variables are independent, which reduces unnecessary contention but requires more locks to manage. 
The queue uses a separate lock so queue operations do not unnecessarily block independent statistics operations, and each lock is released in finally to support continued progress. 
The locks provide mutual exclusion, but the default ReentrantLock is not fair, so bounded waiting and freedom from starvation are not guaranteed under every possible schedule.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| ReadyQueue: add(), poll(), processOf(), snapshot() | queueLock | Protects list and map from concurrent access and prevents duplicate selection. |
| ReadyQueue: signalShutdown() | queueLock | Protects shutdownSignaled so the shutdown signal is sent only once. |
| incrementContextSwitch(), getContextSwitchCount() | contextSwitchLock | Prevents lost updates and protects reads of contextSwitchCount. |
| incrementCompletedProcess(), getCompletedProcessCount() | completedProcessLock | Prevents lost updates and protects reads of completedProcessCount. |
| addServiceTime(), getTotalServiceTime() | serviceTimeLock | Prevents lost updates and protects reads of totalServiceTime. |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[The starter polls the ready queue and sleeps for 20 ms whenever it finds the queue empty, causing repeated checks and wake-ups, although my original run recorded 0 busy-waiting polls. In the final version, waitForProcess() calls available.acquire() so a CPU blocks when no permit is available. 
The semaphore starts at 0 because the queue is initially empty and reaches 10 after the initial process additions before the CPUs start. During normal execution, its permits represent published work that has not yet been acquired, while signalShutdown() releases SharedStats.totalCPUs permits once to wake waiting CPUs after all processes complete. 
Without those shutdown permits, a CPU already blocked in acquire() could wait forever; after waking for shutdown, it polls the empty queue and exits when thread is null.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[This design resembles the producer-consumer problem: main produces the initial processes, and CPU workers consume queued work while also acting as producers when they re-enqueue unfinished processes.]

**Semaphores for a bounded queue (name and initial value)**:
[For an initially empty bounded buffer of capacity K, the standard semaphores are empty initialized to K, full initialized to 0, and mutex initialized to 1]

**Deadlock scenario and prevention**:
[If the buffer is full and a producer acquires mutex before waiting on empty, it holds the mutex while waiting for a free slot. A consumer cannot remove an item because it also needs mutex, so neither side can proceed. Waiting for the required resource permit before acquiring mutex prevents this hold-and-wait pattern, while using a consistent order for multiple locks can prevent circular wait.]

## Summary

**Key concepts I understood through these questions:**
1. A critical section must protect the complete shared operation, not only its final write.
2. A counting semaphore coordinates work availability, while a mutex protects shared data.
3. Blocked workers need an explicit shutdown notification when no more work will arrive.

**Concepts I need to study more:**
1. Fairness, starvation, and bounded waiting.
2. Deadlock prevention in systems that use multiple locks and bounded queues.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
