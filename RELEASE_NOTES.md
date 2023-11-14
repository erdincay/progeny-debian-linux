# Release Notes for Progeny Debian 1.0

## License

See the file LICENSE for the End User Agreement.

## Release Notes

These notes identify and explain known conditions with the installation
and use of the software. Please read each carefully. Contact
support@progeny.com if you have any questions.

- SECURITY ADVISORY: The 2.2.18 Linux kernel installed by Progeny Debian
has security flaws that were not fixed by the Linux community in time
to be included on this CD. After you install your Progeny Debian system
you should immediately apply all security fixes for the Linux kernel
(and any other software included in Progeny Debian) by following the
instructions at http://www.progeny.com/security.

- If your machine already runs Linux make sure it is shut down *cleanly*
before installing this software. The installer incorrectly interprets ext2
filesystems that were not unmounted cleanly as swap partitions. This is
only a problem if you choose "custom partitioning" during the installation
and there are ext2 partitions that weren't unmounted cleanly. This is
not an issue with "entire disk" or "use free space" choices.

- If you use "custom partitioning" and choose to install to a partition
that already contains a Linux distribution you must select "format"
to format the partition (alternatively, delete all the files from the
partition beforehand).  Progeny Debian will not install correctly on
top of an existing Linux distribution, including itself.

- CDs are mounted with exec permission, allowing users to run programs
from a CD. This is a potential security problem, especially if you are
root, but many third-party CDs include an installation program that must
be run to install the software.

- Selecting then unselecting a package set in the GUI package set manager
will cause *all* the packages in the set to be removed when you apply the
changes. This will happen even if the packages were previously installed.
If you select a package set then change your mind it is better to click
the "Revert" button and start over.

- Using the GUI package set manager to install packages from the "Extras"
CD may fail, printing error messages in the status window. However,
the packages in the package set manager may be left checked, as if the
installation completed successfully.  Should this happen, unselect then
reselect one of the packages to activate the "Apply" button, then click
the "Apply" button. The packages should then install correctly.

- The file /etc/apt/sources.list, which is used by apt to identify
repositories from which to install software, contains the Progeny online
repository by default.  This will cause apt to generate error messages
until you run "apt-get update" while connected to the Internet.  This is
not an issue if you use the GUI package set manager while connected to
the Internet.  Comment out the http lines in the sources.list file if
you do not wish to use the Progeny online repository.

- ISA hardware may not be detected properly.  If you have ISA hardware
that is not detected, you may need to manually edit the /etc/modules
file to include that hardware. ISA sound cards often fall in this
category. Modern PCI hardware should be detected properly.

- All hardware must be enabled through the system BIOS in order for
Linux to use it; specifically, USB must be enabled in the BIOS for USB
keyboards to work.

- The BIOS in some laptops will pause for a while when interrogated by
GRUB during installation if the floppy is not attached. The solution
is to either install with the floppy attached, or wait out the pause.
This is not an issue during subsequent boots once GRUB has been installed.

- Some ISA video cards are not supported correctly, causing the
installation to fail during the first stage.

- Using TAB or right arrow does not rotate through button selections.
Shift-TAB and left arrow do rotate through selections correctly.

- When installing on a machine without a mouse you'll have to use the
numeric keypad to move the cursor, and Tab and Shift-TAB to navigate
the widget focus.

- The disk formatting progress meter is inaccurate. It determines progress
based on the number of partitions, ignoring size.

- Installing Progeny Debian using a /boot partition does not work.

- Trying to create a boot floppy using a write-protected floppy disk
will fail silently. Make sure the floppy is not write-protected.

- When upgrading from Progeny Debian Beta 2 or 3, you will be warned
about a kernel upgrade with the same version number. Please follow
the instructions in the warning and reboot immediately afterwards.
The kernel upgrade includes USB support that is needed for USB keyboard
use during the early boot stages.

- When updating from Progeny Debian Beta 2 or 3, you will need to
update apt and upgrade the system using the new CD. Then remove
the old package sets listings (rm /etc/package-sets/*.contents; rm
/etc/package-sets/*.descriptions).  When next time you run the package
set manager you will see the new list of packages.

- We support VA Linux Debian "Slink and a half" Box,
Potato, Potato plus Helix upgrades. Follow the instructions at
http://www.progeny.com/download/. Storm 1.x, and official Debian 2.1
"Slink" upgrades may also work.

- Special procedure for reporting X bugs: Please send a copy of the
/var/log/XFree86.0.log and /etc/X11/XF86Config-4 files, if they exist,
along with a description of the problem(s) to support@progeny.com.

- When reporting *any* bug encountered during installation or that is
hardware-related (i.e., failure of the system to recognize installed
hardware) please include a copy of /var/log/progeny-installer.log in the
bug report. This file contains debugging information that will help us
solve the problem.

## Feedback

Any feedback you send to support@progeny.com will be reviewed.  Bugs can
be reported either through the Web site form (http://bugs.progeny.com)
or using the progeny-bug package found in the "Standard Progeny System"
package set. It provides a "bug" command that is a convenient way of
reporting bugs.
