# This a note about usages of powershell

[Referenece](https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-6)

## Contents
1. [Files and folder](#Files-and-folder)
2. [String](#String)
3. [Network](#Network)
4. [PC information](#PC-information)

### Files and folder
```powershell
ls *.txt

ls -Recurse | group Extension |sort -Descending Count


```

### String
```powershell
# write into a file
'one','two','three' |set-content -path 'a.txt'
get-content -path 'a.txt' |measure -property length -maximum -minimum -average  


```

### Network
```powershell
# get ip address
Get-WmiObject -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true -ComputerName . | Format-Table -Property IPAddress

# list all ip addresses
 Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true | Select-Object -ExpandProperty IPAddress

 # get Network adapter properties
 Get-CimInstance -Class Win32_NetworkAdapter

# get html from website
Invoke-WebRequest -Uri "www.google.com"


```

### PC information
```powershell
# get BIOS information
Get-CimInstance -classname Win32_BIOS

# get processor information
Get-CimInstance -classname win32_processor |select-object -excludeproperty "CIM*"

# get computer name and manufacturer
get-CimInstance -ClassName Win32_ComputerSystem
```
