---
title: Boot ISO Via GRUB
nav_order: 1040
has_children: false
parent: Boot ISO
grand_parent: ISO
---


# Boot ISO Via GRUB




## 範例專案

* boot-iso-via-grub / [demo-boot-pardus-iso](https://github.com/samwhelp/pardus-adjustment/tree/main/core/iso/boot-iso/boot-iso-via-grub/demo-boot-pardus-iso)




## 下載 ISO

先參考「[Download ISO](https://samwhelp.github.io/note-about-pardus/read/core/iso/download-iso.html)」這篇提到的下載方式，下載「Pardus 官方提供最新的ISO檔案」。

將「ISO檔案」放到「`/opt/iso/pardus/latest/Pardus-25.0-XFCE-amd64.iso`」這個路徑。

舉例執行下面指令

``` sh
sudo curl -fLo /opt/iso/pardus/latest/Pardus-25.0-XFCE-amd64.iso --create-dirs \
	https://indir.pardus.org.tr/ISO/Pardus25/Pardus-25.0-XFCE-amd64.iso
```




## 設定範例

> 接著採用下面其中一種方式來設定。

| GRUB Boot ISO 範例 | 設定檔路徑 | 是否需要執行 update-grub |
| ----------------- | --------- | ----------------------- |
| demo_40_custom | [/etc/grub.d/40_custom](https://github.com/samwhelp/pardus-adjustment/blob/main/core/iso/boot-iso/boot-iso-via-grub/demo-boot-pardus-iso/asset/overlay/etc/grub.d/40_custom) | 修改後，需要執行 `sudo update-grub` |
| demo_41_custom | [/boot/grub/custom.cfg](https://github.com/samwhelp/pardus-adjustment/blob/main/core/iso/boot-iso/boot-iso-via-grub/demo-boot-pardus-iso/asset/overlay/boot/grub/custom.cfg) | 修改後，**不需要**執行 `sudo update-grub` |

> 關於「`sudo update-grub`」指的是「`sudo grub-mkconfig -o /boot/grub/grub.cfg`」




## GRUB Menu Entry / Boot ISO 樣板 / Pardus

``` sh

menuentry "Pardus ISO / Xfce" --class debian {

	set iso_file="/opt/iso/pardus/latest/Pardus-25.0-XFCE-amd64.iso"

	search --set=iso_partition --no-floppy --file ${iso_file}
	probe --set=iso_partition_uuid --fs-uuid ${iso_partition}

	set img_dev="/dev/disk/by-uuid/${iso_partition_uuid}"


	loopback loop (${iso_partition})${iso_file}


	#set boot_option=""
	#set boot_option="components splash quiet"
	#set boot_option="components locales=zh_TW.UTF-8 quiet splash"
	set boot_option="components locales=en_US.UTF-8"


	linux (loop)/live/vmlinuz boot=live buuid=${iso_partition_uuid} findiso=${iso_file} ${boot_option}
	initrd (loop)/live/initrd.img

}

```




## See Also

* Grub 探索筆記 / [GRUB Boot ISO 範例](https://samwhelp.github.io/note-about-grub/read/howto/boot_iso.html)
