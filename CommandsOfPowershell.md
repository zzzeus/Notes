## This a note about usages of powershell

[Referenece](https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-6)

* Files and folder
```powershell
ls *.txt

ls -Recurse | group Extension |sort -Descending Count


```

* String

* Network
```powershell

Get-WmiObject -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true -ComputerName . | Format-Table -Property IPAddress
```

* PC information
```powershell

```
