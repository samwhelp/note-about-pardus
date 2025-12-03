---
title: ISO
nav_order: 1000
has_children: true
---


# ISO




## 主題

| 主題 |
| --- |
| [Download ISO](https://samwhelp.github.io/note-about-pardus/read/core/iso/download-iso.html) |
| [Boot ISO](https://samwhelp.github.io/note-about-pardus/read/core/iso/boot-iso.html) |




## Live Account

> 使用「Pardus Live ISO」開機後，自動登入的帳號。

| Account  | Value  |
| -------- | ------ |
| Username | `user` |
| Password |  |


> 執行下面指令，更改目前登入帳號的密碼。

``` sh
sudo passwd $(whoami)
```


> 執行下面指令，移除目前登入帳號的密碼。

``` sh
sudo passwd -d $(whoami)
```




## 安裝議題

在「`Pardus 25`」，若是「搭載的安裝程式 ([pardus-installer](https://github.com/pardus/pardus-installer))」，無法將系統正常安裝到硬碟。

可以改回使用「[Calamares Installer](https://calamares.euroquis.nl/guide/welcome/)」來安裝。

使用「`Pardus 25 Live ISO`」開機，連上網路，

執行下面指令，安裝「Pacakge: [calamares](https://packages.debian.org/stable/calamares)」和「Pacakge: [calamares-settings-debian](https://packages.debian.org/stable/calamares-settings-debian)」。

``` sh
sudo apt-get install sudo apt-get install calamares calamares-settings-debian
```

上面兩個「Package」安裝完成後，就可以開啟「`calamares`」來將系統安裝到硬碟。
