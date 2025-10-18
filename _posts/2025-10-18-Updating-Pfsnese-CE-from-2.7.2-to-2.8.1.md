---
layout: post
title: "Updating Pfsense CE 2.7.2 to 2.8.1"
date: 2025-10-18
---

At First i did a fresh installation of pfsense CE 2.7.2 on my HP Microserver Gen 10 plus,<br> 
I noticed when i reboot the device i needed a **monitor so he can boot to pfsense**,

<p align="center">
  <img src="/assets/images/pfsense-reboot-pb.jpeg" alt="pfsense boot problem">
</p>

# Solution

So the solution i came up with is to update the system rom firmware using HPE officielle site.
Before i had **U48 2.18 6/24/2020** firmware version, now i have the latest version **U48 3.70 08/08/2025** 

## Update System ROM Firmware 

### Step 1 

Download the correct version from the officiel website of the manufacture for me was HPE Microserver Gen 10 plus, <a href = "https://support.hpe.com/connect/s/softwaredetails?language=en_US&collectionId=MTX-b8b6b31789ce4119&tab=releaseNotes"> click here. </a> 



### Step 2

> **note :** make sure you have stable power supply or UPS in case the power gone, you don't stop the progress of updating the firmware "very dangerous". 
```bash
bios -> F9 system utilities -> Embadded Applications -> System ROM -> Select File -> start update
```
