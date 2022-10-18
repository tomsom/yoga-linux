_STILL WIP:_
# yoga-linux
Run Linux on the Lenovo Yoga 7 14 (14ARB7) with AMD Ryzen 6800U (Rembrand).
This guide will be using Fedora Workstation 36 with the Gnome (42) desktop environment.
## [🖝 Check out the wiki](../../wiki/)

***
_You might also want to take a look at the Arch Wiki article on this device [here.](https://wiki.archlinux.org/title/Lenovo_Yoga_7_Gen_7_(14ARB7))_
***

### _Update:_
- **since Kernel 6.0:**
  > Keyboard works(without patching)
  
- **since Kernel 6.1:**
  > Mic is working
  
  > Machine seems to go reliably to s2idle state(and is also waking up without issues)
***

## Issues:

- [x] **Keyboard not working**
  > The keyboard wont be working out of the box. The issue is resolved with Linux Kernel 6.0
  
- [x] **Internal mic not working**
  > Internal mic does not work. The issue is resolved with Linux kernel 6.1
  
- [x] **S0 sleep (s2idle)**
  > A lowerish power sleep state. Device wakes up almost immediatelly, often brakes keyboard or touch. Resoved with Kernel 6.1
  
- [x] **S4 sleep (hibernating)(guide is still missing)**
  > As an alternative for S3 sleep S4 sleep can be made use of. Requires a swap partition
  
- [ ] **S3 sleep (suspending)**
  > No option for regular S3 sleep support; only for Microsofts S0ix sleep which is not supported by Linux, at least for AMD Processors

- [ ] **Screen rotation**
  > Does not work out of the box in gnome for some reason
  
- [ ] **GRUB scaling**
  > Because of the 2.8K display the text in GRUB is very small and hardly readable
  
- [ ] **The speakers suck**
  > The speakers seem to be tuned the heck out of in Windows with Dolby Atmos, also Linux only recognizes 2 out of the 4 speakers

***

## Other stuff:
### More issues I've noticed:
- Kernel 6.1 is incompatible with my (Delock) USB-C dock(system freezes)
- Waking up from hibernation often needs longer than a reboot/regular system start

### Resources:
- Arch Wiki article: https://wiki.archlinux.org/title/Lenovo_Yoga_7_Gen_7_(14ARB7)
- More on sleep states: https://www.kernel.org/doc/Documentation/power/states.txt

### Relevant patches:
- Microphone:

  https://lore.kernel.org/all/20220920201436.19734-3-mario.limonciello@amd.com/

  https://bugzilla.kernel.org/show_bug.cgi?id=216299
- s2idle: https://lkml.org/lkml/2022/9/21/1207
- Keyboard: https://patchwork.kernel.org/project/linux-acpi/patch/20220712020058.90374-1-gch981213@gmail.com/

***

_If you know anything more, have other issues or noticed a mistake i made - feel free to open an issue. thanks :)_
