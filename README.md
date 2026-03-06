# Windows-Optimization.md

# 💻 Windows OS Optimization & Performance Guide

This guide outlines the standard procedures for optimizing Windows 10/11 for better performance and resolving system lag issues.

# 🟦 Windows Blue Screen of Death (BSOD) Troubleshooting Guide

When a system crashes with a Blue Screen, follow these professional troubleshooting steps to identify and fix the root cause.

---

### 1. 🔍 Identify the Error Code
Every BSOD has a **Stop Code** (e.g., `CRITICAL_PROCESS_DIED`, `MEMORY_MANAGEMENT`, `IRQL_NOT_LESS_OR_EQUAL`). 
- Take a photo of the screen or check **Event Viewer** (Windows Logs > System) after restart.

### 2. 🛠️ Step-by-Step Resolution

#### **Step 1: Boot into Safe Mode**
If the PC is stuck in a boot loop:
- Restart and interrupt the boot process 3 times to enter **Automatic Repair**.
- Go to **Troubleshoot > Advanced options > Startup Settings > Restart**.
- Press **4** or **F4** to start in **Safe Mode**.

#### **Step 2: Run System File Checker (SFC)**
Corrupted system files are a common cause of BSOD.
- Open **CMD as Administrator**.
- Type: `sfc /scannow` and press Enter.

#### **Step 3: Run Check Disk (CHKDSK)**
If the BSOD is caused by Hard Drive/SSD errors:
- In CMD (Admin), type: `chkdsk c: /f /r`
- Type `Y` and restart the PC to let it scan.

#### **Step 4: Memory Diagnostic Tool**
To check if your RAM is faulty:
- Press `Win + R`, type `mdsched.exe`, and press Enter.
- Select **"Restart now and check for problems"**.

#### **Step 5: Driver Rollback or Update**
BSOD often happens after a faulty driver update (especially Display or Network drivers).
- Open **Device Manager**.
- Right-click the suspected driver > **Properties > Driver > Roll Back Driver**.
- If no rollback is available, select **Update Driver**.

#### **Step 6: Uninstall Recent Updates**
If the BSOD started after a Windows Update:
- Go to **Settings > Update & Security > View update history > Uninstall updates**.
- Select the most recent update and click **Uninstall**.

---

### 📊 Common BSOD Error Codes & Fixes


| Error Code | Common Cause | Quick Fix |
| :--- | :--- | :--- |
| **0x0000000A** | Faulty Driver/Incompatible Software | Update Drivers in Safe Mode |
| **0x0000007B** | Hard Drive Controller Issues | Check SATA Mode in BIOS (AHCI/IDE) |
| **0x000000ED** | Corrupted File System | Run `chkdsk /f` |
| **0x00000024** | NTFS Partition Corruption | Run `chkdsk /r` |
| **PAGE_FAULT_IN_NONPAGED_AREA** | Faulty RAM or Antivirus Conflict | Run Memory Diagnostic / Disable AV |

# 🟦 Detailed Step-by-Step Fixes for BSOD Errors

When you encounter specific Blue Screen error codes, follow these professional troubleshooting procedures.

---

### 1️⃣ Error: 0x0000000A (Driver or Software Conflict)
**Scenario:** Occurs when a driver uses an incorrect memory address.
1. **Boot into Safe Mode:** Restart and hold `Shift` while clicking **Restart** > Troubleshoot > Advanced options > Startup Settings > Restart > Press **4**.
2. **Open Device Manager:** Press `Win + X` and select **Device Manager**.
3. **Identify Driver:** Look for any device with a yellow exclamation mark (⚠️).
4. **Update/Uninstall:** Right-click the suspect driver and select **Update Driver** or **Uninstall device**.
5. **Clean Boot:** If the error persists, run `msconfig`, hide all Microsoft services, and disable all startup items to find the faulty software.

