This is a significantly used plugin which helps in listing the details of the processes which were running when the dump was taken. It shows the offset, process name, process ID(PID), the parent process ID(PPID), number of threads, number of handles, and date/time when the process started and exited.

### Usage
	volatility -f memory.dump --profile=Win7SP1x86 pslist

![[volatility_pslist.png]]

However, pslist fails to show hidden/terminated processes. The plugin which solves this problem is psscan.