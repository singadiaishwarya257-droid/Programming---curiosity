# Processes

A process is a running instance of a program, managed by the operating system. The program is the set of instructions; the process is those instructions executing with state and resources.

A process commonly has:

- Its own virtual address space
- One or more threads of execution
- Open files or network connections
- Operating-system information such as permissions and identifiers

Starting an application creates a process. The operating system schedules its threads, controls access to resources, and can stop the process. Two processes running the same program are usually isolated from each other's memory, though they can communicate through files, pipes, sockets, or other inter-process mechanisms.

## Process versus thread

A process is a resource and isolation boundary; a thread is a path of execution inside a process. Threads in the same process can share memory, which makes communication convenient but also introduces coordination challenges. See [threads](threads.md).

When a process crashes, the operating system can usually reclaim its resources. If the program needs work to survive a restart, it must save appropriate state to persistent storage or another service.

## Curiosity questions

31. Who receives the `python app.py` command?
32. How does the operating system know where Python is?
33. What is a process?
40. What happens when the program crashes?

### Rabbit hole

How does a program know that another program has crashed?

## Explanations guided by the seven questions

### 31. Who receives the `python app.py` command?

A command must be interpreted to start the requested program. The shell or command processor receives the typed command. It resolves `python`, builds arguments, and asks the OS to launch it. In the terminal session and operating-system process environment. After you press Enter. The shell, OS, Python executable, then the script participate. If the executable cannot be found, the shell reports a command error.

### 32. How does the operating system know where Python is?

It must locate an executable to start the interpreter. The shell searches the current path or an explicitly supplied executable path. Environment settings such as `PATH` list directories to search. The executable resides in an installed directory or environment. The command is resolved at launch time. The shell locates the executable; the OS loads it. A wrong or missing path can select another version or fail to launch.

### 33. What is a process?

The OS needs to isolate and manage running programs and their resources. A process is a running program with state, memory, and operating-system resources. The OS creates an address space, starts threads, and schedules execution. It exists as managed state in the operating system and uses physical resources. It begins when a program is launched and ends when it exits or is terminated. The OS manages it; users and services can start or stop it. A crash ends or disrupts the process, while the OS reclaims its resources.

### 40. What happens when the program crashes?

A crash means execution cannot continue correctly. The process exits unexpectedly or is stopped after an unhandled failure. The runtime or OS reports an exception, fault, signal, or exit status. The failure occurs in the process; logs may be stored elsewhere. At the point an invalid operation or unhandled error occurs. The runtime, OS, supervisor, and monitoring system may observe it. A supervisor may restart it, but unsaved in-memory state can be lost.

### Rabbit hole: How does a program know another program has crashed?

Dependent work needs to detect failures and recover. It observes a process exit, missed heartbeat, closed connection, or timeout. The OS can report child-process status; remote systems use health checks and timeouts. Detection occurs in a supervisor, parent process, orchestrator, or peer service. Immediately for local exits, or after a timeout for network peers. Operating systems and monitoring software detect it; applications decide recovery. A slow but healthy process can look failed, so systems need cautious timeouts.
