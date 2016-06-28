# Get Monitor Information
A Powershell Module/Script that gets the serial number, make and model of a monitor(s) attached to a computer via WMI

## Module vs Script
I've included both a module and script version of this. This allows you to either run it quickly for one-off situations (script version) or install it (module version) into your PSModule path (see instructions below) for long-term use without relying on a having the script file's path.

## Module Installation
If you choose to install the .psm1 module version of this, follow these instructions:

1. Find your PSModule paths by running `$env:PSModulePath.Split(";")` in a Powershell prompt
2. Place a folder in any one of these paths named Monitor-Information (this can actually be anything)
3. Place Monitor-Information.psm1 inside of this folder
4. If you have Powershell 3 or higher running the command (in this case Get-Monitor) will automatically import the module, otherwise you'll need to run `Import-Module Monitor-Information` and then run the command.

## Usage (Script)
To use the script:

```PowerShell
PS C:\Scripts\> Get-Monitor.ps1 -ComputerName SSL1-F1102-1G2Z

Manufacturer Model    SerialNumber AttachedComputer
------------ -----    ------------ ----------------
HP           HP E241i CN12345678   SSL1-F1102-1G2Z
HP           HP E241i CN91234567   SSL1-F1102-1G2Z 
```

You can also use it with multiple computers:
```PowerShell
PS C:\Scripts\> $Computers = @("SSL7-F108F-9D4Z","SSL1-F1102-1G2Z","SSA7-F1071-0T7F")
PS C:\Scripts\> Get-Monitor.ps1 -ComputerName $Computers

Manufacturer Model      SerialNumber AttachedComputer
------------ -----      ------------ ----------------
HP           HP LA2405x CN12345678   SSL7-F108F-9D4Z
HP           HP E241i   CN91234567   SSL1-F1102-1G2Z 
HP           HP E241i   CN89123456   SSL1-F1102-1G2Z 
HP           HP E241i   CN78912345   SSL1-F1102-1G2Z
HP           HP ZR22w   CN67891234   SSA7-F1071-0T7F
```

## Usage (Module)
The module version is identical accept you don't have to reference the script file and its location, you simply have to run the command from any directory. Once the module is installed, use the command:

```PowerShell
PS C:\Scripts\> Get-Monitor -ComputerName SSL1-F1102-1G2Z

Manufacturer Model    SerialNumber AttachedComputer
------------ -----    ------------ ----------------
HP           HP E241i CN12345678   SSL1-F1102-1G2Z
HP           HP E241i CN91234567   SSL1-F1102-1G2Z 
```

You can also use it with multiple computers:
```PowerShell
PS C:\Scripts\> $Computers = @("SSL7-F108F-9D4Z","SSL1-F1102-1G2Z","SSA7-F1071-0T7F")
PS C:\Scripts\> Get-Monitor -ComputerName $Computers

Manufacturer Model      SerialNumber AttachedComputer
------------ -----      ------------ ----------------
HP           HP LA2405x CN12345678   SSL7-F108F-9D4Z
HP           HP E241i   CN91234567   SSL1-F1102-1G2Z 
HP           HP E241i   CN89123456   SSL1-F1102-1G2Z 
HP           HP E241i   CN78912345   SSL1-F1102-1G2Z
HP           HP ZR22w   CN67891234   SSA7-F1071-0T7F
```
