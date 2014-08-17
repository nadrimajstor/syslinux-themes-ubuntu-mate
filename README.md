TL;DR
``` bash
cd isolinux #or wherever your files for ISO might be
BASE_URL=https://raw.githubusercontent.com/nadrimajstor/syslinux-themes-ubuntu-mate/master
wget $BASE_URL/ubuntu-mate-syslinux-gfxboot.cfg -O gfxboot.cfg
wget $BASE_URL/ubuntu-mate-syslinux-splash.png -O splash.png
wget $BASE_URL/ubuntu-mate-syslinux-splash.pcx -O splash.pcx
wget $BASE_URL/ubuntu-mate-syslinux-blank.pcx -O blank.pcx
wget $BASE_URL/ubuntu-mate-syslinux-access.pcx -O access.pcx

```
***


All the steps documented 'cos we gonna redo some for live-image-mate-desktop.

Destination paths are relative 'cos I'm standing in the isolinux directory.

``` bash
cp /usr/lib/syslinux/isolinux-debug.bin isolinux.bin
#or
cp /usr/lib/syslinux/isolinux.bin isolinux.bin #for production
```
![](docs/no_configuration_file_found.png)

***


``` bash
cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/isolinux.cfg .
```
![](docs/could_not_find_kernel_image_gfxboot.png)

***


``` bash
cp /usr/lib/syslinux/gfxboot.c32 .
```
![](docs/no_label_keywords_found.png)

***


``` bash
cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/menu.cfg .
```
![](docs/error_setting_up_gfxboot.png)

***


``` bash
tar -xf /tmp/gfxboot-theme-ubuntu/install/bootlogo.tar.gz
```
* This should come from `gfxboot-theme-ubuntu: /usr/share/gfxboot-theme-ubuntu/bootlogo.tar.gz` but at the moment there is some bugchaseing and I built it from source.
* Note that cpio archive `bootlogo` contins only one file `init`. With the help of isolinux bootloader we have access to a filesystem, however for other usages, some files that reside in our isolinux directory might need to be added also inside the `booglogo` cpio archive.
![](docs/blue_background_without_menu.png)

***

So it works... Ok then lets check on dependancyes.

`isolinux.cfg`:
* `default vesamenu.c32`
``` bash
cp /usr/lib/syslinux/vesamenu.c32 .
```

In `menu.cfg` we asked for:
* stdmenu.cfg
``` bash
cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/stdmenu.cfg .
```
* txt.cfg
``` bash
cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/txt.cfg .
```
* gtk.cfg
``` bash
# Can't find it anywhere / don't have a clue reagarding its purpose
```
* adtxt.cfg
``` bash
cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/adtxt.cfg .
```
* adgtk.cfg
``` bash
# Can't find it anywhere / don't have a clue reagarding its purpose
```
* prompt.cfg
``` bash
cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/prompt.cfg .
```
![](docs/blue_background_with_menu.png)
***

stdmenu.cfg:
* splash.png
``` bash
wget https://raw.githubusercontent.com/nadrimajstor/syslinux-themes-ubuntu-mate/master/ubuntu-mate-syslinux-splash.png -O splash.png
```

txt.cfg:
* /casper/vmlinuz `do not go to isolinux directory - ignoring for now`
* /cdrom/preseed/ubuntu.seed `do not go to isolinux directory - ignoring for now`
* /casper/initrd.lz `do not go to isolinux directory - ignoring for now`
* /install/mt86plus `do not go to isolinux directory - ignoring for now`
* localboot 0x80
``` bash
cp /usr/lib/syslinux/chain.c32 .
```

prompt.cfg:
* f1.txt
* f2.txt
* f3.txt
* f4.txt
* f5.txt
* f6.txt
* f7.txt
* f8.txt
* f9.txt
* f10.txt
``` bash
cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/f{1..10}.txt .
```
* exithelp.cfg
``` bash
cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/exithelp.cfg .
```

***

``` bash
wget https://raw.githubusercontent.com/nadrimajstor/syslinux-themes-ubuntu-mate/master/ubuntu-mate-syslinux-splash.pcx -O splash.pcx
wget https://raw.githubusercontent.com/nadrimajstor/syslinux-themes-ubuntu-mate/master/ubuntu-mate-syslinux-gfxboot.cfg -O gfxboot.cfg
wget https://raw.githubusercontent.com/nadrimajstor/syslinux-themes-ubuntu-mate/master/ubuntu-mate-syslinux-blank.pcx -O blank.pcx
wget https://raw.githubusercontent.com/nadrimajstor/syslinux-themes-ubuntu-mate/master/ubuntu-mate-syslinux-access.pcx -O access.pcx
```
