# Useful PowerShell Commands and Scripts for New Administrators

## **Useful Commands**

### **System Information**
```powershell
Get-ComputerInfo        # Retrieve system details
Get-NetIPAddress        # Display network information
systeminfo              # Detailed system info (cmd command usable in PowerShell)
```

### **Process and Service Management**
```powershell
Get-Process             # List running processes
Stop-Process -Name notepad -Force  # Kill Notepad process
Get-Service             # List system services
Restart-Service Spooler # Restart Print Spooler service
```

### **File and Folder Management**
```powershell
Get-ChildItem           # List files in a directory (like 'ls')
New-Item -ItemType File -Name newfile.txt  # Create a new file
Remove-Item newfile.txt -Force   # Delete a file
Copy-Item file1.txt -Destination C:\Backup  # Copy file to another location
```

### **User Management**
```powershell
Get-LocalUser           # List local user accounts
New-LocalUser -Name "TestUser" -Password (ConvertTo-SecureString "Test@123" -AsPlainText -Force)
Remove-LocalUser -Name "TestUser"  # Delete a user account
```

### **Networking**
```powershell
Test-Connection google.com -Count 4  # Ping Google
Get-NetAdapter           # List network adapters
Get-NetFirewallRule      # Show active firewall rules
```

---

## **Useful PowerShell Scripts and How-To Guides**

### **1. System Health Check Script**
#### **Description:**
This script gathers system information, checks disk space, and lists running processes.
#### **Script:**
```powershell
Write-Output "System Health Check"
Write-Output "--------------------"
Get-ComputerInfo | Select-Object CsName, OsName, WindowsVersion
Get-Process | Sort-Object -Property CPU -Descending | Select-Object -First 5
Get-PSDrive -PSProvider FileSystem | Select-Object Name, Used, Free
```
#### **How to Run:**
1. Save the script as `SystemHealth.ps1`.
2. Open PowerShell as Administrator.
3. Navigate to the script location.
4. Run `./SystemHealth.ps1`

---

### **2. Automated Backup Script**
#### **Description:**
This script copies files from a source directory to a backup directory.
#### **Script:**
```powershell
$source = "C:\ImportantFiles"
$destination = "D:\Backup"
Copy-Item -Path $source -Destination $destination -Recurse -Force
Write-Output "Backup completed successfully."
```
#### **How to Run:**
1. Save the script as `BackupScript.ps1`.
2. Ensure the `C:\ImportantFiles` directory exists.
3. Run `./BackupScript.ps1`.

---

### **3. User Account Creation Script**
#### **Description:**
This script creates a new local user with a predefined password.
#### **Script:**
```powershell
$username = "NewAdmin"
$password = ConvertTo-SecureString "SecureP@ssw0rd" -AsPlainText -Force
New-LocalUser -Name $username -Password $password -FullName "New Admin User" -Description "Created via script"
Add-LocalGroupMember -Group "Administrators" -Member $username
Write-Output "User $username created successfully."
```
#### **How to Run:**
1. Save the script as `CreateUser.ps1`.
2. Open PowerShell as Administrator.
3. Run `./CreateUser.ps1`.

---

### **4. Event Log Analysis Script**
#### **Description:**
This script extracts the last 10 system event logs for analysis.
#### **Script:**
```powershell
Get-EventLog -LogName System -Newest 10 | Format-Table -AutoSize
```
#### **How to Run:**
1. Open PowerShell.
2. Copy and paste the command to execute immediately.

---

### **5. Scheduled Task Creation Script**
#### **Description:**
This script creates a scheduled task to run a PowerShell script at startup.
#### **Script:**
```powershell
$action = New-ScheduledTaskAction -Execute "PowerShell.exe" -Argument "-File C:\Scripts\BackupScript.ps1"
$trigger = New-ScheduledTaskTrigger -AtStartup
Register-ScheduledTask -Action $action -Trigger $trigger -TaskName "BackupTask" -Description "Runs backup at startup" -User "SYSTEM" -RunLevel Highest
Write-Output "Scheduled task created successfully."
```
#### **How to Run:**
1. Save the script as `CreateTask.ps1`.
2. Run as Administrator in PowerShell.
3. Check the task in Task Scheduler.

---

### **Final Notes:**
- Use `Get-Help <command>` for more details on any PowerShell command.
- Modify scripts based on your system and security policies.
- Always test scripts in a safe environment before deploying.
