# Easy PowerShell Lab Exercises

## **Lab 1: Basic Navigation & Commands**
### **Objective:** Learn to navigate the file system and use basic commands.

### **Steps:**
1. Open PowerShell.
2. Check the current directory:
   ```powershell
   Get-Location
   ```
3. List all files and folders in `C:\Windows`:
   ```powershell
   Get-ChildItem C:\Windows
   ```
4. Navigate to the `Documents` folder:
   ```powershell
   Set-Location $HOME\Documents
   ```
5. Create a new folder called `PowerShellLab`:
   ```powershell
   New-Item -ItemType Directory -Path PowerShellLab
   ```
6. Navigate into `PowerShellLab` and verify your location:
   ```powershell
   Set-Location PowerShellLab
   Get-Location
   ```

---

## **Lab 2: Working with Files & Content**
### **Objective:** Create, modify, and read text files.

### **Steps:**
1. Inside `PowerShellLab`, create a text file called `testfile.txt`:
   ```powershell
   New-Item -ItemType File -Name testfile.txt
   ```
2. Write some text into the file:
   ```powershell
   Set-Content -Path testfile.txt -Value "Hello, this is my first PowerShell file!"
   ```
3. Read the contents of the file:
   ```powershell
   Get-Content testfile.txt
   ```
4. Append more text to the file:
   ```powershell
   Add-Content -Path testfile.txt -Value "Appending another line."
   ```
5. Verify the changes:
   ```powershell
   Get-Content testfile.txt
   ```

---

## **Lab 3: Managing Processes & Services**
### **Objective:** Learn how to manage running processes and services.

### **Steps:**
1. List all running processes:
   ```powershell
   Get-Process
   ```
2. Find the `notepad` process (if running):
   ```powershell
   Get-Process -Name notepad
   ```
3. Open Notepad:
   ```powershell
   Start-Process notepad
   ```
4. Stop the Notepad process:
   ```powershell
   Stop-Process -Name notepad -Force
   ```
5. List all services running on the system:
   ```powershell
   Get-Service
   ```
6. Check the status of the Print Spooler service:
   ```powershell
   Get-Service -Name Spooler
   ```
7. Restart the Print Spooler service:
   ```powershell
   Restart-Service -Name Spooler
   ```

---

## **Lab 4: Working with Users**
### **Objective:** Create, modify, and check user accounts.

### **Steps:**
1. List all local users:
   ```powershell
   Get-LocalUser
   ```
2. Create a new local user named `TestUser`:
   ```powershell
   New-LocalUser -Name "TestUser" -Password (ConvertTo-SecureString "Test@123" -AsPlainText -Force) -FullName "Test User" -Description "PowerShell Test User"
   ```
3. Check if the user was created successfully:
   ```powershell
   Get-LocalUser -Name "TestUser"
   ```
4. Disable the user account:
   ```powershell
   Disable-LocalUser -Name "TestUser"
   ```
5. Enable the user account again:
   ```powershell
   Enable-LocalUser -Name "TestUser"
   ```
6. Delete the user account:
   ```powershell
   Remove-LocalUser -Name "TestUser"
   ```

---

## **Lab 5: Automating with Scripts**
### **Objective:** Create and run a simple PowerShell script.

### **Steps:**
1. Open Notepad and type the following script:
   ```powershell
   Write-Output "Hello, this is my first PowerShell script!"
   Start-Sleep -Seconds 3
   Write-Output "PowerShell is fun!"
   ```
2. Save it as `script.ps1` inside `PowerShellLab`.
3. Run the script in PowerShell:
   ```powershell
   .\script.ps1
   ```
4. Modify the script to display the current date and time:
   ```powershell
   Write-Output "Current Date and Time: $(Get-Date)"
   ```

---

## **Bonus Lab: Networking Commands**
### **Objective:** Learn basic networking-related commands.

### **Steps:**
1. Check your system's IP address:
   ```powershell
   Get-NetIPAddress
   ```
2. Test connectivity to Google:
   ```powershell
   Test-Connection google.com -Count 4
   ```
3. Get information about your network adapter:
   ```powershell
   Get-NetAdapter
   ```
4. Display the system’s firewall rules:
   ```powershell
   Get-NetFirewallRule
   ```

---

## **Final Notes:**
- Use `Get-Help <command>` to understand any PowerShell command.
- Try modifying the commands to see how they work with different parameters.
- Experiment by writing simple scripts to automate tasks.

