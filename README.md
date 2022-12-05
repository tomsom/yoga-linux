# yoga-linux (_WIP_)
 - Run Linux on the Lenovo Yoga 7 Gen 7 14" (14ARB7) with AMD Ryzen 6600U / 6800U (Rembrandt)
 - This guide will be using Fedora Workstation 37 with the GNOME (43) desktop environment

_**For more information take a look at the [issues](https://github.com/tomsom/yoga-linux/issues)**_

## Wiki links:
 - [This project](../../wiki)
 - [Arch Wiki](https://wiki.archlinux.org/title/Lenovo_Yoga_7_Gen_7_(14ARB7))

## Latest Fixes:
> **Kernel independent:**
 > - [x] **Fingerprint Sensor**
 > - Seems to be working with the driver from this [Copr repo](https://copr.fedorainfracloud.org/coprs/d-k-bo/libfprint-goodixtls/).
 > - [x] **S4 sleep | Hibernating (guide is still missing)**
 > - As an alternative for S3 sleep, S4 sleep can be made use of (requires a SWAP partition).
 > - [x] **Screen rotation**
 > - Automatic rotation does not work out of the box in GNOME for some reason.
 > - Can be fixed with an [extension](https://github.com/shyzus/gnome-shell-extension-screen-autorotate).
 
> **Kernel 6.1+:**
 > - [x] **Fixed incompatibility with 'Delock' USB-C dock**
 > - [x] **Microphone is working**
 > - [x] **S2Idle is working**
 > - Laptop seems to reliably go to this state (and is also waking up without issues for most laptops).

> **Kernel 6.0+:**
 > - [x] **Keyboard works without patching**

## Partially Fixed:
> **Kernel independent:**
> - [x] **Speakers**
> - Switch to the bottom firing woofers makes the sound bearable, having all 4 speakers working in parallel is still WIP.
> - [X] **GRUB scaling**
> 
> - Because of the 2.8K display the text in GRUB is very small and hardly readable.
> - This can be partially fixed by using a GRUB theme that forces a font size, or manually configuring GRUB.

## Remaining Issues:
> - [ ] **Speakers quality**
> - Even after both 4 speakers get working all together, another challenge will be tune them to sound like they do in Windows with Dolby.

> - [ ] **S3 sleep | Suspending**
> - No option for regular S3 sleep support.

### Remaining issues that don't seem to impact all Yoga 7 Gen 7 users:

 > - [ ] **Waking up from hibernation often needs longer than a reboot/regular system start**
 > - [ ] **Cursor jumps around the screen**
 >  - This is caused by PSR (Panel Self-Refresh), and can be worked around using `amdgpu.dcdebugmask=0x10` as a kernel parameter
 >  - This value is documented [here](https://github.com/torvalds/linux/blob/8813381a62e1f1703f8fbeccc5fa4fcc988be882/drivers/gpu/drm/amd/include/amd_shared.h#L250)

 > - [ ] **System crashes after resuming**
 >  - Yoga laptops with Samsung SSDs may become unstable after resuming from s2idle
 >  - This is a firmware bug in the SSD (PCI ID `0xa80b`)
 >  - This issue is better documented [here](https://github.com/tomsom/yoga-linux/issues/9)

## Useful links:
### Resources:
 - More on sleep states: https://www.kernel.org/doc/Documentation/power/states.txt

### Relevant patches:
 - Microphone:
   - https://lore.kernel.org/all/20220920201436.19734-3-mario.limonciello@amd.com/
   - https://bugzilla.kernel.org/show_bug.cgi?id=216299
 - s2idle: https://lkml.org/lkml/2022/9/21/1207
 - Keyboard: https://patchwork.kernel.org/project/linux-acpi/patch/20220712020058.90374-1-gch981213@gmail.com/

_If you have any more information, other issues or noticed mistakes - feel free to open an issue. Thanks :)_
