---
title: Download ISO
nav_order: 1000
has_children: false
parent: ISO
---


# Download ISO




## Pardus 25

> `Pardus 25` based on `Debian 13`

* Pardus / [Pardus 25.0 Release Note](https://pardus.org.tr/en/pardus-25-release-note/)
* Pardus / [Download](https://pardus.org.tr/en/download/)
* [https://indir.pardus.org.tr/ISO/Pardus25/](https://indir.pardus.org.tr/ISO/Pardus25/)




## 下載腳本

* [下載腳本](https://github.com/samwhelp/pardus-adjustment/tree/main/core/iso/boot-iso/boot-iso-via-grub/demo-boot-pardus-iso)




## 下載點

> 可以到「Pardus / [Download](https://pardus.org.tr/en/download/)」找到下載點。

> 也可以在「[https://indir.pardus.org.tr/ISO/Pardus25/](https://indir.pardus.org.tr/ISO/Pardus25/)」找到下載連結。




## 下載方式


### iso-download.txt

先產生一個檔案「`iso-download.txt`」，內容如下

```

https://indir.pardus.org.tr/ISO/Pardus25/Pardus-25.0-XFCE-amd64.iso
https://indir.pardus.org.tr/ISO/Pardus25/Pardus-25.0-GNOME-amd64.iso
https://indir.pardus.org.tr/ISO/Pardus25/Pardus-25.0-SERVER-amd64.iso

```


### iso-download.sh

接著執行下面的指令，就會下載剛剛「`iso-download.txt`」裡面所列的檔案

``` sh
wget -c -i iso-download.txt
```

> 關於「`-c`」指的是續傳

> 關於「`-i iso-download.txt`」，指的是下載「`iso-download.txt`」裡面所列的檔案




## Boot ISO

> 簡單「[驗證](#驗證)」過「下載完成的ISO檔案」，接下來可以選擇不同的「[Boot ISO](https://samwhelp.github.io/note-about-pardus/read/core/iso/boot-iso.html)」方式。





## 驗證


### md5sum

* [man md5sum](https://manpages.debian.org/stable/coreutils/md5sum.1.en.html)

執行

``` sh
wget -c https://indir.pardus.org.tr/ISO/Pardus25/MD5SUMS

md5sum -c MD5SUMS
```

會看到類似如下的內容

```
Pardus-25.0-XFCE-amd64.iso: OK
Pardus-25.0-GNOME-amd64.iso: OK
Pardus-25.0-SERVER-amd64.iso OK
```
