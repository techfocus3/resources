# TechFocus III VirtualBox Installation Instructions for Macintosh OS X

The TechFocus III practical sessions will require the use of very specialized software, as such, we will be providing attendees with a virtual environment that already contains all of the tools and sample files we will be using. In order to use this virtual environemnt there are some setup steps that you *must* take prior to the TechFocus III conference.

## Do this in advance of TechFocus!
**Note:** please carry out these instructions several days in advance of the conference so that you have time to troubleshoot any issues. Note that you **must** have administrator rights on your computer, or use the username and password of an administrative account. If you are using a computer issued by your employer, ask your IT department to install the software for you. 

### Step 1: Download VirtualBox

Navigate to [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads), and download the VirtualBox installer for Mac OS X:

![](../img/mac/mac-installer.png) 

Click the "amd64" link. After clicking the link the VirtualBox installer will begin downloading.

![](../img/mac/download.png)

### Step 2: Run the installer

Open the DMG file that was downloaded. This will open a Finder window that looks like this:

![](../img/mac/dmg.png)

Double click the "VirtualBox.pkg" icon. This will run the VirtualBox Installer. The first window you will see looks like this:

![](../img/mac/installer-1.png)

Click "continue". You will then see this window:

![](../img/mac/installer-2.png)

Click "continue". You will then see this window:

![](../img/mac/installer-3.png)

Click "Install". The installer will now ask for your password:

![](../img/mac/installer-4.png)

After entering your password, or administrator's password, and clicking "Install Software", you will see a series of progress bars as the software is installed:

![](../img/mac/installer-5.png)

Eventually you will see this window, indicating that the software was sucsessfully installed.

![](../img/mac/installer-6.png)

Click "Close".

### Step 3: Install the VirtualBox Extension Pack

Navigate again to [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

Look for the second bullet point that says "VirtualBox 5.0.4 Oracle VM VirtualBox Extension Pack". Click the link that says "All supported platforms". Note that if you encountered issues with VirtualBox 5.0.4 and had to install an older version of VirtualBox, you must install the appropriate/corresponding extension pack version. Otherwise, choose the link pictured here:

![](../img/mac/extension-pack.png)

After clicking the download link, the extension pack will download to your computer:

![](../img/mac/extension-pack-1.png)

Open the extension pack file by double clicking it's icon. This will launch VirtualBox, and you will see the following warning:

![](../img/mac/extension-pack-2.png)

Click "Install". Next you will be shown the VirtualBox Personal Use and Evaluation License:

![](../img/mac/extension-pack-3.png)

Scroll through and read the license – you must scroll all the way through in order to enable the "agree" button. If you agree to the license, click "I Agree":

![](../img/mac/extension-pack-4.png)

VirtualBox will now again ask for your administrative password:

![](../img/mac/extension-pack-5.png)

Enter your password, and click "OK". You will very quickly see the following notification indicating that the VirtualBox Extension Pack has been successfully installed:

![](../img/mac/extension-pack-6.png)

### Step 4: Import the virtual machine
TechFocus III Virtal Machine can be downloaded from here: [TechFocus_VM.ova](https://dl.dropboxusercontent.com/u/11471672/TFIII/VirtualBox/TechFocus_VM.ova). This File is 5GB in size and can take a considerable ammount of time to download, depending on the speed of your internet connection. At check-in on Day 1 of TechFocus III, we will be providing the TechFocus Virtual Machine on a USB thumb drive to all attendees, so do not fear if you find downloading this 5GB file to be impossible. Nonetheless, we highly reccommended that you download the TechFocus III Virtual Machine and import it into VirtualBox in advance of TechFocus III, as you may encounter challenges in this process due to some particular characteristic of your computer.

When your download of [TechFocus_VM.ova](https://dl.dropboxusercontent.com/u/11471672/TFIII/VirtualBox/TechFocus_VM.ova) completes, double click the file. This will open VirtualBox and display the following screen:

![](../img/mac/import-1.png)

Click "Import". This will begin the Virtual Machine import process, which can take several minutes. You will see a progress bar as this process completes:

![](../img/mac/import-2.png)

When the import process completes, you will now see your Virtual Machine listed in the left sidebar of the VirtualBox window. Click the Virtual Machine's name (TechFocus III), and click the green "Start" button at the top of the window:

![](../img/mac/import-4.png)

A new VirtualBox icon will pop up in your dock, called "VirtualBox VM":

![](../img/mac/launch-1.png)

Click this icon. You will now see the following notification alerting you that the VirtualMachine is going to start in fullscreen mode:

![](../img/mac/launch-2.png)

Click "Switch". The Virtual Machine will now go into full screen mode, and begin to boot. You may see a black screen for a moment. You will also see two notifications at the top of your screen that look like this:

![](../img/mac/launch-3.png)

You can dismiss these alerts by clicking the small blue "x" on the right side of the window. When your Virtual Machine finshes booting you will see the following:

![](../img/mac/launch-4.png)

This is your Linux (Ubuntu specifically) desktop – This virtual Linux computer is loaded with all of the tools and materials we will be using during the TechFocus III workshops. Congratulations on sucsessfully installing virtualbox and importing your TechFocus Virtual Machine! If at any time you decide that you would like to switch out of fullscreen mode, simply press and hold the ⌘ (command) button on your keyboard, followed by the "F" key. If this does not work, move your mouse all the way to the top of the screen, and when the OS X menu bar appears, click the view menu, and un-check "Full-screen" mode.

![](../img/mac/launch-5.png)

This will switch your Virtual Machine to a floating window that is adjustable in size:

![](../img/mac/launch-6.png)

When you want to close your Virtual Machine, it is critical that you properly shut it down, just as you would a real computer. To do so, click the gear icon in the upper right hand corner:

![](../img/mac/shutdown-1.png)

Next, click "Shut down…"

![](../img/mac/shutdown-2.png)

Finally click the large shut down icon that pops up:

![](../img/mac/shutdown-3.png)

This will shut down and close your Virtual Machine.

### Technical Assistance
If you encounter any insurmountable errors in setting up your virtual machine, feel free to contact Ben Fino-Radin ([ben_fino-radin@moma.org](mailto:ben_fino-radin@moma.org)) for assistance.




