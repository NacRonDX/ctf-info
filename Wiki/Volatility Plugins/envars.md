To display a process’s environment variables, use the envars plugin. Typically this will show the number of CPUs installed and the hardware architecture, the process’s current directory, temporary directory, session name, computer name, username, and various other interesting artifacts.

### Usage
	volatility -f memory.dump --profile=Win7SP1x86 envars

![[volatility_envars.png]]