# Get Monitor Information
A Powershell Module/Function that gets the serial number, make and model of a monitor(s) attached to a computer via WMI

#Installation
1. Find your PSModule paths by running `$env:PSModulePath.Split(";")` in a Powershell prompt
2. Place a folder in any one of these paths named Monitor-Information (this can actually be anything)
3. Place Monitor-Information.psm1 inside of this folder
4. If you have Powershell 3 or higher running the command (in this case Get-Monitor) will automatically import the module, otherwise you'll need to run `Import-Module Monitor-Information` and then run the command.
