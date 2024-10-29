So here's the fun and exciting part. You can literally get the hashes of the domain credentials stored in the registry using hashdump. What I mean to say is that you can actually get the passwords of the users. These are NTLM hashes. These hashes can be cracked using online NTLM crackers like [crackstation.net](https://crackstation.net/)

### Usage
	volatility -f memory.dump --profile=Win7SP1x86 hashdump

![[volatility_hashdump.png]]