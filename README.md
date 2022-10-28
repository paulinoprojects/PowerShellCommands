# -PowerShellCommands
A list of useful PowerShell CMD
PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework. 
PowerShell runs on Windows, Linux, and macOS

Reference: https://learn.microsoft.com/en-us/powershell/scripting/learn/ps101/01-getting-started?view=powershell-7.2
__________________________________________________________________
Basic Syntax:
      -command-name -Required Parameter -Name Required -Parameter Value
      Optional Parameter Name> <Optional Parameter Value
      Optional Switch Parameters>
      Optional Parameter Name> Required Parameter Value>
__________________________________________________________________

Most-used commands:
1. Get-Command | export-csv c:\temp\AllCommands.csv
2. Get-Service
3. Get-Process
4. Get-EventLog
5. Get-ADUser -Identity "username" -Properties
6. Test-NetConnection -ComputerName "Hostname or IP"  #ping#
7. Resolve-DnsName -Name "Hostname"
      By appending the -server switch, followed by a DNS server’s IP address, we can perform a DNS resolve request against a specific server to verify resolution is working properly.
      The Get-DnsClient cmdlet lets you check the DNS client information for a device. It indicates what DNS servers are being used by the device to perform address resolutions as configured on multiple adapters.
      The Set-DnsClientServerAddress cmdlet allows for specified DNS servers to be added to the network configuration.
8. Get-NetIPConfiguration
9. Get-ExecutionPolicy and Set-ExecutionPolicy
You can create and execute PowerShell scripts, however, Microsoft has disabled scripting by default in an effort to prevent malicious code from executing in a PowerShell environment. You can use the Get-ExecutionPolicy to check which execution policy is enforced prior to running a script and then use the Set-ExecutionPolicy command to change the level of security if needed.

There are four levels of security associated with the Set-ExecutionPolicy command:
  Unrestricted: This removes all restrictions from the execution policy.
  Restricted: This is the default execution policy and only allows commands to be entered interactively. PowerShell scripts are not allowed to run.
  All Signed: If the execution policy is set to All Signed, scripts will be allowed to run if they are signed by a trusted publisher.
  Remote Signed: If the execution policy is set to Remote Signed, PowerShell scripts that have been created locally will be allowed to run. Scripts created remotely will be allowed to run if they are signed by a trusted publisher.
