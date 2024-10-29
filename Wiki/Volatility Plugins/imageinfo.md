---

---
This particular command is most often used to identify the operating system, service pack, and hardware architecture (32 or 64 bit).

The imageinfo output tells you the suggested profile that you should pass as the parameter to --profile=PROFILE when using other plugins. There may be more than the one suggested profile and we must be careful to select the correct one.

### Usage
	volatility -f memory.dump imageinfo

![[volatility_imageinfo.png]]

As you can see this command helps you to know the suggested profiles, the date and time dump image were created and no of processors.