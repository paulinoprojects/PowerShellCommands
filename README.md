# PowerShell Crash Course for New Administrators (1 Hour)

## 0-10 min: Introduction to PowerShell

### What is PowerShell?
- A command-line shell and scripting language for Windows.
- More powerful than Command Prompt (cmd).
- Used for automation, administration, and configuration management.

### How to open PowerShell:
- **Windows + X → Windows Terminal (Admin)**
- **Search "PowerShell" → Run as Administrator** (needed for certain commands)

### Basic Commands:
```powershell
Get-Help             # Shows help system
Get-Command         # Lists available commands
Get-Alias           # Shows cmdlet aliases (e.g., `ls` → `Get-ChildItem`)
```

---

## 10-25 min: Essential PowerShell Commands

### Navigating the File System (Like Command Prompt)
```powershell
Get-ChildItem       # List files (like `ls` or `dir`)
Set-Location C:\    # Change directory (like `cd`)
Get-Location        # Show current directory (like `pwd`)
```

### Managing Processes & Services
```powershell
Get-Process         # List running processes
Stop-Process -Name notepad  # Stop a process
Get-Service         # List services
Restart-Service Spooler  # Restart the Print Spooler service
```

### System Information
```powershell
Get-ComputerInfo    # Shows system details
Get-NetIPAddress    # Shows network info
```

---

## 25-40 min: Working with Objects, Variables, and Pipelines

### Understanding Objects in PowerShell
- Everything in PowerShell is an object.
- Example: `Get-Process` returns a list of process objects.

### Using Variables
```powershell
$user = "Administrator"
Write-Output "Hello, $user"
```

### Pipelines (Chaining Commands)
```powershell
Get-Service | Where-Object Status -eq "Running"
Get-Process | Sort-Object CPU -Descending | Select-Object -First 5
```

---

## 40-50 min: Automating with Scripts

### Creating and Running a Script
1. Open Notepad and write:
   ```powershell
   Write-Output "Hello, PowerShell!"
   ```
2. Save as `script.ps1`
3. Run in PowerShell:
   ```powershell
   .\script.ps1
   ```

### Changing Execution Policy (If Needed)
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

---

## 50-60 min: Practical Use Cases

### User Management
```powershell
Get-LocalUser
New-LocalUser -Name "NewUser" -Password (ConvertTo-SecureString "Password123" -AsPlainText -Force)
```

### Event Logs (Checking for Issues)
```powershell
Get-EventLog -LogName System -Newest 10
```

### Networking
```powershell
Test-Connection google.com  # Ping
Get-NetAdapter              # List network adapters
```

---

## Final Notes
- Use `Get-Help <command> -Examples` to learn more.
- Practice daily with simple scripts.
- Automate small tasks to improve efficiency.
