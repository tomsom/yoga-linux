# STILL WIP:
# yoga-linux
Run Linux on the Lenovo Yoga 7 14 (14ARB7) with AMD Ryzen 6800U (Rembrand).
This guide will be using Fedora Workstation 36 with the Gnome (42) desktop environment.

## Issues:
- [x] **[Keyboard not working:](../../wiki/Keyboard-fix)**
  > The keyboard wont be working out of the box. The issue should be resolved with Linux kernel 5.20, which has not been released as of the writing of this guide.
  
- [x] **[S4 sleep (hibernating)](../../wiki/Enable-S4-sleep)**
  > As an alternative for S3 sleep S4 sleep can be made use of. Requiers a swap partition.
  
- [x] **[Screen rotation](../../wiki/Screen-rotation-fix)**
  > Does not work out of the box in gnome for some reason.
  
- [ ] **[GRUB scaling](../../wiki/Fix-GRUB-scaling)**
  > Because of the 2.8K display the text in GRUB is very small and hardly readable.
  
- [ ] **[The speakers suck](../../wiki/Speaker-tuning)**
  > The speakers seem to be tuned the heck out of in Windows with Dolby Atmos

- [ ] **[S3 sleep (suspending)](../../wiki/S3-sleep)**
  > No option for regular S3 sleep support; only for Microsofts S0ix sleep which is not supported by Linux, at least for AMD Processors
  
## [See the wiki for more](../../wiki/Home)

## Contents:
- Installation
  - Login  to windows (without a Microsoft account)
  - Resize encrypted Windows partition
  - Install Fedora
  - Enable On-Screen-Keyboard (for now)

- Enable S4 sleep/hibernation

- Fix the Keyboard
  - Download vanilla Linux kernel
  - Apply the patch
  - Compile and install the modded kernel

- Fix screen rotation
  - Install Screen Autorotate Gnome extension

- Extra 
