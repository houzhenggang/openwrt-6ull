#
# Copyright (C) 2013-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

#PKG_VERSION:=2017.03
#PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https:///github.com/Freescale/u-boot-fslc.git
PKG_SOURCE_VERSION:=02e2e1cb19fcdcb107b73970a1a1230b93f5d40e


#PKG_HASH:=fe732aaf037d9cc3c0909bad8362af366ae964bbdac6913a34081ff4ad565372
PKG_HASH:=52fed6ce16e0c4a50e2cd4defdf9097a

include $(INCLUDE_DIR)/u-boot.mk
include $(INCLUDE_DIR)/package.mk

define U-Boot/Default
  BUILD_TARGET:=imx6ul
  UBOOT_IMAGE:=u-boot.imx
endef


define U-Boot/ev-imx6ul-nano
  NAME:=out4 ev-imx6ul-nano module
endef

define U-Boot/o4-imx6ul-sodimm
  NAME:=out4 o4-imx6ul-sodimm module
endef

define U-Boot/ev-imx6ul-m2
  NAME:=out4 ev-imx6ul-m2 module
endef

UBOOT_TARGETS := \
	ev-imx6ul-nano \
	o4-imx6ul-sodimm \
	ev-imx6ul-m2

UBOOT_MAKE_FLAGS += u-boot.imx

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR_IMAGE)
	$(foreach img,$(UBOOT_IMAGE), \
		$(CP) $(PKG_BUILD_DIR)/$(img) $(STAGING_DIR_IMAGE)/$(BUILD_VARIANT)-$(img); \
	)
endef

$(eval $(call BuildPackage/U-Boot))
