---
marp: true
footer: 'James Gress - https://jamesgress.com'
paginate: true
theme: default
style: |
  body {
    font-family: 'Courier New', monospace;
  }
  h1 {
    font-size: 50px;
    color: black;
  }
  h2 {
    font-size: 30px;
    color: black;
  }
---

# Ubuntu Monero Mining
![bg right:40%](./img/jamesgress.png)

---

![bg left:40%](./img/jamesgress.png)

# James Gress
## Director Emerging Technologies<br>Generative AI<br>Accenture

<i class="fa-brands fa-x-twitter"></i> 𝕏: [@jmgress](https://twitter.com/jmgress)
<i class="fa-brands fa-linkedin"></i> LinkedIn: - [James Gress](https://linkedin.com/in/jamesgress/)
<i class="fa fa-window-maximize"></i> Blog: [https://jamesgress\.com/](https://jamesgress.com/)
<i class="fa-brands fa-github"></i> GitHub: [jmgress](https://github.com/jmgress)
<i class="fa-brands fa-meetup"></i> Meetup: [Generative AI](https://www.meetup.com/tampa-bay-generative-ai-meetup/)

---

# Note: 

# This is intended for hobbyists as you will not make money.  The computing power alone is more costly than what you will earn in coins.

---

# Create a Bootable USB with Rufus

- **Download Rufus**: Visit the Rufus website at [https://rufus.ie/](https://rufus.ie/) and download the latest version.
- **Prepare USB Drive**: Use a USB drive with a minimum of 4GB space.
- **Launch Rufus**: Run the downloaded Rufus executable file.
- **Configure Rufus Settings**:
  - Select USB drive under “Device”.
  - Click “SELECT” and choose the Ubuntu ISO file.
  - Optionally adjust partition scheme, file system, and cluster size.
- **Start Process**: Click “START”. Confirm data erasure warning.
- **Rufus Bootable USB Creation**: Wait for the completion, indicated by a progress bar.
- **Eject USB**: Safely eject the USB drive after Rufus completes.

---

# Installing XMRig on Ubuntu

- **Update System**: Open a terminal and update your system with `sudo apt update && sudo apt upgrade`.
- **Install Dependencies**: Install necessary build tools and libraries with `sudo apt install git build-essential cmake libuv1-dev libssl-dev libhwloc-dev`.
- **Clone XMRig Repo**: Clone the XMRig GitHub repository using `git clone https://github.com/xmrig/xmrig.git`.
- **Navigate to Directory**: Change into the cloned directory with `cd xmrig`.

---

# Installing XMRig on Ubuntu

- **Create Build Directory**: Create and navigate to a new build directory with `mkdir build && cd build`.
- **Build XMRig**: Run `cmake ..` and then `make` to compile XMRig.
- **Configure Mining Settings**: Edit the `config.json` file in the XMRig folder to set up your mining pool and other preferences.
- **Start Mining**: Execute `./xmrig` to start mining. Ensure you comply with all legal and ethical guidelines related to cryptocurrency mining.

---

# Advanced Settings: Prevent Sleep & Hibernation on Ubuntu

- **Open Terminal**: Press `Ctrl + Alt + T` to open a terminal window.

- **Edit System Config File**:
  - Type `sudo nano /etc/systemd/logind.conf` and press Enter to edit the file with Nano text editor.
  - You might need to enter your password.

- **Modify Lid Close Behavior**:
  - Find the line `#HandleLidSwitch=suspend`. If it's not there, add it.
  - Change it to `HandleLidSwitch=ignore` to prevent sleep when the lid is closed.
  - Uncomment the line (remove the `#` at the beginning) if it's commented.

---

# Advanced Settings: Prevent Sleep & Hibernation on Ubuntu

- **Disable Automatic Suspend**:
  - Similarly, find or add `#HandleSuspendKey=suspend`.
  - Change it to `HandleSuspendKey=ignore` to disable suspend key action.

- **Apply Changes**:
  - Save the file (Ctrl + O, then Enter) and exit (Ctrl + X).
  - Restart the systemd-logind service with `sudo systemctl restart systemd-logind`.


---

# Configuring Screen Lock Settings in Ubuntu

- **Prevent Automatic Screen Lock**:
  - Open "Settings".
  - Navigate to "Privacy" > "Screen Lock".
  - Toggle off the "Automatic Screen Lock" option.
  - Adjust the delay for screen lock as desired, or set to 'Never'.

- **Modify Lock Screen on Suspend**:
  - In the same "Screen Lock" settings:
  - Find the option "Lock Screen on Suspend".
  - Toggle it according to your preference (enable or disable).

---

# Auto-Start XMRig on Ubuntu Boot

- **Create a Script for XMRig**:
  - Open a text editor and create a new script, e.g., `start_xmrig.sh`.
  - Add `#!/bin/bash` at the top of the file.
  - Then, add the command to start XMRig, e.g., `/path/to/xmrig`.
  - Save and close the file. Replace `/path/to/xmrig` with the actual path to your XMRig executable.

- **Make the Script Executable**:
  - Open terminal and navigate to the script's directory.
  - Run `chmod +x start_xmrig.sh` to make the script executable.

---

# Auto-Start XMRig on Ubuntu Boot


- **Edit crontab to Schedule the Script**:
  - In the terminal, type `crontab -e` to edit the crontab file.
  - Add the line `@reboot /path/to/start_xmrig.sh` at the end of the file. Replace `/path/to/start_xmrig.sh` with the full path to your script.
  - Save and exit the editor.

- **Alternative: Use Startup Applications** (GUI method):
  - Open "Startup Applications".
  - Click "Add" and enter the name, command (`/path/to/start_xmrig.sh`), and comment for the new startup application.
  - Click "Add" to confirm.

---

# Auto-Start Performance Monitor on Ubuntu

- **Access Startup Applications**:
  - Search and open "Startup Applications" from the Ubuntu dashboard.

- **Create New Startup Entry**:
  - Click on "Add" to create a new entry.
  - In "Name", enter “Performance Monitor”.
  - In "Command", type `gnome-system-monitor` (or your preferred monitoring tool's command).
  - Optionally, add a description in "Comment".

---

# Auto-Start Performance Monitor on Ubuntu

- **Save and Exit**:
  - Click "Add" to save the new entry.
  - Close the Startup Applications window.

- **Restart/Log Out**:
  - Restart your computer or log out and back in for the changes to take effect.


---

# Instaling Ubuntu

---

<!-- Needed for mermaid, can be anywhere in file except frontmatter -->
<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
  mermaid.initialize({ startOnLoad: true });
</script>

# Mermaid

<div class="mermaid">
gitGraph
    commit
    commit
    branch develop
    checkout develop
    commit
    commit
    checkout main
    merge develop
    commit
    commit
</div>
