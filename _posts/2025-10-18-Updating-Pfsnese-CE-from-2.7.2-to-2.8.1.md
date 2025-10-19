---
layout: post
title: "Update Pfsense CE 2.7.2 to 2.8.1"
date: 2025-10-18
--- 

 # OLD Problem (Booting PFsense CE with a screen)
 
At First i did a fresh installation of pfsense CE 2.7.2 on my HP Microserver Gen 10 plus,<br> 
I noticed when i reboot the device i needed a **monitor so he can boot up to pfsense**,

<p align="center">
  <img src="/assets/images/pfsense-reboot-pb.jpeg" alt="pfsense boot problem">
</p>

## Solution

So the solution i came up with is to update the system rom firmware using HPE officielle site.
Before i had **U48 2.18 6/24/2020** firmware version, now i have the latest version **U48 3.70 08/08/2025** 

### Update System ROM Firmware 

#### Step 1 

Download the correct version from the officiel website of the manufacture. for me was HPE Microserver Gen 10 plus, <a href = "https://support.hpe.com/connect/s/softwaredetails?language=en_US&collectionId=MTX-b8b6b31789ce4119&tab=releaseNotes"> click here. </a> 

After downloading the firmware file .fwpkg, put it in a flash drive and plug it into the physical hardware.

#### Step 2

> **note :** make sure you have stable power supply or UPS, in case the power gone.
>  you don't want to stop the progress of updating the firmware it is "very dangerous".

```bash
bios -> F9 system utilities -> Embadded Applications -> System ROM -> Select File -> start update
```
### Conclusion 
After finally updating the system rom firmware to the latest version, now you will not have the issue of booting without a screen.
> **issue** i still got to update the Server Platform Services (SPS) from 5.01.03.94.0 to 5.01.05.103.0,
>  But i didn't find how, i couldn't find the SPS update console?
<p align="center"><img src="/assets/images/pfsense-SPS.jpeg" alt="Pfsense SPS"></p> 
<br>

# NEXT STEP 
## Update pfsense CE from 2.7.2 to 2.8.1

### Step 1

You must follow all Pre-Upgrade Tasks in the officiel website of netgate, <a href="https://docs.netgate.com/pfsense/en/latest/install/upgrade-guide-prepare.html "> Pre-Upgrade Tasks.</a> 
I'll mention the important ones

1-make sure you device is capable of handaling the latest version of Pfsense 2.8.1,which was not a problem for me since i had a microserver is powerfull enough. 

2- Make a back up 
```bash
Diagnostics -> Backup/Restore -> Backup area "all"
uncheck "Skip RRD data"
Check "Include extra data"
Click "download configuration as XML"
```
and you're done, keep you backup in a safe place.

3- Remove all installed packages 
> **note :** don't worry every package has a checkbox to keep configuration even after removing it. That's mean after installing it you will get the same configuration as before.

```bash
System -> Package Manager -> Installed packages
```
remove package each one at a time

### Step 2 
**Update**

```bash
system -> update -> branch "Current Stable Version (2.8.1)" -> Confirm
```
