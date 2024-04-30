---
layout: post
title: Linux on the Asus Transformer Book T100 CHI / TA
date: Mon, 10 Jun 2019 21:29:14 -0000
description: 
...

Two years ago I tried installing Linux on my Asus Transformer Book T100CHI,
which is a pretty weird little machine in terms of hardware and firmware.
Back then I didn't succeed but today I actually did
and because I didn't find any comprehensive guide/tutorial on how to make the thing usable again with Linux,
I want to share which steps it took me and which hoops I had to jump through, to get everything up and running.

## The device

The Asus Transfromer Book T100CHI is a funny little machine.
Featuring a 64 bit Quad Core Intel Atom Bay Trail processor, 2GB RAM, 32 GB of EMMC internal storage,
a 1920x1200 IPS touch-screen and a bluetooth connected detachable keyboard/touchpad combo,
it only allows for 32 bit UEFI booting.
Nothing else, no 64 bit UEFI, no legacy option to speak off.

## Finding a distro that would actually boot and install fine

My first try was the 32 bit Manjaro version, which did boot fine, install fine, but some things didn't work.
There was no Wifi and Bluetooh, but there was sound.
To improve the situation my first idea was to install a more recent kernel, which I did.
Manjaro32 comes with the 4.14 kernel which isn't ideal at all for this convertiable series of tablets/notebooks
according to the T100 community on Google+.
However, kernel 4.19, which was the most recent one in the repos, didn't boot at all.
Something with the mesa driver was not working, but I didn't care.

After some research I found that Debian offers so called multi-arch ISOs for download
that feature a 32 bit bootloader and a 64 bit bootloader
which would boot either 64 oder 32 bit Debian installers.
The image was twice as big, 600MB, but it did exactly what I wanted.
Boot a more recent 64 bit Linux through a 32 Bit bootloader.
And yes, it booted without issues and installed without issues.
On and btw, I choose Debian 10, nicknamed Buster, because it comes with kernel version 4.19.
<a href="https://www.debian.org/devel/debian-installer/">This is where I got my installation image.</a>

## Installation

I opted for a clean GNOME and Cinnanomon Desktop installation as GNOME has excellent touch support
and Cinnanomon would be lightweight enough if GNOME didn't work well on this machine.

To get internet access I used a USB to Ethernet dongle which was connected to a USB hub together with my mouse and keyboard receiver.

During the installation the installer informed me of a missing firmware, called `brcm/brcmfmac43241b4-sdio.bin`
which I looked up and immediately found in <a href="https://packages.debian.org/sid/firmware-brcm80211">this package</a>.
I remembered this for later.

Luckily, no jerking around with bootloaders was required
because the Debian installer detected my weird system without problems and installed grub for 32IA UEFI.

## Post-Installation proceedure

After a successfull installation I found myself with a working GNOME desktop with touch support, but no Wifi, no Bluetooth and no sound.

### Wifi and Bluetooth

To get Wifi and Bluetooth working, installation of the non-free firmware package I from above was required.
I edited `/etc/apt/sources.list` to add `non-free` at the end of the first two mirrors
and updated my sources with `sudo apt update`.
`firmware-brcm80211` was now successfully found and installed and after a quick reboot, Bluetooth worked, but no Wifi yet.
`dmesg` showed my something about "failed to load firmware for xy".

To actually get Wifi working, I had to copy contents of one of my EFI vars to a file.
I tried mounting the EFI vars with this command:
```bash
mount -t efivarfs none /sys/firmware/efi/efivars
```

Wich did fail because they were already mounted.
To copy the contents of the nvram file to a .txt file that would live next to the binary driver for the wireless,
I executed a command similar to this: 
```bash
cat /sys/firmware/efi/efivars/nvram-74b00bd9-805a-4d61-b51f-43268123d113 < /lib/firmware/brcm/brcmfmac43241b4-sdio.txt
```

Now for a quick reboot and tada, Wifi works! … just as bad as in Windows, constantly loosing connection.
For further information consult
[the brcm80211 driver entry on the Linux Kernel Wiki](https://wireless.wiki.kernel.org/en/users/drivers/brcm80211#firmware_installation1).

### Sound

Sound was fairly easy to get running, all it needed was the installation of `firmware-intel-sound`
and a quick reboot, another non-free firmware-package.

## Conclusion

After about an hour or two of googling and installation I brought this tablet back to life.
Video playback works fine with mpv, browsing the internet is flawless with Firefox,
though YouTube is a bit slow and overall this makes for a soild and portable little Linux machine.

Not every problem has been solved.
I didn't care about brightness control for example, which still doesn't work.
On and also, it won't boot without a USB keyboard attached for some reason.
It is stuck at loading the initramfs during boot without it.
The last one does actually bother me tho because I really wanna be able to boot this without a dongle hanging of the side.

If you have got a T100CHI/TA and it is lying around and collecting dust, this makes for a fun project with actual profilt.
There are some hoops to jump through but in general it works well.
Though please, don't do this if your daily life relies on this tablet, because this is in no way stable or supported.

Also, isn't it amazing how well GNOME is optimized for touch devices like this one?
Props to the GNOME developers: some of you guys are contaminated with java script and bloated-thinking.
After all, 2GB of RAM is barely enough for GNOME, but UI design is something you really rock.
Keep up the amazing work.

Cheers,<br>
Lucy.

## Update 19th of July, 2019

It might also be wise to install `firmware-linux-nonfree` and `firmware-misc-nonfree` for better video playback performance.
For instance, when generating the initramfs it complains about some missing firmware which went away after installing these packages.
This doesn't solve the backlight issue though.
I got this hint from <a href="https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=800835">here</a>.

## Update 30th of April, 2024

I did another round of getting more use out of this tabled by installing Arch Linux!
Wifi, Bluetooth, Wifi and Backlight control work with the usualy firmware package.
All you need to adjust to install the 64bit version is to install the GRUB 32 bit EFI version when taking care of the bootloader.
It'll load a 64 bit kernel regardless.
I do no remember how I managed to boot a arch-ISO though.
