# TechFocus III: Caring for Software-based Art


 ```
______ _     _      _                       _               __  _____  __  
|  _  (_)   | |    (_)                     (_)             /  ||  _  |/  | 
| | | |_ ___| | __  _ _ __ ___   __ _  __ _ _ _ __   __ _  `| || |/' |`| | 
| | | | / __| |/ / | | '_ ` _ \ / _` |/ _` | | '_ \ / _` |  | ||  /| | | | 
| |/ /| \__ \   <  | | | | | | | (_| | (_| | | | | | (_| | _| |\ |_/ /_| |_
|___/ |_|___/_|\_\ |_|_| |_| |_|\__,_|\__, |_|_| |_|\__, | \___/\___/ \___/
                                       __/ |         __/ |                 
                                      |___/         |___/                  
This document is an introduction and tutorial to the practice of disk imaging. It was produced by Ben Fino-Radin for the American Institute for Conservation of Historic and Artistic Work's third TechFocus workshop, TechFocus III: Caring for Software-based Art, hosted by the Solomon R. Guggenheim Museum, New York, NY on September 25th-26th, 2015.
```

### What is a disk image?
A disk image is a file that usually contains a complete and linear "recording" of what your computer sees when it looks at a hard drive, USB drive, CD, DVD, or any other kind of digital carriers of information.

###  Why make disk images?
* To preserve the entireity of a disk as it was delivered by an artist
* To preserve a backup of a dedicated computer that is integral to an artwork
* To "boot" a dedicated computer in a virtual or emulated environment
* To preseve a deeper perspective of the artist provided media, including deleted files

### You will need
1. A way to safely connect the media to your workstation
2. Software for creating the disk image

### Safely connecting media
Most common modern operating systems (Mac and PC) write hidden data to media when it is attached. When handling media that warrants disk imaging, it is almost always advisable to to implmenent measures to prevent any kind of inadvertant modification of the artist provided media. The most commonly used method is to use a hardware device called a write-blocker. A write blocker acts as an intermediary between your workstation, and the media you wish to inspect or disk image. A search online for "write-blocker" will yield reults for various vendors that sell various makes and models of write-blockers. In order to choose the correct model of write blocker, consider the interface formats you face on a day-to-day basis:

* SCSI
* PATA / IDE
* SATA
* USB 2.0
* USB 3.0
* Firewire 400
* Firewire 800

Although the physical form factor of USB 2.0 and 3.0 are identical – their interoperability for write blocking purposes is not reliable. A USB 2.0 write blocker should only be used for USB 2.0 devices, and a USB 3.0 write blcoker should only be used for USB 3.0 devices. At the time of writing there are no commercially available Thunderbolt write blockers.

###  A few tools for creating disk images
* dd – aka Direct Duplicate
* ddrescue
* guymager

Although there are many many more tools one could use for disk imaging, for the purposes of this workshop we will be sticking with these three tools as examples. It warrants mentioning that all three are free and open source.

### Handing control of the USB thumb drive to your Virtual Machine
For this disk imaging exercise we will be making a disk image of the TechFocus USB thumb drive that you were provided at check-in. First – make sure that your Linux virtual machine is running, then plug in the TechFocus USB thumb drive. If the USB thumb drive was already plugged in when you started your virtual machine, please unplug it, and then plug it back in. This initial step is just to ensure that your Linux virtual machine has full control of the thumb drive, rather than your "real" computer.

### Preparing for disk imaging

Before we can dive into using dd, ddrescue, and guymager to actually make disk images, there is some initial preparation that we need to do. Firstly, we need to find what is essentially an identifier your computer uses to refer to the USB thumb drive as a physical device.

Type `mount` in your terminal and press enter. You will see something similar to this, though there may be slight variation:

```
/dev/sda1 on / type ext4 (rw,errors=remount-ro)
proc on /proc type proc (rw,noexec,nosuid,nodev)
sysfs on /sys type sysfs (rw,noexec,nosuid,nodev)
none on /sys/fs/cgroup type tmpfs (rw)
none on /sys/fs/fuse/connections type fusectl (rw)
none on /sys/kernel/debug type debugfs (rw)
none on /sys/kernel/security type securityfs (rw)
udev on /dev type devtmpfs (rw,mode=0755)
devpts on /dev/pts type devpts (rw,noexec,nosuid,gid=5,mode=0620)
tmpfs on /run type tmpfs (rw,noexec,nosuid,size=10%,mode=0755)
none on /run/lock type tmpfs (rw,noexec,nosuid,nodev,size=5242880)
none on /run/shm type tmpfs (rw,nosuid,nodev)
none on /run/user type tmpfs (rw,noexec,nosuid,nodev,size=104857600,mode=0755)
none on /sys/fs/pstore type pstore (rw)
systemd on /sys/fs/cgroup/systemd type cgroup (rw,noexec,nosuid,nodev,none,name=systemd)
gvfsd-fuse on /run/user/1000/gvfs type fuse.gvfsd-fuse (rw,nosuid,nodev,user=techfocus)
/dev/sr0 on /media/techfocus/VBOXADDITIONS_5.0.0_101573 type iso9660 (ro,nosuid,nodev,uid=1000,gid=1000,iocharset=utf8,mode=0400,dmode=0500,uhelper=udisks2)
```