### 2️⃣ Error: 0x0000007B (Inaccessible Boot Device)
**Scenario:** Windows cannot communicate with the Hard Drive/SSD during startup.
1. **Enter BIOS/UEFI:** Restart and tap `F2`, `F12`, or `Del` repeatedly.
2. **Locate SATA Mode:** Go to **Storage/Advanced** settings and find **SATA Configuration**.
3. **Switch Mode:** If it is set to **IDE**, change it to **AHCI**. If it is **AHCI**, try **RAID** or **IDE**.
4. **Save and Exit:** Press `F10` to save and restart.
5. **Command Prompt:** If it still fails, boot from a Windows USB, open **Command Prompt**, and run `bootrec /fixmbr` and `bootrec /fixboot`.

### 3️⃣ Error: 0x000000ED (Unmountable Boot Volume)
**Scenario:** The file system on the boot drive is corrupted.
1. **Automatic Repair:** Allow Windows to enter the **Automatic Repair** screen after 2-3 failed boots.
2. **Advanced Options:** Navigate to **Troubleshoot** > **Advanced Options** > **Command Prompt**.
3. **Run Repair:** Type `chkdsk c: /f` and press **Enter**. (Note: Change `c:` if your OS is on a different drive).
4. **Restart:** Once the scan reaches 100%, type `exit` and click **Continue to Windows**.

### 4️⃣ Error: 0x00000024 (NTFS File System Error)
**Scenario:** Severe corruption within the NTFS disk partition.
1. **Admin CMD:** Search for **CMD**, right-click, and select **Run as Administrator**.
2. **Deep Scan:** Type `chkdsk c: /r` and press **Enter**.
3. **Schedule Scan:** Type `Y` when asked to schedule the scan for the next restart.
4. **Execute:** Restart the PC. Windows will perform a 5-stage repair. **Do not turn off the power** during this process (it may take 1-2 hours).

