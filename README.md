syslinux-themes-ubuntu-mate
===========================
All the steps documented 'cos we gonna redo some for live-image-mate-desktop.

Destination paths are relative 'cos I'm standing in the isolinux directory.

``` bash
cp /usr/lib/syslinux/isolinux-debug.bin isolinux.bin
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
