## IMPLEMENTATION OF CPU SCHEDULING ALGORITHM
## FIRST COME FIRST SERVE(FCFS) SCHEDULING


## AIM:
To implement First-Come-First-Serve (FCFS) Scheduling

## ALGORITHM:
Start the process
Accept the number of processes in the ready queue
For each process in the ready queue, do the following:
Accept the process ID and burst time
Calculate the waiting time for the current process
Calculate the turnaround time for the current process
Display the process ID, burst time, waiting time and turnaround time for the current process
Calculate the average waiting time and average turnaround time
Stop the process
## PROGRAM:
```
# Get the number of processes from the user
n = int(input("Enter number of processes: "))

# Initialize lists to store process names and burst times
processes = []
burst_time = []

# Input process names and burst times
for i in range(n):
    p = input("Enter process name: ")
    processes.append(p)
    b = int(input("Enter burst time: "))
    burst_time.append(b)

# Initialize waiting time and turnaround time lists
wt = [0] * n
tat = [0] * n

# Calculate waiting time for each process
wt[0] = 0
for i in range(1, n):
    wt[i] = burst_time[i - 1] + wt[i - 1]

# Calculate turnaround time for each process
for i in range(n):
    tat[i] = burst_time[i] + wt[i]

# Display processes along with all details
print("Processes Burst time Waiting time Turn around time")
total_wt = 0
total_tat = 0

# Calculate total waiting time and total turnaround time
for i in range(n):
    total_wt += wt[i]
    total_tat += tat[i]
    print(f"{processes[i]}\t\t{burst_time[i]}\t {wt[i]}\t\t {tat[i]}")

# Calculate and display average waiting time and average turnaround time
avg_wt = total_wt / n
avg_tat = total_tat / n
print(f"Average waiting time = {avg_wt}")
print(f"Average turnaround time = {avg_tat}")
```
## OUTPUT:
![272647726-bd4d6101-b830-4aa6-ac62-15827e35009d](https://github.com/JAYAVARTHAN-P/EX.5-IMPLEMENTATION-OF-CPU-SCHEDULING-ALGORITHMS/assets/121369281/29d09aec-1662-4e01-9ed5-e07921c82d08)


## RESULT:
First-Come-First-Serve Scheduling is implemented successfully.

## Shortest Job First (SJF) Preemptive Scheduling

AIM:
To implement Shortest Job First (SJF) Preemptive Scheduling

ALGORITHM:
Start the process
Accept the number of processes in the ready queue
For each process in the ready queue, do the following:
Accept the process ID and burst time
Calculate the waiting time for the current process
Calculate the turnaround time for the current process
Display the process ID, burst time, waiting time and turnaround time for the current process
Calculate the average waiting time and average turnaround time
Stop the process
PROGRAM:
```
n = int(input("Enter the number of processes: "))

burst_time = []
processes = list(range(1, n + 1))

print("Enter burst times for each process:")
for i in range(n):
    burst_time.append(int(input(f"Burst time for process {i + 1}: ")))

total = 0
wt = [0] * n
tat = [0] * n

# Sorting burst times and processes
for i in range(n):
    pos = i
    for j in range(i + 1, n):
        if burst_time[j] < burst_time[pos]:
            pos = j

    burst_time[i], burst_time[pos] = burst_time[pos], burst_time[i]
    processes[i], processes[pos] = processes[pos], processes[i]

wt[0] = 0

# Calculating waiting time for all processes
for i in range(1, n):
    wt[i] = 0
    for j in range(i):
        wt[i] += burst_time[j]

    total += wt[i]

avg_wt = total / n

print("\nProcess   Burst Time   Waiting Time   Turnaround Time")
total_tat = 0
for i in range(n):
    tat[i] = burst_time[i] + wt[i]
    total_tat += tat[i]
    print(f"P{processes[i]} {burst_time[i]:12d} {wt[i]:12d} {tat[i]:12d}")

avg_tat = total_tat / n
print(f"\nAverage Waiting Time = {avg_wt:.2f}")
print(f"Average Turnaround Time = {avg_tat:.2f}")
```
## OUTPUT:
![272655574-a44410a0-f001-4f05-ae9b-f870766e18c5](https://github.com/JAYAVARTHAN-P/EX.5-IMPLEMENTATION-OF-CPU-SCHEDULING-ALGORITHMS/assets/121369281/720c913e-67be-4f89-8adb-897c074eb527)


## RESULT:
Shortest Job First (SJF) preemptive scheduling is implemented successfully.

## Shortest Job First (SJF) Non-Preemptive Scheduling

## AIM:
To implement Shortest Job First (SJF) Non-Preemptive Scheduling

## ALGORITHM:
## PROGRAM:
## OUTPUT:
## RESULT:
Shortest Job First (SJF) Non-preemptive scheduling is implemented successfully.

AIM: To implement Round Robin (RR) Scheduling

ALGORITHM:

PROGRAM:

OUTPUT:

RESULT: Round Robin (RR) Scheduling is implemented successfully.

AIM: To implement Priority Preemptive Scheduling

ALGORITHM:

PROGRAM:

OUTPUT:

RESULT: Priority Preemptive scheduling is implemented successfully.

AIM: To implement Priority Non-Preemptive Scheduling

ALGORITHM:

PROGRAM:

OUTPUT:

RESULT: Priority Non-preemptive scheduling is implemented successfully.
