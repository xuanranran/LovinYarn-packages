#
# Copyright 2019 Telco Antennas Pty Ltd <nicholas.smith@telcoantennas.com.au>
# SPDX-License-Identifier: Apache-2.0
#

include $(TOPDIR)/rules.mk

# LUCI_TITLE:=Support for ModemManager
# LUCI_DEPENDS:=+modemmanager
#
# include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature


PKG_NAME:=luci-proto-modemmanager
PKG_RELEASE:=1

PKG_SRC_DIR := $(shell pwd)
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/luci-proto-modemmanager
  SECTION:=luci
  CATEGORY:=LuCI
  SUBMENU:=5. Protocols
  TITLE:= Support for ModemManager
  DEPENDS:=+modemmanager
endef

define Package/luci-proto-modemmanager/description
	LuCI protocol interface for ModemManager
endef

define Build/Prepare
       mkdir -p $(PKG_BUILD_DIR)
       cp -r $(PKG_SRC_DIR)/* $(PKG_BUILD_DIR)
       $(Build/Patch)
endef

define Build/Configure
endef

define Build/Compile
endef

# Install all our files, including our LuCI replacement files
define Package/$(PKG_NAME)/install
       $(INSTALL_DIR) $(1)/usr/lib/lua/luci
       $(CP) ./luasrc/* $(1)/usr/lib/lua/luci
endef

$(eval $(call BuildPackage,luci-proto-modemmanager))
