# GoGo Board Firmware Update Guide

This guide explains how to update the firmware of the **GoGo Board 7** using the update utility available at [https://code.gogoboard.org](https://code.gogoboard.org).

---

## Table of Contents
- [When to Update](#when-to-update)
- [Update Scenarios](#update-scenarios)
  - [Automated Update (Firmware v2.3.8 or newer)](#1-automated-update-firmware-v238-or-newer)
  - [Manual Update (Firmware older than v2.3.8)](#2-manual-update-firmware-older-than-v238)
- [Summary](#summary)

---

## When to Update
- The firmware update utility is built into the web app.
- When a new firmware version is available, the **hamburger menu** (top right corner) will display a **red dot indicator**.
- To access the update utility:
  1. Click the hamburger button.
  2. Select **Update Firmware** from the menu.  

     <img src="images/01 firmware update notification and menu.png" alt="Update Firmware Menu" width="50%"/>

---

## Update Scenarios
There are two possible update paths depending on your current firmware version.

---

### 1. Automated Update (Firmware v2.3.8 or newer)
If your GoGo Board 7 is running firmware **2.3.8 or later**, the update process is automated.

1. The utility will show the **current firmware version** and the **new version** available, along with an **Install** button.  
   <img src="images/02 new firmware dashboard.png" alt="Install Button" width="60%"/>

2. Click **Install**, then confirm by clicking **Understand**.  

   <img src="images/03 information.png" alt="Confirm Update" width="60%"/>

3. A popup window will appear. Select **ESP32-S3** or **USB/JTAG/serial debug unit**, then press **Connect**.  

   <img src="images/04 select the target.png" alt="Device Selection" width="50%"/>

4. The GoGo Board will reset and begin the firmware update.  

   <img src="images/05 update in progress.png" alt="Updating Firmware" width="60%"/>
5. When the update completes, a **success message** will be displayed.  

   <img src="images/06 Update success.png" alt="Update Success" width="60%"/>
6. The utility will confirm that the latest firmware is installed.  

   <img src="images/07 dashboard with latest firmware.png" alt="Latest Firmware Dashboard" width="60%"/>

---

### 2. Manual Update (Firmware older than v2.3.8)
If your GoGo Board 7 is running firmware **older than 2.3.8**, you must use the manual update process.

1. Press **Update** and the manual update utility will appear.  

   <img src="images/10 advanced installer.png" alt="Manual Update Utility" width="50%"/>

The manual firmware update utility can also be accessed from the following URL:

> https://install-firmware.gogoboard.org/

2. From the **Select firmware** dropdown list, choose the desired firmware (default is the latest GoGo Board 7 firmware).  

   <img src="images/11 selecting the firmwrae.png" alt="Select Firmware" width="50%"/>
   
3. Put the GoGo Board into **bootloader mode**:
   - Hold the **Boot** button (near the power on/off switch*) while turning on the board.
   - The screen should display a **solid white** background.
4. Press **Connect**. A device selection window will appear.
5. Select **ESP32-S3** or **USB/JTAG/serial debug unit**, then press **Connect**.
6. Follow the on-screen instructions until the firmware update completes.
7. **Power cycle the board** (turn it off and back on).  
   The firmware update is now complete.

> \* The boot button is either located on the edge or on the back side of the GoGo Board, depending on the version you have. E.g. GoGo 7C, the button is on the back side. 

---

## Summary
- Use **Automated Update** if your firmware is **v2.3.8 or newer**.  
- Use **Manual Update** if your firmware is **older than v2.3.8**.  
- Always confirm the update utility shows the latest firmware after completion.
