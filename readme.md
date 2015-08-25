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
```
This document is an introduction and tutorial to the practice of disk imaging. It was produced by Ben Fino-Radin for the American Institute for Conservation of Historic and Artistic Work's third TechFocus workshop, TechFocus III: Caring for Software-based Art, hosted by the Solomon R. Guggenheim Museum, New York, NY on September 25th-26th, 2015.

### What is a disk image?
A disk image is a file that usually contains a complete and linear "recording" of what your computer sees when it looks at a hard drive, USB drive, CD, DVD, or any other kind of digital carriers of information.

###  Why make disk images?
* To preserve a the entireity of a disk as it was delivered by an artist
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

###  Some tools for creating disk images
* dd – aka Direct Duplicate
* ddrescue
* guymager
* many proprietary options

### using dd
To begin, open up your terminal. To read the manual for dd, type ```man dd``` and press enter.


### Further reading
* [The Forensics Wiki](http://forensicswiki.org)




***


![Creative Commons License](https://i.creativecommons.org/l/by/4.0/80x15.png)

This document is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).