This is a list of all of the mounted devices in your Linux virtual machine. Look for the line that mentions "TechFocus III". You will see that this line has three parts, first something that looks like `/dev/disk1s02`, followed by `/media/techfocus/Mac\ IIci`, and finally followed by `type HFS`. In other words:

```
/dev/disk1s02 /media/techfocus/Mac\ IIci type NTFS
```

The second part of the line you will recognize as being the name of the USB thumb drive – this is what we call the "Volume". It is what you as a user see when you plug in a readable piece of media – it is where you see all of your files. The first part of the line `/dev/disk1s02` is called the "device file" – this is where your computer assigns a location in its filesystem for the physical device of the USB thumb drive itself. This piece of information – the device file – is of crucial importance, and we will need it later, so write it down.

Now that we have the device file, we need to "unmount" the "Volume". The USB device is currently preoccupied with talking to your operating system so that it can show you the `Mac IIci` Volume and the files inside it. We need its full attention so that `dd` can read it in full. To unmount the Mac IIci Volume, type the following into your terminal and press enter:

```
sudo umount /media/techfocus/Mac\ IIci
```

We now have our device file, and we have unmounted the Volume we would like to image – and so we are ready to disk image!


### Using dd

To begin, open up your terminal. To read the manual for dd, type `man dd` and press enter. As you can see, `dd` has many options. The two we only really care about for this exercise are `if` and `of` – these are short for "input file"" and "output file" or some variant of those words. Press `q` to exit the man page. The basic syntax we want to use for making a disk image with `dd` is as follows:

```
$ dd if=[device file goes here] of=[path to write disk image to]
```

The text inside the `[ ]` brackets is of course a placeholder to explain what actually should go in this place. As you can see, after `if=` we are supposed to write the device file of the disk we want to image. So this should look something like `if=/dev/disk1s02`. The output file is the full file path to where we would like to write the disk image – including the name of the disk image and its file extension. Let's put the disk image on our Desktop and call it "dd_demo.001". This means your `of=` should now read `of=/home/techfocus/Desktop/dd_demo.001`. Stiching it all together, your full and complete command will look something like this:

```
$ dd if=/dev/disk1s02 of=/home/techfocus/Desktop/dd_demo.img
```
Type or copy/pase the above and press enter to begin the process of imaging your disk. You will notice that there is absolutely no indication as to what is happening – is the disk imaging process running? Is it working? Has your computer frozen? By default `dd` does not provide the user with any useful feedback or output. It would be good to coax some information out of it so that we know the process is working, and so that we can get an idea of how far along it is in the process.

In a new terminal window, type `killall -USR1 dd` and press enter. When you return to your terminal window where `dd` is running, you will now see some information displayed. This command forces `dd` to tell us how far along it is – but as you can see it only tells us once. In order to get a constant feed of `dd`'s progress, we will use the `watch` command. Open a new terminal window, type the following command, and press enter:

```
watch -n 1 'killall -USR1 dd'
```

This tells our computer to repeat the `killall` command every second - and thus we are shown `dd`'s progress every second. This is a bit cumbersome though, so lets look at a slightly more featured program that is similar to `dd` but more user-friendly.

### Using ddrescue
In your terminal, type `ddrescue --help` and press enter. As you can see, ddrescue has many options. We actually are not going to use any of them today. `ddrescue`'s syntax is very similar to `dd`, but a bit simpler: `ddrescue [input file] [output file]`. As you can see, `ddrescue` does not have the same `if=` `of=` paradigm as `dd` – you simply type the name of the program, follwed by the device file of the disk you wish to image, followed by the path to and filename of the disk image. Give this a try:

```
$ ddrescue if=/dev/disk1s02 of=/home/techfocus/Desktop/ddrescue_demo.img
```
As you can see, `ddrescue`'s output is much more useful – right out of the box we can see what the program is doing. It will even tell us if there are any errors in reading the source disk – while if this occurs with `dd`it will silently continue. So now we can make raw disk images using two free and open source command line tools. This is great – and as discussed  raw images are wonderful for preservation 

### Further reading
* [The Forensics Wiki](http://forensicswiki.org)




***


![Creative Commons License](https://i.creativecommons.org/l/by/4.0/80x15.png)

This document is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).