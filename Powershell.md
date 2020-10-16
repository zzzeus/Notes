# This a note about usages of powershell

[Referenece](https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-6)

## Contents
1. [Files and folder](#Files-and-folder)
2. [String](#String)
3. [Network](#Network)
4. [PC information](#PC-information)

### 1. Files and folder
```powershell
ls *.txt

ls -Recurse | group Extension |sort -Descending Count

# Rename files
ls -File  | foreach { Rename-Item $_ -NewName $_.FullName.Replace('old','new')}

dir *.pdf | foreach { Rename-Item $_ -NewName ($_.BaseName+”_123.pdf”)  }

Dir | Where-Object { $_.Name -contains "-x86" } | ForEach-Object {
Rename-Item $_.Name $_.Name.replace("-x86", "") }

ls | Sort-Object -Descending Name | Select-Object Name,Length,LastWriteTime | ConvertTo-Html | Out-File ls.html

```

### 2. String
```powershell
# write into a file
'one','two','three' |set-content -path 'a.txt'
get-content -path 'a.txt' |measure -property length -maximum -minimum -average  

"太多 太多 的话 我还没有说， 太多 太多 太多 的理由值得你留下" -replace "\b(\w+)(\s+\1){2}\b", '$1'

Import-Csv .\file.csv -Header "link" | foreach { ( [uri]($_.link) ).Host }

```

### 3. Network
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

### 4. PC information
```powershell
# get BIOS information
Get-CimInstance -classname Win32_BIOS

# get processor information
Get-CimInstance -classname win32_processor |select-object -excludeproperty "CIM*"

# get computer name and manufacturer
get-CimInstance -ClassName Win32_ComputerSystem
```

### 5. GetInstalledSoftwares
```powershell
function Get-InstalledSoftwares
{
    #
    # Read registry key as product entity.
    #
    function ConvertTo-ProductEntity
    {
        param([Microsoft.Win32.RegistryKey]$RegKey)
        $product = '' | select Name,Publisher,Version
        $product.Name =  $_.GetValue("DisplayName")
        $product.Publisher = $_.GetValue("Publisher")
        $product.Version =  $_.GetValue("DisplayVersion")

        if( -not [string]::IsNullOrEmpty($product.Name)){
            $product
        }
    }

    $UninstallPaths = @(,
    # For local machine.
    'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall',
    # For current user.
    'HKCU:\Software\Microsoft\Windows\CurrentVersion\Uninstall')

    # For 32bit softwares that were installed on 64bit operating system.
    if([Environment]::Is64BitOperatingSystem) {
        $UninstallPaths += 'HKLM:SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall'
    }
    $UninstallPaths | foreach {
        Get-ChildItem $_ | foreach {
            ConvertTo-ProductEntity -RegKey $_
        }
    }
}
```