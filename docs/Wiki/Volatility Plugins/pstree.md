To view the process listing in tree form, use the pstree command. This plugin uses the same approach as pslist hence it'll not display the hidden/terminated processes.

But the one advantage that this plugin gives is that we can easily identify the parent & child processes.

### Usage
	volatility -f memory.dump --profile=Win7SP1x86 pstree

![[volatility_pstree.png]]