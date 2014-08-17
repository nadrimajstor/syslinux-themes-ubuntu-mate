syslinux-themes-ubuntu-mate
===========================
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

