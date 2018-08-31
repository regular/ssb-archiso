ssb-archiso
===
> Create a reproducible ArchLinux live ISO with or without persistent storage and optionally encrypted rootfs


Prerequsits
---

- [ssb-pacman](https://github.com/regular/ssb-pacman)
- [regaur/kiosk-initcpio](https://github.com/regaur/kiosk-initcpio)
- all the packages you want to install need to be on a local ssb-pacman mirror

Installation
---

```
git clone https://github.com/regular/ssb-archiso.git
cd ssb-archiso
lin -s $(pwd)/buildfs.sh /usr/bin/ssb-archiso
```

Usage
--

- Copy the contents of `config.proto` to your project's directory and adjust as needed.
- `make iso` creates a new directory named `root` in the current working directory and installs a root file system into it.
- directory `build` will contain a squashfs image of `root` and images for the EFI boot partition and (optionally) an empty data partition.
- an ISO image will be created in the current working directory, ready for being dd'ed onto a USB thumb drive.
- `make clean` deletes `root` and `build`
- If there are newly created, random passwords (for user accounts or the encrypted rootfs), you'll find them in `passwords`.