### 5️⃣ Error: PAGE_FAULT_IN_NONPAGED_AREA
**Scenario:** Data requested is not found in memory (Faulty RAM or Antivirus conflict).
1. **Memory Diagnostic:** Press `Win + R`, type `mdsched.exe`, and select **Restart now and check for problems**.
2. **Observe Results:** The PC will restart and test your RAM. If it finds errors, the RAM stick may need replacement.
3. **Check Virtual Memory:** Go to **System Properties** > **Advanced** > **Settings (Performance)** > **Advanced** > **Change**. Ensure **"Automatically manage paging file size"** is checked.
4. **Disable Antivirus:** If the error occurs after installing an Antivirus, uninstall it in **Safe Mode** to check for compatibility.
-----
##  BitLocker Recovery Issues
**Scenario:** User is locked out and the system asks for a 48-digit Recovery Key.
1. Log in to the **Microsoft Azure Portal** (://azure.com).
2. Search for the **Device Name**.
3. Retrieve the **BitLocker Recovery Key** and provide it to the user.
4. *Note: Advise users to never store the key on the same device.*


# 💻 Windows System Support & Troubleshooting

This document covers common OS-level issues and hardware-related troubleshooting steps.

| # | Task | Emoji | Action / Benefit |
| :--- | :--- | :--- | :--- |
| 1 | **Temp Cleanup** | 🧹 | Run `%temp%`, `temp`, and `prefetch` to delete junk files. |
| 2 | **Startup Apps** | 🏎️ | Disable high-impact apps in **Task Manager > Startup**. |
| 3 | **Power Plan** | 🔋 | Switch to **High Performance** in Control Panel for better CPU speed. |
| 4 | **Visual Effects** | ✨ | Select **"Adjust for best performance"** in Advanced System Settings. |
| 5 | **Virtual Memory** | 💾 | Manually set Paging File to 1.5x of your RAM size. |
| 6 | **Storage Sense** | 📦 | Enable **Storage Sense** to auto-delete temporary files periodically. |
| 7 | **Registry Tweak** | ⚙️ | Set `MenuShowDelay` to `20` in Registry Editor for snappier menus. |
| 8 | **Background Apps** | 🛑 | Turn off **"Background apps"** in Privacy settings. |
| 9 | **Game Mode** | 🛡️ | Enable **"Game Mode"** to prioritize system resources for active tasks. |
| 10 | **Disk Cleanup** | 📀 | Use `cleanmgr` to remove system junk and old Windows updates. |
| 11 | **Service Optimization** | ⚙️ | Disable services like **Connected User Experiences and Telemetry**. |
| 12 | **Delivery Optimization** | 📡 | Turn off **"Allow downloads from other PCs"** to save bandwidth. |
| 13 | **GPU Scheduling** | 🖥️ | Enable **Hardware-accelerated GPU scheduling** in Graphics Settings. |
| 14 | **Fast Startup** | ⚡ | Turn off **"Fast Startup"** to ensure a clean boot every time. |
| 15 | **Drive Optimization** | 🧩 | Optimize SSDs or Defragment HDDs via **"Defragment and Optimize Drives"**. |
| 16 | **Transparency** | 🚫 | Disable **Transparency Effects** in Personalization to save GPU power. |
| 17 | **Indexing Options** | 🔍 | Limit indexing to essential folders to reduce background disk usage. |
| 18 | **Notifications** | 📢 | Turn off unnecessary **Notifications & Actions** to reduce CPU spikes. |
| 19 | **Quick Access** | 📂 | Uncheck **"Show frequently used folders"** for faster File Explorer. |
| 20 | **Optional Updates** | 🔄 | Install **Optional Driver Updates** from Windows Settings. |

---

# 🚀 Windows OS Optimization: Step-by-Step Guide

Follow these 20 steps to improve system performance and reduce lag on Windows 10/11.

---

### 1. 🧹 Cleanup Temporary Files
- Press `Win + R`, type `%temp%`, and delete all files.
- Press `Win + R`, type `temp`, and delete all files.
- Press `Win + R`, type `prefetch`, and delete all files.

### 2. 🏎️ Disable Startup Apps
- Open **Task Manager** (Ctrl + Shift + Esc).
- Go to the **Startup** tab.
- Right-click and **Disable** unnecessary apps (e.g., Cortana, Spotify, Steam).

### 3. 🔋 Enable High Performance Power Plan
- Go to **Control Panel** > **Hardware and Sound** > **Power Options**.
- Select **High Performance** to ensure the CPU runs at maximum speed.

### 4. ✨ Adjust for Best Performance
- Search for "Adjust the appearance and performance of Windows".
- Select **"Adjust for best performance"** to disable heavy animations.

### 5. 💾 Virtual Memory (Paging File)
- Go to **System Properties** > **Advanced** > **Settings** > **Advanced** > **Virtual Memory**.
- Set the **Initial size** to 1.5x of your physical RAM.

### 6. 📦 Enable Storage Sense
- Go to **Settings** > **System** > **Storage**.
- Turn **On** Storage Sense to auto-delete junk files.

### 7. ⚙️ Registry Tweak (Faster Menus)
- Open `regedit` (Registry Editor).
- Go to `HKEY_CURRENT_USER\Control Panel\Desktop`.
- Change **MenuShowDelay** from 400 to **20**.

### 8. 🛑 Disable Background Apps
- Go to **Settings** > **Privacy** > **Background apps**.
- Toggle the switch to **Off** to save RAM and CPU.

### 9. 🛡️ Enable Game Mode
- Go to **Settings** > **Gaming** > **Game Mode**.
- Turn it **On** to prioritize system resources for active tasks.

### 10. 📀 Run Disk Cleanup (cleanmgr)
- Press `Win + R`, type `cleanmgr`, and click **Clean up system files**.
- Select the C: drive and remove old Windows updates and cache.

### 11. ⚙️ Disable Unnecessary Services
- Open `services.msc`.
- Disable **"Connected User Experiences and Telemetry"** to stop background data collection.

### 12. 📡 Turn Off Delivery Optimization
- Go to **Settings** > **Update & Security** > **Delivery Optimization**.
- Turn off **"Allow downloads from other PCs"** to save bandwidth.

### 13. 🖥️ Hardware Accelerated GPU Scheduling
- Go to **Settings** > **Display** > **Graphics Settings**.
- Turn **On** "Hardware-accelerated GPU scheduling" to reduce CPU bottleneck.

### 14. ⚡ Disable Fast Startup
- Go to **Power Options** > **Choose what the power buttons do**.
- Uncheck **"Turn on fast startup"** to ensure a clean system boot.

### 15. 🧩 Optimize Drives (Defrag/Trim)
- Search for **"Defragment and Optimize Drives"**.
- Click **Optimize** for SSDs (Trim) or HDDs (Defragment).

### 16. 🚫 Disable Transparency Effects
- Go to **Settings** > **Personalization** > **Colors**.
- Turn off **Transparency effects** to reduce GPU load.

### 17. 🔍 Limit Search Indexing
- Go to **Settings** > **Search** > **Searching Windows**.
- Select **Classic** mode to reduce background disk usage.

### 18. 📢 Disable Notifications
- Go to **Settings** > **System** > **Notifications & actions**.
- Turn off unnecessary notifications to reduce system interrupts.

### 19. 📂 Speed Up File Explorer
- Open **File Explorer Options** > **General**.
- Uncheck **"Show frequently used folders in Quick access"**.

### 20. 🔄 Install Optional Driver Updates
- Go to **Windows Update** > **View optional updates**.
- Install the latest **Driver updates** for hardware stability.

---
## 🛠️ Essential Maintenance Commands (Admin)
- `sfc /scannow` : Repairs corrupted system files.
- `chkdsk c: /f` : Fixes file system errors on the drive.
- `ipconfig /flushdns` : Resolves network browsing lag.


---

## 🐢 Troubleshooting Slow App Launch Issues

If applications are taking too long to open, follow these technical troubleshooting steps:

### 1. 🚦 Check for Background Resource Hogging
- Open **Task Manager** (Ctrl + Shift + Esc).
- Sort by **CPU** and **Memory** columns.
- Identify any process using more than 20-30% CPU while idle.
- **Action:** Right-click and **End Task** for unnecessary third-party apps.

### 2. ⚡ Clear Prefetch and Superfetch (SysMain)
Windows uses these to "speed up" apps, but if the cache is corrupted, it slows them down.
- Press `Win + R`, type `prefetch`, and delete all files.
- Press `Win + R`, type `services.msc`, find **SysMain**, right-click and select **Restart**.

### 3. 🧹 Clean Boot (To identify conflicts)
Sometimes an antivirus or a third-party service slows down other apps.
- Press `Win + R`, type `msconfig`.
- Go to the **Services** tab > Check **"Hide all Microsoft services"** > Click **Disable all**.
- Go to **Startup** tab > Open **Task Manager** > **Disable** all items.
- Restart the PC and see if apps open faster.

### 4. 🛠️ Repair System Image (DISM & SFC)
Corrupted Windows files can slow down the execution of `.exe` files.
- Open **CMD as Administrator**.
- Run: `DISM /Online /Cleanup-Image /RestoreHealth`
- After it finishes, run: `sfc /scannow`

### 5. 🖥️ Enable Hardware-Accelerated GPU Scheduling
This offloads some UI tasks to the GPU, making app windows pop up faster.
- Go to **Settings > System > Display > Graphics Settings**.
- Turn **On** "Hardware-accelerated GPU scheduling" and **Restart**.

### 6. 💾 Check Disk Health & Fragmentation
If you have an HDD, fragmentation is a major reason for slow app starts.
- Search for **"Defragment and Optimize Drives"**.
- For SSD: Click **Optimize** (Trim).
- For HDD: Click **Analyze** and then **Optimize**.

##  Printer Spooler Service Fix
**Scenario:** Documents are stuck in the print queue or printer shows "Offline".
1. Press `Win + R`, type `services.msc`, and hit Enter.
2. Find **Print Spooler**, right-click it, and select **Restart**.
3. If it fails, clear the spooler cache:
   - Stop Print Spooler.
   - Delete files in `C:\Windows\System32\spool\PRINTERS`.
   - Start Print Spooler again.


---


