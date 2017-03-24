# 6Harmonics Inc
# maintainer: Qige Zhao
# 2017.03.17

include $(TOPDIR)/rules.mk

APP_NAME:=grid-lite
PKG_NAME:=grid-lite
PKG_VERSION:=1.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)
PKG_SOURCE_URL:=https://github.com/zhaoqige/6w-grid-lite.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=419e398e1b5b0842d4d6f53c70c23bf645a0a98b

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)


include $(INCLUDE_DIR)/package.mk
#include $(INCLUDE_DIR)/cmake.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=GRID lite for GWS Products
  DEPENDS:=+grid-base +grid-cs
  MAINTAINER:=Qige Zhao <zhaoqige@163.com>
endef

define Package/$(PKG_NAME)/description
  GRID lite for GWS Products Monitor & Control.
  Based on Materialize.CSS
  jQuery.Flot charts.
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DIR) $(1)/www/cgi-bin
	$(INSTALL_DIR) $(1)/www

	$(CP) \
		$(PKG_BUILD_DIR)/lib/* \
		$(1)/usr/lib/lua/
	$(INSTALL_CONF) \
		$(PKG_BUILD_DIR)/conf/$(APP_NAME).conf \
		$(1)/usr/lib/lua/grid/$(APP_NAME).conf
	$(INSTALL_CONF) \
		$(PKG_BUILD_DIR)/conf/$(APP_NAME).conf \
		$(1)/etc/config/$(APP_NAME)
	$(INSTALL_BIN) \
		$(PKG_BUILD_DIR)/bin/* \
		$(1)/www/cgi-bin/
	$(CP) \
		$(PKG_BUILD_DIR)/www/* \
		$(1)/www/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))