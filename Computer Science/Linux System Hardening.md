---
tags:
  - concept
  - security
---
# Physical Security
Obviously, you need to make sure your system is inaccessible to unwanted parties.
But this **is about more than just stealing**. Anyone with access to a Linux machine could easily reset the root password with [[GRUB]], for example.
## Mitigations
- **Set a boot password on your [[BIOS]]/[[UEFI]]**: this will prevent anyone from just booting their own OS on a separate USB, or access your bootloader to do funky stuff like resetting your root password.
  Problem is, this only works for personal devices; you can't always be at a server's location to input a boot password.
- **Add a bootloader password**: Some tools help achieve this on GRUB, for example. One of this is `grub2-mkpasswd-pbkdf2`, which just prompts for your password and makes a hash for you. The hash can then be added to your bootloader's configuration file to prevent access to advanced settings, where the root password reset option is usually located.
  However, it's not all perfect. It can't work for systems deployed from cloud service providers; you can't access the bootloader there.
# Filesystem Partitioning and Encryption
Physical security is great and all, but **what happens when someone steals your drives**? They don't need your OS, they can just extract the data on their own.
**This is why encryption is a thing.** Partly.
## Mitigations
- Use one of the various software tools to encrypt your Linux system. Many modern distributions ship with [[Linux Unified Key Setup]].