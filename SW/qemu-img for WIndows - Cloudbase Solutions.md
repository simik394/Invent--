---
page-title: "qemu-img for WIndows - Cloudbase Solutions"
url: https://cloudbase.it/qemu-img-windows/
date: "2024-08-17 00:48:31"
tags: [a/sw/images, f/guide, c/examples, p/pwf]
about: ["[[Inv/SW/windows.os|windows.os]]"]
aliases: 
- 
by: 
length: 889
dir: 
---

### Usage examples

**Convert a QCOW2, RAW, VMDK or VDI image to VHDX**

qemu\-img.exe convert source.img \-O vhdx \-o subformat\=dynamic dest.vhdx

**Convert a QCOW2, RAW, VMDK or VDI image to VHD**

qemu\-img.exe convert source.img \-O vpc \-o subformat\=dynamic dest.vhd

*Subformat can be either “dynamic” or “fixed” for VHD (vpc) or VHDX.*

Note: use the fixed VHD subformat for [Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/create-upload-generic), the conversion will automatically take care of the required 1MB virtual size alignment.

**Check a virtual disk for consistency**

qemu\-img.exe check source.qcow2

**Get info about a virtual disk**

qemu\-img.exe info image.qcow2

Run **qemu-img.exe -h** or see the [manual page](https://qemu.weilnetz.de/doc/) for a complete list of all supported options.