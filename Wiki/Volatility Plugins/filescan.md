This will find open files even if a rootkit is hiding the files on disk and if the rootkit hooks some API functions to hide the open handles on a live system. The output shows the physical offset of the FILE_OBJECT, file name, number of pointers to the object, number of handles to the object, and the effective permissions granted to the object.

### Usage
	volatility -f memory.dump --profile=Win7SP1x86 filescan

![[volatility_filescan_plugin.png]]