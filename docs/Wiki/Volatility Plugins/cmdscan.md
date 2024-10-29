The cmdscan plugin searches the memory for conhost.exe on Windows 7 Operating systems. This is one of the most powerful commands you can use to gain visibility into an attackers actions on a victim system, whether they opened cmd.exe

This plugin finds structures known as COMMAND_HISTORY by looking for a known constant value (MaxHistory) and then applying sanity checks.

To put it simply, you can see the content that the attacker typed in the command prompt.

### Usage
	volatility -f memory.dump --profile=Win7SP1x86 cmdscan

![[volatility_cmdscan.png]]

By default, the value in MAXHistory is set to 50. We can change that. Also, cmdscan can print up to 50 commands. We can increase that by adding  --max_history=NUMBER along with the plugin command.