# Booting ISO from GRUB2

## Overview
This guide explains how to modify GRUB2 to boot an ISO directly from an existing GRUB2 installation.

## Steps to Modify GRUB2

1. Open the `40_custom` file for editing:
   ```sh
   sudo nano /etc/grub.d/40_custom
   ```
   Use the following file as a reference when modifying this file.

2. Save the changes and exit the editor.

3. Update GRUB2 configuration:
   - For Debian/Ubuntu:
     ```sh
     sudo update-grub2
     ```
   - For CentOS/Fedora/Red Hat:
     ```sh
     sudo grub2-mkconfig -o "$(readlink -e /etc/grub2.cfg)"
     ```
     or, if using UEFI:
     ```sh
     sudo grub2-mkconfig -o "$(readlink -e /etc/grub2-efi.cfg)"
     ```
     alternatively:
     ```sh
     sudo grub2-mkconfig -o /boot/grub2.grub.cfg
     ```
     

## Notes
- Ensure you modify the correct GRUB2 configuration file depending on your system.
- The exact GRUB2 command may vary based on the distribution and bootloader configuration.
## Reference
- https://clonezilla.org/livehd.php

