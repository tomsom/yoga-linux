# yoga-linux (_WIP_)
 - Run Linux on the Lenovo Yoga 7 Gen 7 14" (14ARB7) with AMD Ryzen 6600U / 6800U (Rembrandt)
 - This guide will be using Fedora Workstation 36 with the GNOME (42) desktop environment

## Wiki links:
 - [This project](../../wiki)
 - [Arch Wiki](https://wiki.archlinux.org/title/Lenovo_Yoga_7_Gen_7_(14ARB7))

## Updates:
 - **Kernel 6.1+:**
  > Mic is working
  > Machine seems to go reliably to s2idle state (and is also waking up without issues for most laptops)

 - **Kernel 6.0+:**
  > Keyboard works without patching

 - _**For more information take a look at the issues**_

## Problems:
- [x] **Keyboard not working**
  > The keyboard doesn't be work out of the box (Fixed in kernel 6.0)

- [x] **Internal mic not working**
  > Internal mic does not work (Fixed in kernel 6.1)

- [x] **S0 sleep (s2idle)**
  > A lower power sleep state: device wakes up almost immediately, but often breaks the keyboard or touchscreen (Fixed in kernel 6.1)

- [x] **The speakers suck**
  > Switch to the bottom firing woofers makes the sound bearable, having all 4 speakers working in parallel is still WIP

- [x] **S4 sleep (hibernating) (guide is still missing)**
  > As an alternative for S3 sleep S4 sleep can be made use of (requires a swap partition)

- [ ] **S3 sleep (suspending)**
  > No option for regular S3 sleep support; only for Microsofts S0ix sleep which is not supported by Linux, at least for AMD Processors

- [ ] **Screen rotation**
  > Does not work out of the box in GNOME for some reason
  > However, [this](https://extensions.gnome.org/extension/5389/screen-rotate/) extension fixes this for Wayland, as long as `iio-sensor-proxy` is installed

- [ ] **GRUB scaling**
  > Because of the 2.8K display the text in GRUB is very small and hardly readable
  > This can be partially fixed by using a GRUB theme that forces a font size, or manually configuring GRUB

## Other issues:
 - These issues don't seem to impact all Yoga 7 Gen 7 users
 - **Cursor jumps around the screen**
  - This is caused by PSR (Panel Self-Refresh), and can be worked around using `amdgpu.dcdebugmask=0x10` as a kernel parameter
  - This value is documented [here](https://github.com/torvalds/linux/blob/8813381a62e1f1703f8fbeccc5fa4fcc988be882/drivers/gpu/drm/amd/include/amd_shared.h#L250)

 - **System crashes after resuming**
  - Yoga laptops with Samsung SSDs may become unstable after resuming from s2idle
  - This is a firmware bug in the SSD (PCI ID `0xa80b`)
  - This issue is better documented [here](https://github.com/tomsom/yoga-linux/issues/9)

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

_If you have any more information, other issues or noticed mistakes - feel free to open an issue. Thanks :)_
