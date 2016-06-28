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
