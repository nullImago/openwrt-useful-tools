#
# Copyright (C) 2009-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mdk4
PKG_VERSION:=1.0
PKG_RELEASE:=2

PKG_BUILD_DIR:=$(BUILD_DIR)/mdk4-$(PKG_VERSION)
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/adde88/mdk4.git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_VERSION:=35f87554754de51e6bea7b1eb5759fb119491fb5
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Andreas Nilsen <adde88@gmail.com.com>

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/mdk4
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=+libpthread +libnl +libpcap
  TITLE:= mdk4
  URL:=https://github.com/aircrack-ng/mdk4
  SUBMENU:=wireless
endef

define Package/mdk4/description
  Tool to exploit wireless vulnerabilities. (DEVELOPER VERSION)
endef

MAKE_FLAGS += \
	$(TARGET_CONFIGURE_OPTS)

define Build/Compile
        $(MAKE) -C $(PKG_BUILD_DIR)/src \
                $(TARGET_CONFIGURE_OPTS)
endef

define Package/mdk4/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_BUILD_DIR)/src/mdk4 $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,mdk4))
