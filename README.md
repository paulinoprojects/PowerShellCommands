# -PowerShellCommands
A list of useful PowerShell CMDs / Windows Powershell ISE
PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework. 
PowerShell runs on Windows, Linux, and macOS

Reference: https://learn.microsoft.com/en-us/powershell/scripting/learn/ps101/01-getting-started?view=powershell-7.2
__________________________________________________________________

Most-used commands:
- <b>Get-Command | export-csv c:\temp\AllCommands.csv</b> : Get-Command is an easy-to-use reference cmdlet that brings up all the commands available for use in your current session.
-     Get-Command | export-csv c:\temp\AllCommands.csv

- <b>Get-Help</b>: quick access to the information you need to run and work with all of the available commands.
-     Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>][-Functionality <String[]>] [-Role <String[]>] [-Examples][<CommonParameters>]
      
- <b>Get-EventLog</b>:  parse your machine’s event logs using the Get-EventLog cmdlet. There are several parameters available. Use the -Log switch followed by the name of the log file to view a specific log.
-     Get-EventLog -Log "Application"
