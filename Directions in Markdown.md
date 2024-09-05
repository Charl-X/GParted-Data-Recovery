# Data Inspection and Recovery Using The GParted Live Utility on a Bootable USB Drive
___  
  
### Who should attempt data recovery, and why?
___  
##### An IT technician or experienced consumer of computer hardware will start to consider manually recovering data when a hard drive starts logging erros, failing diagnostic tests, and/or making suspicious clicking noises. In ideal cases, there will already be a backup solution in place, and inspecting a damaged drive for recoverable data is not necessary. If this is not the case, this *may* be a reasonable solution.
  
### **Important Warnings**:
 - ##### **As soon as you have determined there is a damaged drive, turn off the computer and unplug it from power.** 
    ##### At this point, you haven't yet made a plan, and it's important to prevent any unneccessary mechanical damage and/or data corruption from read/write operations, especially if the disk in question is the boot drive (the one storing the operating system).
 - ##### **Check the warranty before attempting anything on your own.** 
    ##### If the machine is under warranty, call the manufacturer first and see what help they can offer for failed drives. Data recovery is hard - a specialist has a better chance at recovering more data and doing less damage to the drive in the process.
- ##### **Price out other options, especially if there are I/O (Input/Output) errors** 
    ##### Continuing to run a damaged hard drive will eventually result in further data corruption. I/O errors mean the drive is already *very* damaged. Inspecting and/or copying data from a failing drive without first repairing any mechanical damage at a specialized facility has inherent risks. Your budget will need to be weighed against the importance of the data you're working with. Hiring an expert is effective, but expensive.
##### That being said, if hard drive is still readable, or mostly readable, copying as much as possible onto a more stable medium (a new hard drive or USB drive with sufficient storage - ideally about twice the size of the stored data on the old disk) is often very worth doing. Depending on the extent of data loss, it may be repairable with free tools, or it may be worthwhile to cut your losses before spending money on professional data recovery.

### Required Knowledge and Tools
----
##### Following these instructions requires some familiarity with the Linux command line, as well as knowledge what a hard drive, USB drive, filesystem, and data partition are.

##### You will also need:
1. ##### A blank USB drive with at least 300MB of space for installing and running GParted Live
2. ##### An extra external drive (or an internal drive, + the knowledge to install it) with more than enough space to hold any data that was stored on the old drive

### What is GParted, and what is GParted Live?
---
#### GParted, or the GNOME Partition Editor, 
##### is a free and open source graphical application for managing disk partitions and filesystems. When inspecting the data on a hard drive, the graphical interface gives a good overview of which drives are present on the computer, how many partitions there are, and how much space is being used. It's also helpful for getting oriented to where the drives are physically mounted to the data ports on the motherboard, for the purpose of mounting and inspecting the filesystme, as explained later.    
####
![GParted Main Window](gparted-main-window.png)

##### Further documentation, and instructions for dowloading GParted, can be found at: [GParted.org](https://gparted.org/)    
####
#### GParted Live 
##### is a lightweight, Debian Linux based operating system. It comes with the GParted application pre-installed, as well as several helpful command-line utilities for managing disks and filesystems. It can be loaded onto a relatively small USB drive and run on any x86-64 based computer.
    
### Why use a bootable USB Drive?
___
##### Loading a lightweight operating system onto a USB drive and using that to  inspect a failing disk has a number of benefits:

- ##### If the failing disk happens to be the boot drive, the original operating system may no longer be accessible. Booting from a USB offers an alternative to opening the computer and removing the fialing drive in order to attach it to a working machine.
- ##### A bootable USB drive can be loaded with helpful tools that may not otherwise exist on the original operating system.

### How to Create a GParted Live Bootable USB
----
1. ##### Download the GParted Live .iso file from [gparted.org](https://gparted.org/).
2. ##### On Windows:
    ##### Use a tool like [Rufus](https://rufus.ie/en/) to copy the .iso file onto a USB drive and make it bootable. Alternatively, if you have a larger USB drive, use a tool like [Ventoy](https://www.ventoy.net/en/index.html) or [Yumi] (https://yumiusb.com/) to create a bootable drive that can store and run multiple lightweight operating systems.

### How to Boot from GParted Live USB
___

1. ##### Plug the bootable USB drive into an open USB slot on the computer containing the damaged drive.
2. ##### Plug the computer back into power and turn it on.
3. ##### While the computer is booting, spam-click the special function key to bring up the boot menu. This is usually F12, but on some computer models, it can be F2 or F10 or another key. Consult your user manual if unsure.
4. #### From the boot menu, select the removable USB drive.

##### When GParted Live first boots, it will ask a bunch of questions about settings that can be changed. For our purposes, we can hit Enter to accept the defaults.

### How to Inspect Drive Partitions with Gparted
___


