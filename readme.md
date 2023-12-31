# What is this?

This is a debian live image creator with the purpose to run on an offline
computer to create and double-check Bitcoin seed generation.
The image is built for wide compatibility, i.e. aimed to run in 
i386 and amd64 architechtures.

# Quickstart

```
$ lb config
# lb build
```

After the build copy the image to the usb key.
WARNING! I use `dd` to write directly into the usb device with following
command
```
# dd if=live-image.iso of=/dev/<your usb device> bs=4M status=progress conv=fdatasync
```
The path to the usb device could be `/dev/sda`, `/dev/sdb`, `/dev/sdc`, etc, depending on
your system. Be careful not to write to the wrong disk or you may lose your
data.

# Config

To configure a live build you would typically call
```
$ lb config
```
This will populate your current directory with the barebones necessary files to
create a live system with default options.
For reproducibility of custom builds I use a set of bash scripts under the `auto`
directory. These are based on a template that you can find
in `/usr/share/doc/live-build/auto`.

The directory in `./config/package-lists` contains a list of packages to be
pre-installed in the system.

Any file in the director `./config/includes.chroot` will be present in the live
system.

Once configuration has been set-up then you can call.
```
# lb build
```

# References 
[1] https://live-team.pages.debian.net/live-manual/html/live-manual/managing-a-configuration.en.html

