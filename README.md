# gooseOS
Main repository, used for main issue tracking and hosting wiki.

## Edition plan
- Holo Universe, includes GNOME and Steam Deck Vapor theme, but does not have Steam and proprietary drivers
- Gnome Dome, only GNOME, basic software and minimum system, like real Arch
- Plasma Fantastic, only KDE, basic software and minimum system, like real Arch

## Building
### Requirements
Atleast 50 GB of free space
Internet connection
Good CPU for fast builds
Arch-based distro
Some luck and advanced copy-pasting skills

### First start
First, ```git clone``` needed configuration (like holo-universe), and move to directory.
Then, run build, remember the command, it makes the ISO, in the future it will be the main build process:
```bash
sudo mkarchiso -v
```

### File legend
bootableusb.sh - makes a USB pendrive with gooseOS
cleanup.sh - cleans build directories
profiledef.sh - gooseOS branding piece
services.sh - some distro wrap and service link
packages.x86_64 - includes packages, that will be included in livecd and main OS
pacman.conf - pacman configuration, for main OS
airootfs/ - overlay for gooseOS, includes files that will be overrided, added and overlayed, including configs for GDM, some scripts, etc.
efiboot/ - includes EFI settings, do not change unless you know what are you doing, as it can make distro unbootable
grub/ - includes GRUB settings, do not change unless you know what are you doing as it can make distro unbootable
syslinux/ - includes syslinux settings, do not change unless you know what are you doing as it can make distro unbootable

Airootfs will be explained here, other directories do not count, as others are the same as in Arch Linux

#### Airootfs legend
etc/ - mainly GDM settings, pacman mirrorlists and configurations
  - skel/ - includes .bashrc, .config so you can make custom shell and user configuration
root/ - just a placeholder for future changes, in future may include customize_airootfs.sh, but initially there was .automated_script.sh and .zlogin
usr/ - main changes, rest of content here
  - bin/ - includes our custom scripts
  - local/ - local files
    - bin/ - scripts
    - share/ - livecd sound configs
  - share/ - wallpapers and Vapor deck theme
