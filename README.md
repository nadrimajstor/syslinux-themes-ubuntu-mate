syslinux-themes-ubuntu-mate
===========================
All the steps documented 'cos we gonna redo some for live-image-mate-desktop.
Destination paths are relative 'cos I'm standing in the isolinux directory.

cp /usr/lib/syslinux/isolinux-debug.bin isolinux.bin
no_configuration_file_found.png

cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/isolinux.cfg .
could_not_find_kernel_image_gfxboot.png

cp /usr/lib/syslinux/gfxboot.c32 .
no_label_keywords_found.png

cp /usr/share/syslinux/themes/ubuntu-trusty/isolinux-live/menu.cfg .
error_setting_up_gfxboot.png

