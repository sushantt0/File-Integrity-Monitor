# File Integrity Monitor

A simple **PowerShell ISE-based file integrity monitoring (FIM)** tool.  
This script lets you generate a baseline of file hashes for a target folder and then continuously monitor that folder for **file changes, creations, or deletions**.  

## Features
- Uses **SHA512 hashing** to detect changes with high accuracy.  
- Supports two modes:
  - **Collect Baseline** → Creates a baseline file (`baseline.txt`) containing paths and hashes of all files in the `Files` folder.  
  - **Monitor Mode** → Continuously monitors the `Files` folder against the baseline, detecting:
    - **New files** (not in baseline)  
    - **Modified files** (hash mismatch)  
    - **Deleted files** (baseline entry missing)  
- Console notifications with color highlighting for each event.  
- Designed to run in **PowerShell ISE** for interactive monitoring.


## Usage
1. Place the script in a folder alongside a subfolder called `Files`.  
   - All files inside `Files` will be monitored.  

2. Open **PowerShell ISE** and load the script.

3. Run the script (F5 or click Run Script).

4. Choose an option when prompted:
   - **A** → Collect new baseline  
   - **B** → Begin monitoring using existing baseline  

## Example Workflow
1. First, choose **A** to generate `baseline.txt`.  
2. Then, re-run and choose **B** to start monitoring.  
3. Modify, create, or delete files inside `Files` and watch the console notifications:
   - ✅ New file created → Green  
   - ⚠️ File changed → Yellow  
   - ❌ File deleted → Dark Red  

## Requirements
- **PowerShell ISE** (comes with Windows by default)  
- Permission to run scripts on your system

## Notes
- Hashing uses **SHA512**, which is computationally heavy but very secure.  
- The monitoring loop runs indefinitely until stopped manually (press `CTRL + C` in the console pane).  
- `baseline.txt` is overwritten each time you collect a new baseline.  






