# Auto-Sort Downloads (Linux)

A lightweight background automation setup for **Ubuntu / Linux** that automatically monitors your `Downloads` folder and organizes incoming files (images, videos, etc.) into their respective directories in real-time using `inotify-tools`.

---

## Features

* **Zero-Touch Automation:** Automatically routes downloaded files the moment they finish downloading.
* **Lightweight:** Uses native Linux file system event monitoring (`inotifywait`).
* **Background Service:** Runs silently in the background without keeping a terminal window open.

---

## Installation & Setup Guide

### Step 1: Install Dependencies & Setup Script

1. Open your terminal (`Ctrl` + `Alt` + `T`).
2. Install `inotify-tools` for your specific distribution:
   * **Ubuntu / Debian / Kali / Mint:**
     ```bash
     sudo apt update && sudo apt install inotify-tools -y
     ```
   * **Fedora / RHEL:**
     ```bash
     sudo dnf install inotify-tools -y
     ```
   * **Arch Linux / Manjaro:**
     ```bash
     sudo pacman -S inotify-tools
     ```
3. Create the automation script file:
   ```bash
   nano ~/auto_sort.sh

2. Copy the script content from [script.txt](script.txt) and paste it into the nano editor window.

3. Save and exit (Ctrl + O, press Enter, then Ctrl + X).

### Step 2: Clean Up & Live Test
Before putting it into permanent background mode, test it live to ensure everything is working:

1. Stop any previously running versions of the script:
   ```bash
   pkill -f auto_sort.sh

2. Start the script interactively:
   ```bash
   /bin/bash ~/auto_sort.sh

3. Test it out:
  * Open your web browser.
  * Download any test image or video file.
  * Check your Pictures or Videos folder to confirm the file auto-moved.

### Step 3: Run Permanently in Background
Once you have verified that it works correctly:
1. Press Ctrl + C in your terminal to stop the live test.
2. Push the script to run permanently in the background:
   ```bash
   nohup ~/auto_sort.sh > /dev/null 2>&1 &

### How to Stop the Auto-Sorter
If you ever need to stop or disable the background sorting process, simply run:
   ```bash
   pkill -f auto_sort.sh
    
