# Quickstart

```
$ lb config
# lb build
```

After the build copy the image to the usb key:
```
# dd if=live-image.iso of=/dev/sdb bs=4M status=progress conv=fdatasync
```

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

