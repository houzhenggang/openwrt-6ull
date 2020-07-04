#
# Copyright (C) 2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/image.mk

#################################################
# Images
#################################################

DEVICE_VARS += MKUBIFS_OPTS UBOOT BOOT_SCRIPT



#################################################
# Devices
#################################################


KERNEL_LOADADDR=0x10008000

define Device/Default
  PROFILES := imx6ull
  FILESYSTEMS := ext4
  KERNEL_INSTALL := 1
  KERNEL_SUFFIX := -zImage
  KERNEL_NAME := zImage
  KERNEL_PREFIX := $$(IMAGE_PREFIX)
#  KERNEL := kernel-bin | uImage | install-dtb none
  IMAGE/dtb := install-dtb
endef



define Device/ev-imx6ul-nano
  DEVICE_VENDOR := Evodbg
  DEVICE_MODEL := ev-imx6ul-nano
  DEVICE_DTS := ev-o4-imx6ul-nano
    IMAGES := dtb
    IMAGE/dtb := install-dtb 
    KERNEL := kernel-bin | install-dtb
endef
TARGET_DEVICES += ev-imx6ul-nano

define Device/o4-imx6ul-sodimm
  DEVICE_VENDOR := Out4
  DEVICE_MODEL := o4-imx6ul-sodimm
  DEVICE_DTS := o4-imx6ul-sodimm
  UBOOT := o4-imx6ul-sodimm
    IMAGES := dtb
    IMAGE/dtb := install-dtb.
    KERNEL := kernel-bin | install-dtb
endef
TARGET_DEVICES += o4-imx6ul-sodimm

define Device/ev-imx6ul-m2
  DEVICE_VENDOR := Evodbg
  DEVICE_MODEL := ev-imx6ul-m2
  DEVICE_DTS := ev-imx6ul-m2
    IMAGES := dtb
    IMAGE/dtb := install-dtb.
    KERNEL := kernel-bin | install-dtb
endef
TARGET_DEVICES +=  \
	ev-imx6ul-m2 





$(eval $(call BuildImage))
