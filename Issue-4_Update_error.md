# Issue 4: Windows Update Error - "We Couldn't Complete the Update. Undoing Changes."

https://www.thewindowsclub.com/we-couldnt-complete-the-updates-undoing-changes

## Problem:
Sarah is receiving an error message when trying to run Windows Update, stating, "We couldn't complete the update. Undoing changes." This error prevents the update from being installed, and Windows rolls back the changes.

## Potential Causes:
- **Corrupted Update Files**: The update process may have been interrupted or corrupted.
- **Driver Conflicts**: A recent update may have caused a conflict with hardware drivers, preventing the update from completing.
- **Insufficient Disk Space**: There may not be enough space on the system drive to complete the update.
- **Windows Update Service Issues**: The Windows Update service may have encountered an error or be stuck in a bad state.
- **Third-Party Software Conflicts**: Security software or other third-party applications may interfere with the update process.

## Tests/Questions:
1. **Check Disk Space:**
   - Ask Sarah to check if there is sufficient disk space on her primary drive (usually `C:`) for the update. Go to **Settings > System > Storage** to verify available space.
2. **Run Windows Update Troubleshooter:**
   - Suggest running the built-in **Windows Update Troubleshooter** by going to **Settings > Update & Security > Troubleshoot > Windows Update**.
3. **Check for Update History:**
   - Ask Sarah to check the **Update History** in **Settings > Update & Security > Windows Update > View update history** to see if there are any failed updates listed.
4. **Look for Error Codes:**
   - Ask if there is any error code provided along with the message. These codes can be used to look up more specific solutions for the issue.
5. **Disable Antivirus and Security Software:**
   - Suggest temporarily disabling any third-party antivirus or security software that might be blocking the update.
6. **Check Windows Update Service:**
   - Ask Sarah to check if the **Windows Update service** is running. She can do this by typing "services.msc" in the Windows search bar and checking that the **Windows Update** service is set to **Automatic** and is running.

## Suggested Fixes:
1. **Free Up Disk Space:**
   - If there is insufficient disk space, suggest deleting unnecessary files or using **Disk Cleanup** to free up space.
2. **Reset Windows Update Components:**
   - Reset the **Windows Update components** by stopping the **Windows Update service**, renaming the update cache folders (SoftwareDistribution and Catroot2), and restarting the service. This can be done using the following commands in Command Prompt (run as Administrator):
     ```bash
     net stop wuauserv
     ren C:\Windows\SoftwareDistribution SoftwareDistribution.old
     ren C:\Windows\System32\catroot2 Catroot2.old
     net start wuauserv
     ```
3. **Install the Update Manually:**
   - Suggest downloading the update manually from the **Windows Update Catalog** (https://www.catalog.update.microsoft.com/Home.aspx) using the update's KB number.
4. **Run the System File Checker:**
   - Ask Sarah to run **System File Checker** to repair any corrupted system files. She can do this by opening **Command Prompt (Admin)** and running:
     ```bash
     sfc /scannow
     ```
5. **Perform a System Restore:**
   - If the issue started after a specific update, Sarah can try performing a **System Restore** to revert the system back to a point before the update was applied.
6. **Check for Driver Updates:**
   - Ensure all drivers, especially those related to critical hardware like the graphics card or network adapter, are up to date.
