# PowerShell Learning Lab Setup

## 🔧 Setting Up a PowerShell Learning Lab

### 1️⃣ Choose Your Lab Environment
You need a **test environment** to practice without affecting your main system. Here are two options:

#### Option 1: Virtual Machine (Recommended)
- Install **Windows Server 2019/2022** or **Windows 10/11** in a virtualized environment.
- Use **Hyper-V** (built into Windows Pro) or **VirtualBox/VMware**.
- Create a **test domain** (for Active Directory automation).

#### Option 2: Windows Sandbox
- If you’re using Windows 10/11 Pro, enable **Windows Sandbox** for an isolated, temporary test environment.

---

### 2️⃣ Install PowerShell 7 (Latest Version)
PowerShell 7 is cross-platform and more powerful than Windows PowerShell.

- Download from: [PowerShell GitHub](https://github.com/PowerShell/PowerShell)
- Install using PowerShell:
  ```powershell
  winget install --id Microsoft.Powershell --source winget
