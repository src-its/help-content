# Using `chkdsk` to maintain a healthy Windows file system [NTFS]


## Overview

Check Disk examines disks and can correct many types of common errors on FAT16, FAT32, and NTFS drives. One of the ways Check Disk locates errors is by comparing the volume bitmap with the disk sectors assigned to files in the file system. The tool cannot, however, repair corrupted data within files that appear to be structurally intact.

Use the Check Disk tool periodically to check the integrity of disks and to eliminate bad index values (such as may occur when a file transfer is interrupted). You can run Check Disk from the command line or through a graphical interface.


## Running Chek Disk with a GUI

Open up Computer and then right-click on the drive you want to check, and choose Properties, or just click the drive, and then click the Properties button.

![](http://cdn5.howtogeek.com/wp-content/uploads/2010/11/image77.png)

Then select the Tools tab, and click the “Check Now” button.

![](http://cdn5.howtogeek.com/wp-content/uploads/2010/11/532x235ximage78.png.pagespeed.ic.pTkjvODqd0.png)

A little dialog will pop up to allow you to choose the options you want for the disk check. You should check both options if you want to really check the disk properly, but if you just want to do a quick check you could select only the first one.

Open up an administrator mode command prompt by searching in the Start menu or screen for “cmd” and then right-clicking on the item and choosing “Run as Administrator”. Type in the following command, substituting the drive letter if necessary.


![](http://cdn5.howtogeek.com/wp-content/uploads/2010/11/image79.png)

## Running Check Disk from the Command Line

You can run Check Disk from an elevated command prompt or within other tools.  Open up an administrator mode command prompt by searching in the Start menu or screen for “cmd” and then right-clicking on the item and choosing “Run as Administrator”.

At the elevated command prompt, you can test the integrity of drive C by typing `chkdsk C:` . Additional flags tell Check Disk  what action to perform.  The `/f` parameter, for example, tells it to performs an analysis of the disk and then repairs any errors it finds, provided that the disk isn’t in use. `chkdsk /r` locates bad sectors and recovers readable information. It implies `/f`, meaning that you are automatically using `chkdsk /r /f`.

The complete syntax for Check Disk is:

`CHKDSK [volume[[path]filename]] [/F] [/V] [/R] [/X] [/I] [/C] [/L[:size]]`

The options and switches for Check Disk are used as follows:

* volume Sets the volume to work with
* path/filename Specifies files to check for fragmentation (FAT16 and FAT32 only)

* `/F` Fixes errors on the disk
* `/V` Displays the full path and name of every file on the disk (FAT16 and FAT32); displays cleanup messages if any (NTFS)
* `/R` Locates bad sectors and recovers readable information (implies /F)
* `/X` Forces the volume to dismount first if necessary (implies /F)
* `/I` Performs a minimum check of index entries (NTFS only)
* `/C` Skips checking of cycles within the folder structure (NTFS only)
* `/L:size` Sets the log file size (NTFS only)
* `/B` Re-evaluates bad clusters on the volume (NTFS only; implies /R)


## Scheduling a scan for an active drive

The disk must be locked to operate chkdsk. If the disk is in use, Check Disk will display a prompt that asks whether you want to schedule the disk to be checked the next time you restart the system.

*Via the Windows GUI*

![](http://cdn5.howtogeek.com/wp-content/uploads/2010/11/image80.png)

*...or, from the command line:*

![](http://cdn5.howtogeek.com/wp-content/uploads/2008/02/image98.png)

Click or type Yes to schedule this check.

To Tell if a manual disk Check is scheduled, open an admin mode command prompt, and then type in the following command:

`chkntfs c:`

![](http://cdn5.howtogeek.com/wp-content/uploads/2008/02/image96.png)

The output is different if the drive is set to be automatically checked.

![](http://cdn5.howtogeek.com/wp-content/uploads/2008/02/image97.png)
