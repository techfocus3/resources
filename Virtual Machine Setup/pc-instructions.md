# TechFocus III VirtualBox Installation Instructions for Microsoft Windows

The TechFocus III practical sessions will require the use of very specialized software, as such, we will be providing attendees with a virtual environment that already contains all of the tools and sample files we will be using. In order to use this virtual environemnt there are some setup steps that you *must* take prior to the TechFocus III conference.

## Do this in advance of TechFocus!
**Note:** please carry out these instructions several days in advance of the conference so that you have time to troubleshoot any issues. Note that you may need administrator rights on your computer. If you are using a computer issued by your employer, ask your IT department to install the software for you.

### Step 1: Download VirtualBox

Navigate to [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads), and download the VirtualBox installer for "Windows hosts":

![](img/pc/download-1.png) 

Click the "x86/amd64" link. After clicking the link the VirtualBox installer will begin downloading.

![](img/pc/download-2.png) 

### Step 2: Run the installer

Open the EXE file that was downloaded. You may see a security warning like this one:

![](img/pc/download-3.png) 

Click "Run". This will launch the VirtualBox installer: 

![](img/pc/installer-1.png)

Click "Next". You will then see this window:

![](img/pc/installer-2.png)

Click "Next". You will then see this window:

![](img/pc/installer-3.png)

Click "Next". You will then see this window:

![](img/pc/installer-4.png)

Click "Yes". You will then see this window:

![](img/pc/installer-5.png)

Click "Install". You will then see a progress bar that looks like this:

![](img/pc/installer-6.png)

At this point, you may see an alert that looks like this:

![](img/pc/installer-7.png)

Click "Yes". When installation completes, you will see a window that looks like this:

![](img/pc/installer-8.png)

Un-check the box next to "Start Oracle VM Virtualbox 5.0.4 after installation", and then click "Finish"


### Step 3: Install the VirtualBox Extension Pack

Navigate again to [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

Look for the second bullet point that says "VirtualBox 5.0.4 Oracle VM VirtualBox Extension Pack". Click the link that says "All supported platforms". Note that if you encountered issues with VirtualBox 5.0.4 and had to install an older version of VirtualBox, you must install the appropriate/corresponding extension pack version. Otherwise, choose the link pictured here:

![](img/pc/extension-1.png)

After clicking the download link, the extension pack will download to your computer:

![](img/pc/extension-2.png)

Open the extension pack file by double clicking it's icon. This will launch VirtualBox, and you will see the following warning:

![](img/pc/extension-3.png)

Click "Install". Next you will be shown the VirtualBox Personal Use and Evaluation License:

![](img/pc/extension-4.png)

Scroll through and read the license – you must scroll all the way through in order to enable the "agree" button. If you agree to the license, click "I Agree":

Windows may now display the following warning: 

![](img/pc/extension-5.png)

Click "Yes". Next you will see that the extension pack has been sucesfully installed:

![](img/pc/extension-6.png)

### Step 4: Import the virtual machine
TechFocus III Virtal Machine can be downloaded from here: [TechFocus_VM.ova](https://dl.dropboxusercontent.com/u/11471672/TFIII/VirtualBox/TechFocus_VM.ova). This File is 5GB in size and can take a considerable ammount of time to download, depending on the speed of your internet connection. At check-in on Day 1 of TechFocus III, we will be providing the TechFocus Virtual Machine on a USB thumb drive to all attendees, so do not fear if you find downloading this 5GB file to be impossible. Nonetheless, we highly reccommended that you download the TechFocus III Virtual Machine and import it into VirtualBox in advance of TechFocus III, as you may encounter challenges in this process due to some particular characteristic of your computer.

When your download of [TechFocus_VM.ova](https://dl.dropboxusercontent.com/u/11471672/TFIII/VirtualBox/TechFocus_VM.ova) completes, double click the file. This will open VirtualBox and display the following screen:

![](img/pc/import-1.png)

Click "Import". This will begin the Virtual Machine import process, which can take several minutes. You will see a progress bar as this process completes:

![](img/pc/import-2.png)

When the import process completes, you will now see your Virtual Machine listed in the left sidebar of the VirtualBox window. 

![](img/pc/import-3.png)

Click the Virtual Machine's name (TechFocus III). You will now see some of the Virtual Machine's specifications displayed:

![](img/pc/import-4.png)

Click the green "Start" button at the top of the window:

![](img/pc/import-5.png)

This is a critical moment – either the Virtual Machine will sucsesfully boot, or you will see an error that means we are not finished. If you see the following error saying "VT-x/AMD-v hardware acceleration is not available on your system", you will unfortunately be unable to run the TechFocus Virtual Machine on your system:

![](img/pc/virt-err-1.png)

There is a similar error that is less severe – if you see the following error, we will need to enable hardware virtualization in your PC's BIOS. 


If this is a work-issued PC, work with your IT department to 


A new VirtualBox icon will pop up in your dock, called "VirtualBox VM":

![](img/pc/launch-1.png)

Click this icon. You will now see the following notification alerting you that the VirtualMachine is going to start in fullscreen mode:

![](img/pc/launch-2.png)

Click "Switch". The Virtual Machine will now go into full screen mode, and begin to boot. You may see a black screen for a moment. You will also see two notifications at the top of your screen that look like this:

![](img/pc/launch-3.png)

You can dismiss these alerts by clicking the small blue "x" on the right side of the window. When your Virtual Machine finshes booting you will see the following:

![](img/pc/launch-4.png)

This is your Linux (Ubuntu specifically) desktop – This virtual Linux computer is loaded with all of the tools and materials we will be using during the TechFocus III workshops. Congratulations on sucsessfully installing virtualbox and importing your TechFocus Virtual Machine! If at any time you decide that you would like to switch out of fullscreen mode, simply press and hold the ⌘ (command) button on your keyboard, followed by the "F" key. If this does not work, move your mouse all the way to the top of the screen, and when the OS X menu bar appears, click the view menu, and un-check "Full-screen" mode.

![](img/pc/launch-5.png)

This will switch your Virtual Machine to a floating window that is adjustable in size:

![](img/pc/launch-6.png)

When you want to close your Virtual Machine, it is critical that you properly shut it down, just as you would a real computer. To do so, click the gear icon in the upper right hand corner:

![](img/pc/shutdown-1.png)

Next, click "Shut down…"

![](img/pc/shutdown-2.png)

Finally click the large shut down icon that pops up:

![](img/pc/shutdown-3.png)

This will shut down and close your Virtual Machine.

### Technical Assistance
If you encounter any insurmountable errors in setting up your virtual machine, feel free to contact Ben Fino-Radin ([ben_fino-radin@moma.org](mailto:ben_fino-radin@moma.org)) for assistance.




