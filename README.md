# Windows-Optimization.md

# 💻 Windows OS Optimization & Performance Guide

This guide outlines the standard procedures for optimizing Windows 10/11 for better performance and resolving system lag issues.

  # 💻 Windows System Support & Troubleshooting

This document covers common OS-level issues and hardware-related troubleshooting steps.

---

##  Blue Screen of Death (BSOD) Troubleshooting
**Scenario:** The system crashes with a blue error screen.
1. Restart the PC and boot into **Safe Mode**.
2. Run Command Prompt as Admin and type: `sfc /scannow`.
3. Check **Event Viewer** (Windows Logs > System) for critical errors.
4. Update or Rollback **Display/Network Drivers** in Device Manager.


##  BitLocker Recovery Issues
**Scenario:** User is locked out and the system asks for a 48-digit Recovery Key.
1. Log in to the **Microsoft Azure Portal** (://azure.com).
2. Search for the **Device Name**.
3. Retrieve the **BitLocker Recovery Key** and provide it to the user.
4. *Note: Advise users to never store the key on the same device.*


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


