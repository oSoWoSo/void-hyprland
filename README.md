### FORK OF MAKRENNELS HYPRLAND-VOID

This is a fork of Makrennel's [hyprland-void](https://github.com/Makrennel/hyprland-void) repository, using his template, workflows etc. I just wanted to create my own copy of it since the packages in his repository are outdated.

# Void Extra

This repository contains template files and binaries for building or installing software on Void linux that are not part of the offical repositories. It serves as the Void Linux equivalent of the AUR. 

### Installation

The easiest way to install the packages on Void Linux is using the [binary repository](https://github.com/Encoded14/void-extra/tree/repository-x86_64-glibc) which is built automatically using [GitHub Actions](https://github.com/Encoded14/void-extra/blob/master/.github/workflows/build-latest.yml) whenever a new commit is pushed to this repository.

You can add this repository to xbps's repositories by creating a file such as `/etc/xbps.d/20-void-extra.conf` with the following text:

```
repository=https://raw.githubusercontent.com/Encoded14/void-extra/repository-x86_64-glibc
```

This can be done with the following command:
```
echo repository=https://raw.githubusercontent.com/Encoded14/void-extra/repository-x86_64-glibc | sudo tee /etc/xbps.d/20-void-extra.conf
```
Then you need to refresh your repositories and accept the repository's fingerprint:
```
sudo xbps-install -S
```

Currently this repository provides binary packages for:

- x86_64-glibc

Change the end of the url in `/etc/xbps.d/20-void-extra.conf` as appropriate with the above options.

### Running Hyprland

In order to run Hyprland you will need to install some additional packages which will depend on your setup, for example a [session and seat manager](https://docs.voidlinux.org/config/session-management.html) and [graphics drivers](https://docs.voidlinux.org/config/graphical-session/graphics-drivers/index.html). You may also have to add the user to the `_seatd` group. If you use an Nvidia GPU refer to the [Hyprland Wiki](https://wiki.hyprland.org/Nvidia), but keep in mind that Hyprland does not officially support Nvidia.

### Contributing
Contributions are greatly appreciated. Overall, this repository adheres to the same rules and guidelines as the [official void-packages repository](https://github.com/void-linux/void-packages/blob/master/CONTRIBUTING.md). The main difference is that here, you’re welcome to add template files for Chromium or Firefox forks if they provide additional value beyond changing certain settings or configuration files. 
